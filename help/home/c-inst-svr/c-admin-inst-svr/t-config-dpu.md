---
description: O arquivo de configuração DPU, DPU.cfg, especifica vários parâmetros de desempenho para o servidor Insight.
title: Configurar DPU.cfg
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
exl-id: 55e4ea7f-fee3-4af7-9cbc-d121e79e6ab2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 1%

---

# Configurar DPU.cfg{#configuring-dpu-cfg}

O arquivo de configuração DPU, DPU.cfg, especifica vários parâmetros de desempenho para o servidor Insight.

A forma como você define esses parâmetros depende do tamanho do seu conjunto de dados e de muitos outros fatores. Entre em contato com os Serviços de consultoria da Adobe para obter ajuda com o ajuste do desempenho.

**Frequência recomendada:** somente quando necessário

**Para alterar as configurações de desempenho  [!DNL Insight Server] da DPU**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile], clique na miniatura **[!UICONTROL Servers Manager]** para abrir o espaço de trabalho do Gerenciador de Servidores.
1. Clique com o botão direito do mouse no ícone do [!DNL Insight Server] que deseja configurar e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para visualizar seu conteúdo. O arquivo [!DNL DPU.cfg] está localizado dentro desse diretório.
1. Clique com o botão direito do mouse na marca de seleção na coluna *server name* para [!DNL DPU.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece na coluna [!DNL Temp] para [!DNL DPU.cfg].
1. Clique com o botão direito do mouse na marca de seleção recém-criada na coluna [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Na janela [!DNL DPU.cfg], clique no componente para exibir seu conteúdo.
1. Altere as configurações de desempenho e caminho, conforme necessário. Para obter uma lista dos parâmetros disponíveis neste arquivo, consulte [Configurações de desempenho da DPU](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1).

   >[!NOTE]
   >
   >Entre em contato com o Adobe antes de alterar qualquer parâmetro neste arquivo.

   ![](assets/cfg_DPU_egvalues.png)

1. Salve as alterações no servidor fazendo o seguinte:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. No [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na coluna [!DNL Temp] e selecione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.
