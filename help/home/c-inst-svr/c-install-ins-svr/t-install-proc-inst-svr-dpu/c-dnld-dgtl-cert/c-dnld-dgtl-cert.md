---
description: Informações gerais sobre certificados digitais e procedimentos para baixá-los e instalá-los.
solution: Analytics
title: Download e instalação de certificados digitais
uuid: ac484e96-21dc-4643-ae74-01ac957e30ee
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 3%

---


# Download e instalação de certificados digitais{#downloading-and-installing-the-digital-certificates}

Informações gerais sobre certificados digitais e procedimentos para baixá-los e instalá-los.

* [Compreender os certificados digitais](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-e48a776ef39042759d1dfb3444996d8b)
* [Certificados bloqueados por nó](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-b3dc7dcf2aa3439cbe66b0461b42d485)
* [Certificados atuais](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-15aabaa8625c46edaa7436e1f3fc29c5)
* [Usando certificados digitais em máquinas sem acesso à Internet](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)
* [Procedimentos de instalação de certificados digitais](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)

## Compreender os certificados digitais {#section-e48a776ef39042759d1dfb3444996d8b}

O Adobe usa certificados digitais X.509 para identificar e autenticar os componentes cliente e servidor que compõem uma implementação.

Ao instalar um componente de servidor ( [!DNL Insight Server] ou [!DNL Repeater]), você deve instalar o certificado digital emitido pelo Adobe para o componente. Se precisar migrar seu aplicativo Adobe para outro computador, você deve obter um novo certificado do Adobe. Para fazer isso, entre em contato com o Atendimento ao cliente da Adobe.

O nome comum que aparece neste certificado identifica o servidor por um nome de domínio especificado (por exemplo, [!DNL vs001a.mycompany.com]). Quando um cliente de servidor se conecta a esse servidor, o servidor apresenta esse certificado como prova de que ele seja, de fato, o servidor solicitado pelo cliente.

Da mesma forma, ao instalar um cliente servidor (por exemplo, [!DNL Insight] ou [!DNL Report]), você deve instalar o certificado digital que autoriza um indivíduo nomeado (por exemplo, Jane Smith) a usar o aplicativo cliente instalado. Se precisar migrar seu aplicativo Adobe para outra máquina ou outro usuário nomeado, você deverá obter um novo certificado do Adobe. Para fazer isso, entre em contato com o Atendimento ao cliente da Adobe.

O aplicativo cliente apresenta esse certificado digital para obter acesso a um componente de servidor. Um administrador do componente de servidor pode restringir o acesso aos recursos do servidor com base no nome comum ou nos valores da unidade organizacional exibidos no certificado do cliente.

Os certificados digitais X.509 instalados com aplicativos Adobe também permitem que os componentes cliente e servidor troquem informações por SSL (Secure Sockets Layer). O SSL protege as transmissões via HTTP usando um sistema de criptografia de chave pública e privada. A implementação do SSL pelo Adobe suporta chaves RSA de 1024 bits e usa um algoritmo de criptografia RC4 de 128 bits.

Além da segurança, os certificados digitais que você instala também funcionam como chaves de licença que permitem executar o software Adobe instalado. Para funcionar corretamente, um certificado digital deve ser bloqueado por nó e atual ou o aplicativo não é start.

## Criptografia de string {#section-8abe6b2d95704d38a04137d5c4602f0b}

