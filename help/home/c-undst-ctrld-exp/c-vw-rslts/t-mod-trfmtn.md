---
description: Agora que o campo x-experience está disponível, você deve criar uma dimensão estendida para incluir o campo x-experience no conjunto de dados, o que permite que você visualização seus resultados no Insight.
solution: Analytics,Analytics
title: Modificar Transformation.cfg
topic: Data workbench
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---


# Modificar Transformation.cfg{#modifying-transformation-cfg}

Agora que o campo x-experience está disponível, você deve criar uma dimensão estendida para incluir o campo x-experience no conjunto de dados, o que permite que você visualização seus resultados no Insight.

Para isso, é necessário adicionar uma nova dimensão ao [!DNL Transformation.cfg] arquivo.

Se você planeja executar vários experimentos, também deve adicionar uma nova transformação Dividir ao [!DNL Transformation.cfg] arquivo. Essa transformação de Divisão separa os diferentes nomes de experimento e grupo para que as informações sejam mais fáceis de interpretar. Para evitar o reprocessamento de seus dados novamente se você precisar adicionar experimentos adicionais em uma data posterior, o Adobe recomenda que você adicione a transformação Dividir mesmo que não esteja planejando executar vários experimentos.

O procedimento a seguir inclui a criação da nova transformação Dividir e da dimensão estendida. Se você não quiser adicionar a transformação Dividir, basta pular as etapas de 5 a 7.

**Para modificar Transformation.cfg**

1. Em [!DNL Insight], abra o arquivo [!DNL Profile Manager] clicando com o botão direito do mouse em um espaço de trabalho e clicando em **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**, ou abrindo o espaço de trabalho Gerenciamento de Perfis na [!DNL Admin] guia.
1. No [!DNL Profile Manager], clique em **[!UICONTROL Dataset]** para mostrar seu conteúdo.
1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL Transformation.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção para este arquivo é exibida na [!DNL User] coluna.
1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. A [!DNL Transformation.cfg] janela é exibida.
1. Clique em **[!UICONTROL Transformation]** para mostrar seu conteúdo.
1. Clique com o botão direito do mouse **[!UICONTROL Transformations]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Split]**.
1. Conclua a nova divisão na transformação de vírgula, como mostrado no exemplo a seguir:

   ![Informações da etapa](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >É possível inserir qualquer valor no campo Nome.

1. Clique com o botão direito do mouse **[!UICONTROL Extended Dimensions]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**.
1. Complete a nova dimensão conforme mostrado no exemplo a seguir:

   ![Informações da etapa](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* É possível inserir qualquer valor no campo Nome.
   >* Se você não incluiu a transformação Dividir, digite &quot;x-experience&quot; no [!DNL Input] campo.


1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
1. Na [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção para [!DNL Transformation.cfg] na [!DNL User] coluna e, em seguida, clique em **[!UICONTROL Save to]** > **[!UICONTROL profile name]** para salvar as alterações feitas localmente no perfil em funcionamento.

   >[!NOTE]
   >
   >O conjunto de dados começa a ser retransformado imediatamente.

   Para obter mais informações sobre [!DNL Transformation.cfg] e dimensões estendidas, consulte o Guia *de configuração de* conjuntos de dados.
