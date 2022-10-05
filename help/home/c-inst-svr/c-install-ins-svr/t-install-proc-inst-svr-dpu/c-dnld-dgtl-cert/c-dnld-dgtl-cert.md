---
description: Informações gerais sobre certificados digitais e procedimentos para baixá-los e instalá-los.
title: Baixar e instalar certificados digitais
uuid: ac484e96-21dc-4643-ae74-01ac957e30ee
exl-id: 8aae9b63-7df0-4725-9833-711246bbe746
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 100%

---

# Baixar e instalar certificados digitais{#downloading-and-installing-the-digital-certificates}

{{eol}}

Informações gerais sobre certificados digitais e procedimentos para baixá-los e instalá-los.

* [Compreender os certificados digitais](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-e48a776ef39042759d1dfb3444996d8b)
* [Certificados bloqueados por nó](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-b3dc7dcf2aa3439cbe66b0461b42d485)
* [Certificados atuais](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-15aabaa8625c46edaa7436e1f3fc29c5)
* [Usar certificados digitais em máquinas sem acesso à Internet](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)
* [Procedimentos de instalação de certificados digitais](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)

## Compreender os certificados digitais {#section-e48a776ef39042759d1dfb3444996d8b}

A Adobe usa certificados digitais X.509 para identificar e autenticar os componentes cliente e servidor que compõem uma implementação.

Na instalação de um componente de servidor ( [!DNL Insight Server] ou [!DNL Repeater]), instale o certificado digital emitido pela Adobe para o componente. Se precisar migrar o aplicativo Adobe para outro computador, obtenha um novo certificado da Adobe. Para isso, entre em contato com o Atendimento ao cliente da Adobe.

O nome comum que aparece neste certificado identifica o servidor com um nome de domínio especificado (por exemplo, [!DNL vs001a.mycompany.com]). Quando um cliente de servidor se conecta a esse servidor, o servidor apresenta esse certificado como prova de que ele seja de fato o servidor solicitado pelo cliente.

Da mesma forma, ao instalar um cliente de servidor (por exemplo, [!DNL Insight] ou [!DNL Report]), instale o certificado digital que autoriza um indivíduo nomeado (por exemplo, Jane Smith) a usar o aplicativo cliente instalado. Se precisar migrar seu aplicativo Adobe para outra máquina ou outro usuário nomeado, obtenha um novo certificado da Adobe. Para isso, entre em contato com o Atendimento ao cliente da Adobe.

O aplicativo cliente apresenta esse certificado digital para obter acesso a um componente de servidor. Um administrador do componente de servidor pode restringir o acesso aos recursos do servidor com base no nome comum ou nos valores da unidade organizacional exibidos no certificado do cliente.

Os certificados digitais X.509 instalados com aplicativos Adobe também permitem que os componentes cliente e servidor troquem informações por SSL (Secure Sockets Layer). O SSL protege as transmissões via HTTP usando um sistema de criptografia de chave pública e privada. A implementação do SSL pela Adobe é compatível com chaves RSA de 1024 bits e usa um algoritmo de criptografia RC4 de 128 bits.

Além da segurança, os certificados digitais que você instala também funcionam como chaves de licença que permitem executar o software da Adobe instalado. Para funcionar corretamente, um certificado digital deve ser atual e bloqueado por nó, ou o aplicativo não inicia.

## Criptografia de cadeia de caracteres {#section-8abe6b2d95704d38a04137d5c4602f0b}

