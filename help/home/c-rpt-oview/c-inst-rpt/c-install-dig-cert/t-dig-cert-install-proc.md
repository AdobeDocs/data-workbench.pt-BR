---
description: Etapas para baixar e instalar o certificado digital.
title: Procedimentos de instalação de certificados digitais
uuid: 14749a68-96cb-4cf4-819e-07df065e4016
exl-id: a8ae8d23-8db8-44d9-8c45-e552da81c384
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 33%

---

# Procedimentos de instalação de certificados digitais{#digital-certificate-installation-procedures}

{{eol}}

Etapas para baixar e instalar o certificado digital.

1. Abra o navegador em [https://aap.adobe.com](https://aap.adobe.com).

   >[!NOTE]
   >
   >O navegador pode solicitar que você apresente um certificado digital neste momento. Se isso acontecer, basta clicar em **[!UICONTROL Cancel]** para fechar a caixa de diálogo.

1. Na tela de logon, digite o Nome da conta e a Senha que você recebeu do Adobe e clique em **[!UICONTROL login]**.
1. Localize o certificado emitido para a sua instância de [!DNL Report] Servidor (*Seu nome*.pem) e clique no link ![](assets/btn_save_certificatedownload.PNG) ícone associado a esse certificado.
1. Quando solicitado a salvar o certificado, clique em **[!UICONTROL Save]**.
1. Baixe o arquivo para a pasta Certificados no diretório em que você instalou [!DNL Report Server].

   Esta pasta já contém um arquivo de certificado chamado [!DNL trust_ca_cert.pem]. Ambos os arquivos de certificado devem estar sempre presentes para [!DNL Report] Servidor para funcionar.
