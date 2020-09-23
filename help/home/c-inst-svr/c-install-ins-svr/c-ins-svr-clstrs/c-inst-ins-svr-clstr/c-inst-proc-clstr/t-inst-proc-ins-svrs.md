---
description: Um Servidor Insight de processamento é idêntico a um Servidor Insight principal, exceto pelo conteúdo de seu diretório Componentes.
solution: Analytics
title: Instalar e configurar servidores Insight de processamento
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---


# Instalar e configurar servidores Insight de processamento{#installing-and-configuring-the-processing-insight-servers}

Um Servidor Insight de processamento é idêntico a um Servidor Insight principal, exceto pelo conteúdo de seu diretório Componentes.

O diretório Componentes em um processamento [!DNL Insight Server] contém um conjunto especial de arquivos que são configurados especificamente para processamento [!DNL Insight Servers]. Esses arquivos são derivados do diretório Componentes para Servidores de Processamento no principal [!DNL Insight Server].

Ao instalar um processamento, faça o seguinte [!DNL Insight Server]para configurar seu diretório Componentes:

1. Exclua o diretório Componentes original no processamento [!DNL Insight Server].
1. Renomeie o diretório Componentes para Servidores de Processamento para Componentes.
1. Modifique o diretório [!DNL Synchronize.cfg] no diretório Componentes para apontar para o principal [!DNL Insight Server].

**Para instalar e configurar um processamento[!DNL Insight Server]**

1. Instale os arquivos de [!DNL Insight Server] programa conforme descrito em [Instalação dos arquivos](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)de Programa do Insight Server. Certifique-se de duplicado da estrutura de diretório usada no principal [!DNL Insight Server]. Por exemplo, se [!DNL Insight Server] estiver instalado [!DNL C:\Adobe\Server] no principal [!DNL Insight Server], você também deverá instalá-lo [!DNL C:\Adobe\Server] no processamento [!DNL Insight Servers] .
1. Instale o certificado digital emitido pelo Adobe para este processamento em particular [!DNL Insight Server]. Consulte [Download e instalação de certificados](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) digitais para obter instruções.
1. Usando o Windows Explorer, faça o seguinte no processamento [!DNL Insight Server]:

   1. Delete the **[!UICONTROL Components]** folder.
   1. Renomeie a [!DNL Components for Processing Servers] pasta como Componentes.

1. Usando um editor de texto como o Bloco de notas, abra o [!DNL Synchronize.cfg] arquivo no diretório Componentes no processamento [!DNL Insight Server].
1. Adicione o endereço IP do principal (principal) [!DNL Insight Server] à segunda linha deste arquivo, como mostrado no seguinte fragmento de arquivo. Não edite mais nada neste arquivo.

   ```
   component = SynchronizeComponent:
     Cluster Primary Server Address = string: PrimaryIPAddress
     Directories = vector: 7 items
       0 = SynchronizeDir:
         Local Path = string: Profiles\\
         Remote URI = string: /Profiles/
       1 = SynchronizeDir:
         Local Path = string: Lookups\\
         Remote URI = string: /Lookups/
       . . .
   ```

1. Salve o arquivo.
1. Start o [!DNL Insight Server] conforme descrito em [Registrando o Insight Server como um Serviço](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)do Windows.

   Agora você concluiu a instalação do seu [!DNL Insight Server] cluster. Em seguida, configure o perfil do conjunto de dados para ser executado no cluster, conforme descrito na seção a seguir.

