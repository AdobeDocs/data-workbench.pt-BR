---
description: O arquivo de configuração DPU, DPU.cfg, especifica vários parâmetros de desempenho para o Insight Server.
solution: Analytics
title: Configurar DPU.cfg
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 1%

---


# Configurar DPU.cfg{#configuring-dpu-cfg}

O arquivo de configuração DPU, DPU.cfg, especifica vários parâmetros de desempenho para o Insight Server.

A forma como você define esses parâmetros depende do tamanho do conjunto de dados e de muitos outros fatores. Entre em contato com os Serviços de consultoria da Adobe para obter ajuda com o ajuste de desempenho.

**Frequência recomendada:** Somente quando necessário

**Para alterar as configurações de desempenho da[!DNL Insight Server]DPU**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a área de trabalho do Gerenciador de servidores.
1. Clique com o botão direito do mouse no ícone do [!DNL Insight Server] que deseja configurar e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique **[!UICONTROL Components]** para visualização do conteúdo. O [!DNL DPU.cfg] arquivo está localizado dentro deste diretório.
1. Clique com o botão direito do mouse na marca de seleção na coluna de nome *do* servidor para [!DNL DPU.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção é exibida na [!DNL Temp] coluna para [!DNL DPU.cfg].
1. Clique com o botão direito do mouse na marca de seleção recém-criada na [!DNL Temp] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Na [!DNL DPU.cfg] janela, clique no componente para visualização de seu conteúdo.
1. Altere as configurações de desempenho e caminho, conforme necessário. Para obter uma lista dos parâmetros disponíveis neste arquivo, consulte Configurações [de desempenho da](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1)DPU.

   >[!NOTE]
   >
   >Entre em contato com a Adobe antes de alterar qualquer um dos parâmetros deste arquivo.

   ![](assets/cfg_DPU_egvalues.png)

1. Salve as alterações no servidor da seguinte maneira:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Na [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL Temp] coluna e selecione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

