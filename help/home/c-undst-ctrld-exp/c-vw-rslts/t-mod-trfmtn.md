---
description: Agora que o campo x-Experiment está disponível, você deve criar uma dimensão estendida para incluir o campo x-Experiment em seu conjunto de dados, o que permite visualizar seus resultados no Insight.
solution: Analytics
title: Modificar Transformation.cfg
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
exl-id: a9c89789-8290-4a24-91c1-ca1c5b7b437a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---

# Modificar Transformation.cfg{#modifying-transformation-cfg}

{{eol}}

Agora que o campo x-Experiment está disponível, você deve criar uma dimensão estendida para incluir o campo x-Experiment em seu conjunto de dados, o que permite visualizar seus resultados no Insight.

Para fazer isso, é necessário adicionar uma nova dimensão ao [!DNL Transformation.cfg] arquivo.

Se você planeja executar vários experimentos, também deve adicionar uma nova transformação de Split à [!DNL Transformation.cfg] arquivo. Essa transformação Split separa os diferentes nomes de experimento e grupo, de modo que as informações sejam mais fáceis de interpretar. Para evitar o reprocessamento de seus dados novamente se precisar adicionar experimentos adicionais em uma data posterior, o Adobe recomenda adicionar a transformação Split, mesmo que não esteja planejando executar vários experimentos no momento.

O procedimento a seguir inclui a criação da nova transformação Split e da dimensão estendida. Se não quiser adicionar a transformação Split, ignore as etapas 5 a 7.

**Para modificar o Transformation.cfg**

1. Em [!DNL Insight], abra o [!DNL Profile Manager] clicando com o botão direito do mouse em um espaço de trabalho e clicando em **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** ou abrindo a área de trabalho Gerenciamento de perfil no [!DNL Admin] guia .
1. No [!DNL Profile Manager], clique em **[!UICONTROL Dataset]** para mostrar seu conteúdo.
1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL Transformation.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece no [!DNL User] coluna.
1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. O [!DNL Transformation.cfg] será exibida.
1. Clique em **[!UICONTROL Transformation]** para mostrar seu conteúdo.
1. Clique com o botão direito do mouse **[!UICONTROL Transformations]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Split]**.
1. Conclua a nova divisão em transformação de vírgula, conforme mostrado no exemplo a seguir:

   ![Informações da etapa](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >Você pode inserir qualquer valor no campo Nome .

1. Clique com o botão direito do mouse **[!UICONTROL Extended Dimensions]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**.
1. Conclua a nova dimensão conforme mostrado no exemplo a seguir:

   ![Informações da etapa](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* Você pode inserir qualquer valor no campo Nome .
   >* Se você não tiver incluído a transformação Split, deverá digitar &quot;x-Experiment&quot; no [!DNL Input] campo.


1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
1. No [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção de [!DNL Transformation.cfg] no [!DNL User] e, em seguida, clique em **[!UICONTROL Save to]** > **[!UICONTROL profile name]** para salvar as alterações feitas localmente no perfil de trabalho.

   >[!NOTE]
   >
   >O conjunto de dados começa a retransformar imediatamente.

   Para obter mais informações sobre [!DNL Transformation.cfg] e dimensões estendidas, consulte a *Guia de configuração do conjunto de dados*.
