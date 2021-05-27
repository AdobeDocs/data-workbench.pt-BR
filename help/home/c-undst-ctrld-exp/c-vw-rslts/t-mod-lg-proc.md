---
description: Você deve adicionar o campo x-Experiment ao arquivo Log Processing.cfg , que é usado para criar uma dimensão estendida.
solution: Analytics,Analytics
title: Modificar o Log Processing.cfg
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
exl-id: 23c7873f-8ffd-422f-896b-d6c7e16aabbd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---

# Modificar o Log Processing.cfg{#modifying-log-processing-cfg}

Você deve adicionar o campo x-Experiment ao arquivo Log Processing.cfg , que é usado para criar uma dimensão estendida.

Consulte [Modificando Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6).

**Para modificar o Log Processing.cfg**

1. Em [!DNL Insight], abra o [!DNL Profile Manager] clicando com o botão direito do mouse em um espaço de trabalho e clicando em **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**, ou abrindo o espaço de trabalho Gerenciamento de perfil na guia [!DNL Admin].
1. No [!DNL Profile Manager], clique em **[!UICONTROL Dataset]** para mostrar seu conteúdo.
1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL Log Processing.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece na coluna [!DNL User].
1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. A janela [!DNL Log Processing.cfg] é exibida.
1. Clique em **[!UICONTROL Fields]** para mostrar seu conteúdo.
1. Clique com o botão direito do mouse no último campo da lista atual e clique em **[!UICONTROL Add new]** > **[!UICONTROL Field]**.
1. Digite x para experimentar no campo recém-criado, como mostrado no exemplo a seguir:

   ![Informações da etapa](assets/logprocessing.png)

1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
1. No [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção de [!DNL Log Processing.cfg] na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]*** para salvar as alterações feitas localmente no perfil de trabalho.

   >[!NOTE]
   >
   >O conjunto de dados inicia o reprocessamento imediatamente.

   Para obter mais informações sobre Processamento de log e Campos, consulte o *Guia de configuração do conjunto de dados*.
