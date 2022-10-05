---
description: Instruções para usar certificados personalizados.
title: Usar certificados personalizados no Data Workbench
uuid: c3a2db27-bdb2-44b3-95dd-65eedd05c957
exl-id: f813d599-723f-4b5d-a0b5-f4d71c1b1a22
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 1%

---

# Usar certificados personalizados no Data Workbench{#using-custom-certificates-in-data-workbench}

{{eol}}

Instruções para usar certificados personalizados.

Um certificado usado pelo cliente ou servidor do Data Workbench precisa ser assinado por uma autoridade de certificação confiável (autoridade de certificação). Os clientes do Data Workbench recebem certificados assinados pela CA da Visual Sciences. Esses certificados são confiáveis pelo software Data Workbench, já que a variável [!DNL trust_ca_cert.pem] (fornecido junto com o software Insight e armazenado no **Certificados** diretório de servidores e clientes) contém um *Certificado CA raiz* para a CA da Visual Sciences. Esses certificados são usados para licenciamento do software e autenticação quando clientes e servidores se comunicam usando SSL. Somente certificados emitidos pela CA da Visual Sciences podem ser usados para licenciamento, mas outros certificados podem ser usados para comunicação e autenticação. Os certificados emitidos por CA que não a Visual Sciences são a seguir referidos como *certificados personalizados.*

**Observação importante:** Para servidores e clientes, o software Data Workbench usa os arquivos de certificado instalados no cliente ou no servidor **Certificados** diretório ou certificados explicitamente identificados em sua configuração. No entanto, também é possível usar a variável [Windows Certificate Store](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/crypto-api.md#concept-4acb13b7de9340ea8cde8ad84b93358d) para clientes.

As instruções a seguir descrevem os procedimentos a seguir para a utilização de certificados personalizados para a comunicação entre clientes e servidores do Data Workbench. Nem todos os detalhes são um requisito difícil e podem ser utilizadas diferentes variações no processo. No entanto, os procedimentos abaixo foram testados para funcionar.

## Configuração de certificados de cliente personalizados {#section-2083fd41973e451fa404e7a4ae4da591}

1. Adicionar o certificado da autoridade de certificação emissora ao [!DNL trust_cert_ca.pem], que é instalado no **Certificados** diretório do cliente e de cada servidor em cada cluster que deve ser acessado usando este certificado personalizado.

1. Obtenha um certificado personalizado para cada servidor no cluster com as seguintes condições:

   1. O certificado é formatado como um [!DNL .pem] certificado.
   1. O certificado contém sua chave e é não criptografado (ou seja, não tem senha/senha).

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

   1. O certificado tem o CN, O, OU, etc. conforme necessário para este cliente nos servidores [!DNL Access Control.cfg] arquivo.
   1. O certificado foi emitido com um *propósito&#42;&#42;&#42;* de *cliente* (ou ambos *server* **e** *cliente*).

      Para verificar se um certificado tem um código de finalidade de servidor e/ou cliente, os seguintes comandos podem ser usados:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Para certificados de servidor, ambos os comandos devem fornecer:

      ```
      custom_communications_cert.pem: OK
      ```

      Para um certificado de cliente, somente o segundo comando é necessário para fornecer [!DNL OK].

1. Coloque o certificado no **Certificados** diretório.
1. Em [!DNL Insight.cfg] nos termos do *serverInfo* para cada cluster que deseja usar este certificado, verifique se *certificado de cliente personalizado* é nomeado, como:

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:
   <my_custom_client_cert.pem>
   ```

## Configurar certificados de servidor personalizados {#setting-up-custom-server-certificates}

Esta seção parte do princípio que você tem um cluster em execução, usando certificados emitidos pela Visual Sciences e a configuração segue práticas comuns (como *Componentes para servidores de processamento* no principal é sincronizado com o *Componentes* diretórios de todas as DPUs).

1. Adicionar o certificado da autoridade de certificação emissora ao [!DNL trust_cert_ca.pem] que é instalado em cada servidor no cluster e em todos os clientes que precisam se comunicar com esse cluster.
1. Obtenha um certificado personalizado para cada servidor no cluster com estes requisitos:

   1. O certificado personalizado é formatado como um [!DNL .pem] certificado.
   1. O certificado contém sua chave e é não criptografado (ou seja, não tem senha/senha).

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
   1. O certificado foi emitido com o objetivo de *server* e *cliente*.

      Para verificar se um certificado tem um código de finalidade de servidor e/ou cliente, os seguintes comandos podem ser usados:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Para certificados de servidor, ambos os comandos devem fornecer:

      ```
      custom_communications_cert.pem: OK
      ```

      Para um certificado de cliente, somente o segundo comando é necessário para fornecer [!DNL OK].

1. Instale o certificado personalizado de cada servidor na **Certificados** diretório do servidor como [!DNL custom_communications_cert.pem].

1. Usando um editor de texto, adicione a seguinte linha em **Communications.cfg** em ambas as *Componentes* e *Componentes para servidores de processamento* diretórios , logo abaixo da primeira linha ([!DNL component = CommServer]):

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Reinicie todos os servidores.

**Sobre o Aviso de Falha de Certificado**

Quando o servidor ou cliente do Insight está procurando um **licença** no **Certificados** , ele tenta validar todos os certificados (exceto [!DNL trust_ca_cert.pem]), contra uma cópia codificada do certificado CA Insight, que falha em qualquer certificado personalizado presente no diretório. O servidor emite este aviso:

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

Esse aviso pode ser ignorado com segurança.