Consulte [Criptografia de cadeia de caracteres](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/string-encryption.md#concept-35da0b53650a4d7e82b240ad27f6d45a) para criptografar senhas.

## Certificados bloqueados por nó {#section-b3dc7dcf2aa3439cbe66b0461b42d485}

Um certificado bloqueado por nó é um certificado digital que foi registrado na máquina na qual está instalado. O bloqueio de nó associa permanentemente um certificado a um identificador de nó específico (um valor que identifica exclusivamente uma máquina específica). Para que o nó bloqueie o certificado, a máquina deve ter acesso à Internet ao Adobe License Server ou a um servidor proxy que tenha acesso ao License Server.

Se estiver instalando em uma máquina que não acesse a Internet, obtenha e instale um certificado especial pré-bloqueado, conforme descrito em [Usar certificados digitais em computadores sem acesso à Internet](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa).

Ao instalar em uma máquina que possa acessar a Internet, o certificado digital será bloqueado automaticamente no nó na primeira vez que você iniciar seu produto da Adobe. Depois do bloqueio por nó, o certificado não pode ser usado em outra máquina. Se precisar migrar o produto da Adobe para outra máquina, obtenha um certificado novo e desbloqueado da Adobe.

## Certificados atuais {#section-15aabaa8625c46edaa7436e1f3fc29c5}

Além do bloqueio por nó, um certificado digital deve estar atualizado. Para permanecer atual, o certificado deve ser revalidado regularmente (geralmente a cada 30 dias, mas pode variar dependendo do contrato com a Adobe). Se o computador tiver acesso à Internet, o processo de revalidação será totalmente transparente. O produto da Adobe se conecta automaticamente ao License Server e revalida o certificado quando necessário. Se o computador não tiver acesso à Internet, será necessário instalar manualmente os certificados atualizados, conforme descrito na seção a seguir.

## Usar certificados digitais em máquinas sem acesso à Internet {#section-809366329a7d4e198f95fe06c1f534fa}

Se a instalação for em uma máquina sem acesso à Internet, solicite um certificado pré-bloqueado para a instalação do [!DNL Insight Server]. Um certificado pré-bloqueado é um certificado digital que é bloqueado manualmente pela Adobe para o identificador de nó do computador.

Para solicitar um certificado pré-bloqueado, envie o identificador do nó e o número do certificado para o Atendimento ao cliente da Adobe. Para obter o identificador de nó da máquina, entre em contato com o Atendimento ao cliente da Adobe para solicitar o utilitário Adobe Node Identifier. Você também pode obter o identificador do nó a partir do alerta de que o software da Adobe apresenta problemas ao tentar se conectar ao License Server e não conseguir.

Ao receber o certificado pré-bloqueado, instale-o conforme descrito nas duas últimas etapas de [Procedimentos de instalação de certificados digitais](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b). Quando o certificado precisar ser revalidado, baixe um novo validado do License Server e reinstale-o no computador.

## Procedimentos de instalação de certificados digitais {#section-19f31676aad344a98e26e4fca1fad03b}

**Para baixar e instalar o certificado digital**

1. Abra o navegador em [https://aap.adobe.com](https://aap.adobe.com).

   >[!NOTE]
   >
   >O navegador pode solicitar que você apresente um certificado digital neste momento. Se isso acontecer, basta clicar em **[!UICONTROL Cancel]** para fechar a caixa de diálogo.

1. Na tela de logon, digite o **[!UICONTROL Account Name]** e os **[!UICONTROL Password]** que recebeu da Adobe e clique em **[!UICONTROL login]**.

1. Localize o certificado emitido para o seu [!DNL Insight Server] e clique no ícone associado.

   >[!NOTE]
   >
   >Anote o nome comum atribuído a este certificado. Use esse nome em uma etapa posterior.

1. Quando solicitado a salvar o certificado, clique em **[!UICONTROL Save]**. (Observe que o nome do arquivo corresponde ao nome comum associado ao certificado.)
1. Baixe o arquivo para a pasta [!DNL Certificates] no diretório em que você instalou o [!DNL Insight Server]. Esta pasta já contém um arquivo de certificado chamado [!DNL trust_ca_cert.pem]. Esse arquivo de certificado deve estar sempre presente.

1. Renomeie o arquivo de certificado baixado para:

[!DNL server_cert.pem]