Consulte Criptografia [de string](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/string-encryption.md#concept-35da0b53650a4d7e82b240ad27f6d45a) para criptografar senhas.

## Certificados bloqueados por nó {#section-b3dc7dcf2aa3439cbe66b0461b42d485}

Um certificado bloqueado por nó é um certificado digital que foi registrado na máquina em que está instalado. O bloqueio de nó associa permanentemente um certificado a um identificador de nó específico (um valor que identifica exclusivamente uma máquina específica). Para que o nó bloqueie seu certificado, sua máquina deve ter acesso à Internet ao Adobe License Server ou a um servidor proxy que tenha acesso ao License Server.

Se estiver instalando em uma máquina que não pode acessar a Internet, você deverá obter e instalar um certificado especial pré-bloqueado, conforme descrito em [Usando certificados digitais em computadores sem acesso](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)à Internet.

Se você estiver instalando em uma máquina que possa acessar a Internet, seu certificado digital será bloqueado automaticamente no nó na primeira vez que você start seu produto Adobe. Depois de ser bloqueado por nó, o certificado não pode ser usado em qualquer outra máquina. Se precisar migrar seu Adobe para outra máquina, você deverá obter um certificado novo e desbloqueado do Adobe.

## Certificados atuais {#section-15aabaa8625c46edaa7436e1f3fc29c5}

Além de estar bloqueado por nó, um certificado digital deve estar atualizado. Para permanecer atual, seu certificado deve ser revalidado regularmente (geralmente a cada 30 dias, mas pode variar dependendo do acordo com o Adobe). Se o computador tiver acesso à Internet, o processo de revalidação será completamente transparente. Seu produto Adobe se conecta automaticamente ao License Server e revalida o certificado quando necessário. Se o computador não tiver acesso à Internet, será necessário instalar manualmente os certificados atualizados conforme descrito na seção a seguir.

## Usando certificados digitais em máquinas sem acesso à Internet {#section-809366329a7d4e198f95fe06c1f534fa}

Se estiver instalando em uma máquina que não pode acessar a Internet, você deverá solicitar um certificado pré-bloqueado para a instalação do [!DNL Insight Server]. Um certificado pré-bloqueado é um certificado digital que é bloqueado manualmente pelo Adobe para o identificador de nó do computador.

Para solicitar um certificado pré-bloqueado, é necessário enviar o identificador do nó e o número do certificado para o Atendimento ao cliente do Adobe. Para obter o identificador de nó da máquina, entre em contato com o Atendimento ao cliente da Adobe para solicitar o utilitário Adobe Node Identifier. Você também pode obter o identificador do nó a partir do alerta de que o software do Adobe apresenta problemas quando ele tenta se conectar ao License Server e não pode.

Ao receber o certificado pré-bloqueado, instale-o conforme descrito nas duas últimas etapas de Procedimentos [de instalação de certificados](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)digitais. Quando o certificado precisar ser revalidado, você deverá baixar um novo certificado validado do License Server e reinstalá-lo no computador.

## Procedimentos de instalação de certificados digitais {#section-19f31676aad344a98e26e4fca1fad03b}

**Para baixar e instalar o certificado digital**

1. Abra o navegador da Web para [https://aap.adobe.com](https://aap.adobe.com).

   >[!NOTE]
   >
   >Seu navegador pode solicitar que você apresente um certificado digital neste momento. Se isso acontecer, basta clicar **[!UICONTROL Cancel]** para fechar a caixa de diálogo.

1. Na tela de login, digite o **[!UICONTROL Account Name]** e os **[!UICONTROL Password]** que você recebeu do Adobe e clique em **[!UICONTROL login]**.

1. Localize o certificado que foi emitido para o seu certificado [!DNL Insight Server]e clique no ícone associado ao certificado.

   >[!NOTE]
   >
   >Anote o nome comum atribuído a este certificado. Use esse nome em uma etapa posterior.

1. Quando solicitado a salvar o certificado, clique em **[!UICONTROL Save]**. (Observe que o nome do arquivo corresponde ao nome comum associado ao certificado.)
1. Baixe o arquivo para a [!DNL Certificates] pasta no diretório em que você instalou [!DNL Insight Server]. Esta pasta já contém um arquivo de certificado chamado [!DNL trust_ca_cert.pem]. Esse arquivo de certificado deve estar sempre presente.

1. Renomeie o arquivo de certificado baixado para:

[!DNL server_cert.pem]

