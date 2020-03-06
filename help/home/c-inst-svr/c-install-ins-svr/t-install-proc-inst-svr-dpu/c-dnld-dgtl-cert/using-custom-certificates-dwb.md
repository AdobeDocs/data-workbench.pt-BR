---
description: Instruções para uso de certificados personalizados.
title: Uso de certificados personalizados na Análise de big data
uuid: c3a2db27-bdb2-44b3-95dd-65eedd05c957
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Uso de certificados personalizados na Análise de big data{#using-custom-certificates-in-data-workbench}

Instruções para uso de certificados personalizados.

Um certificado usado pelo cliente ou servidor da Análise de big data precisa ser assinado por uma autoridade de certificação (autoridade de certificação) confiável. Os clientes do Análise de big data recebem certificados assinados pela CA do Visual Sciences. Esses certificados são confiáveis pelo software Análise de big data, já que o [!DNL trust_ca_cert.pem] (fornecido junto com o software Insight e armazenado no diretório **Certificados** tanto dos servidores quanto dos clientes) contém um Certificado *CA* raiz para a CA do Visual Sciences. Esses certificados são usados para licenciamento do software e autenticação quando clientes e servidores se comunicam entre si usando SSL. Somente certificados emitidos pela CA do Visual Sciences podem ser usados para licenciamento, mas outros certificados podem ser usados para comunicação e autenticação. Certificados emitidos por CAs que não sejam Visual Sciences são referidos abaixo como certificados *personalizados.*

**Observação importante:** Para servidores e clientes, o software Análise de big data usa os arquivos de certificado instalados no diretório ou certificados **Certificados** do cliente ou servidor explicitamente identificados em sua configuração. No entanto, você também pode usar o Windows Certificate Store [](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/crypto-api.md#concept-4acb13b7de9340ea8cde8ad84b93358d) para clientes.

As instruções a seguir descrevem os procedimentos a serem seguidos para usar certificados personalizados para comunicação entre clientes e servidores da Análise de big data. Nem todos os pormenores são um requisito difícil e podem ser utilizadas variações diferentes no processo. No entanto, os procedimentos abaixo foram testados para funcionar.

## Configuração de certificados de cliente personalizados {#section-2083fd41973e451fa404e7a4ae4da591}

1. Adicione o certificado da CA emissora ao [!DNL trust_cert_ca.pem], que está instalado no diretório **Certificados** do cliente e o de cada servidor em cada cluster que deve ser acessado usando este certificado personalizado.

1. Obtenha um certificado personalizado para cada servidor no cluster com as seguintes condições:

   1. O certificado é formatado como um [!DNL .pem] certificado.
   1. O certificado contém sua chave e não é criptografado (isto é, não tem senha/senha).

      Um certificado contém sua chave com uma das seguintes linhas:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Uma maneira de remover a frase de senha de um [!DNL .pem] certificado:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. O certificado tem o CN, O, OU, etc. conforme necessário para este cliente no arquivo dos servidores [!DNL Access Control.cfg] .
   1. O certificado foi emitido com uma *finalidade **** de *cliente* (ou *servidor* **e** *cliente*).

      Para verificar se um certificado tem um código de finalidade de servidor e/ou cliente, os seguintes comandos podem ser usados:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Para certificados de servidor, ambos os comandos devem fornecer:

      ```
      custom_communications_cert.pem: OK
      ```

      Para um certificado de cliente, somente o segundo comando é necessário para ceder [!DNL OK].

1. Coloque o certificado no diretório **Certificados** do cliente.
1. Em [!DNL Insight.cfg] serverInfo *para cada cluster que você deseja usar este certificado, verifique se o certificado* do cliente ** personalizado está nomeado, como:

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:
   <my_custom_client_cert.pem>
   ```

## Configuração de certificados de servidor personalizados {#setting-up-custom-server-certificates}

Esta seção supõe que você tem um cluster que está ativo e em execução, usando certificados emitidos pelo Visual Sciences, e a configuração segue práticas comuns (como o diretório *Componentes para Servidores* de Processamento no mestre é sincronizado com os diretórios *Componentes* de todas as DPUs).

1. Adicione o certificado da CA emissora ao [!DNL trust_cert_ca.pem] que está instalado em todos os servidores do cluster e todos os clientes que precisam se comunicar com este cluster.
1. Obtenha um certificado personalizado para cada servidor no cluster com estes requisitos:

   1. O certificado personalizado é formatado como um [!DNL .pem] certificado.
   1. O certificado contém sua chave e não é criptografado (isto é, não tem senha/senha).

      Um certificado contém sua chave se tiver uma linha como:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Uma maneira de remover a frase de senha de um [!DNL .pem] certificado:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. O certificado tem o mesmo CN que o [!DNL server_cert.pem] atualmente instalado no servidor.
   1. O certificado foi emitido com uma finalidade de *servidor* e *cliente*.

      Para verificar se um certificado tem um código de finalidade de servidor e/ou cliente, os seguintes comandos podem ser usados:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Para certificados de servidor, ambos os comandos devem fornecer:

      ```
      custom_communications_cert.pem: OK
      ```

      Para um certificado de cliente, somente o segundo comando é necessário para ceder [!DNL OK].

1. Instale o certificado personalizado de cada servidor no diretório **Certificados** do servidor como [!DNL custom_communications_cert.pem].

1. Usando um editor de texto, adicione a seguinte linha ao arquivo **Communications.cfg** nos diretórios *Components* e *Components for Processing Servers (Componentes para processamento de servidores* ), logo abaixo da primeira linha ([!DNL component = CommServer]):

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Reinicie todos os servidores.

**Sobre o Aviso de Falha de Certificado**

Quando o servidor ou cliente do Insight está procurando um certificado de **licença** no diretório **Certificados** , ele tenta validar todos os certificados (exceto [!DNL trust_ca_cert.pem]) em relação a uma cópia codificada do certificado CA do Insight, que falha em qualquer certificado personalizado presente no diretório. O servidor emite este aviso:

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

Este aviso pode ser ignorado com segurança.
