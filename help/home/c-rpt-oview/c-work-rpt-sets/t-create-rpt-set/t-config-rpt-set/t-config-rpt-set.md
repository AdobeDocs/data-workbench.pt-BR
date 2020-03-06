---
description: Depois de criar e salvar os espaços de trabalho na pasta do conjunto de relatórios, você deve criar um novo arquivo Report.cfg.
solution: Analytics
title: Configurar o conjunto de relatórios
topic: Data workbench
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurar o conjunto de relatórios{#configure-the-report-set}

Depois de criar e salvar os espaços de trabalho na pasta do conjunto de relatórios, você deve criar um novo arquivo Report.cfg.

Você deve especificar no [!DNL Report.cfg] arquivo para o conjunto de relatórios quando e como os relatórios devem ser gerados e distribuídos.

**Para criar um novo Report.cfg**

1. Na análise de big data, abra o arquivo clicando com o botão direito do mouse [!DNL Profile Manager] em uma área de trabalho e clicando em **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**.
1. Click **[!UICONTROL Reports]** to open the [!DNL Reports] folder.
1. Clique na pasta do conjunto de relatórios.
1. Na [!DNL User] coluna da pasta do conjunto de relatórios, clique com o botão direito do mouse e selecione **[!UICONTROL Create]** > **[!UICONTROL Report]**. Um novo [!DNL Report.cfg] arquivo é exibido na [!DNL File]coluna.
1. Na [!DNL User] coluna do novo [!DNL Report.cfg] arquivo, clique com o botão direito do mouse na marca de seleção do [!DNL Report.cfg] arquivo e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   ![Informações da etapa](assets/cfg_reportcfg.png)

1. Edite os parâmetros de configuração conforme desejado. Para obter informações sobre esses parâmetros, consulte Parâmetros [](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)Report.cfg.

   >[!NOTE]
   >
   >A amostra [!DNL Report.cfg] mostrada neste exemplo contém apenas os parâmetros incluídos no [!DNL Report.cfg] arquivo por padrão. Se você precisar adicionar outros parâmetros a um [!DNL Report.cfg] arquivo, é necessário fazer isso usando um editor de texto. Para obter etapas para fazer isso, consulte [Editando arquivos](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887)Report.cfg existentes.

1. Salve o arquivo clicando com o botão direito do mouse **[!UICONTROL Report.cfg (modified)]** na parte superior do arquivo e clicando em **[!UICONTROL Salvar como Relatórios\]***&lt;**[!UICONTROL ReportSetName]**>***[!UICONTROL \Report.cfg]**.
1. Feche o arquivo.
1. No [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção na [!DNL User] coluna do novo [!DNL Report.cfg] arquivo e selecione **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.
