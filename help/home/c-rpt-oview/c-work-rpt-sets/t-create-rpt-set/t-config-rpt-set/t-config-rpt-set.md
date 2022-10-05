---
description: Depois de criar e salvar os espaços de trabalho na pasta do conjunto de relatórios, você deve criar um novo arquivo Report.cfg .
title: Configurar o conjunto de relatórios
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
exl-id: 780e6bb1-b332-4984-b132-df11d95b592a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Configurar o conjunto de relatórios{#configure-the-report-set}

{{eol}}

Depois de criar e salvar os espaços de trabalho na pasta do conjunto de relatórios, você deve criar um novo arquivo Report.cfg .

Você deve especificar na variável [!DNL Report.cfg] para o conjunto de relatórios quando e como os relatórios devem ser gerados e distribuídos.

**Para criar um novo Report.cfg**

1. No Data Workbench, abra o [!DNL Profile Manager] clicando com o botão direito do mouse em um espaço de trabalho e clicando em **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**.
1. Clique em **[!UICONTROL Reports]** para abrir o [!DNL Reports] pasta.
1. Clique na pasta do seu conjunto de relatórios.
1. No [!DNL User] para sua pasta de conjunto de relatórios, clique com o botão direito do mouse e selecione **[!UICONTROL Create]** > **[!UICONTROL Report]**. Um novo [!DNL Report.cfg] o arquivo aparece no [!DNL File]coluna.
1. No [!DNL User] coluna para o novo [!DNL Report.cfg] , clique com o botão direito do mouse na marca de seleção do [!DNL Report.cfg] e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   ![Informações da etapa](assets/cfg_reportcfg.png)

1. Edite os parâmetros de configuração conforme desejado. Para obter informações sobre esses parâmetros, consulte [Parâmetros do Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

   >[!NOTE]
   >
   >A amostra [!DNL Report.cfg] mostrado neste exemplo contém apenas os parâmetros incluídos no [!DNL Report.cfg] por padrão. Se você precisar adicionar mais parâmetros a um [!DNL Report.cfg] , faça isso usando um editor de texto. Para obter etapas para fazer isso, consulte [Editar arquivos Report.cfg existentes](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

1. Salve o arquivo clicando com o botão direito do mouse **[!UICONTROL Report.cfg (modified)]** na parte superior do arquivo e clicando em **[!UICONTROL Save as Reports\]***&lt; **[!UICONTROL ReportSetName]**>***[!UICONTROL \Report.cfg]**.
1. Feche o arquivo .
1. No [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção no [!DNL User] coluna para o novo [!DNL Report.cfg] e selecione **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.
