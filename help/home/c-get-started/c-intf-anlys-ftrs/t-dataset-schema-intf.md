---
description: Etapas para alterar a visualização padrão.
title: Configurar a interface do esquema do conjunto de dados
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
exl-id: 0227663f-4789-4780-b753-d0deb35f6144
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 4%

---

# Configurar a interface do esquema do conjunto de dados{#configure-the-dataset-schema-interface}

Etapas para alterar a visualização padrão.

Você pode controlar qual tipo de visualização é exibido ao clicar em um nome de dimensão em um [!DNL Dataset Schema Interface] adicionando arquivos ao nome do perfil\*\Context\Dimension Legend folder of the Data Workbench server installation folder. O arquivo [!DNL Default.1d] nessa pasta controla o tipo de visualização padrão para todas as dimensões. Ao adicionar um arquivo *dimension name*.1d (como [!DNL Hour.1d]) a essa pasta, é possível controlar a visualização padrão dessa dimensão específica.

Para obter mais informações sobre [!DNL Dataset Schema Interfaces], consulte [A interface do esquema do conjunto de dados](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175).

**Para alterar a visualização padrão**

1. Em qualquer espaço de trabalho, crie uma visualização contendo os dados que você deseja exibir na nova visualização padrão.

   Por exemplo, se você quiser que a dimensão seja exibida em um gráfico de barras, crie uma visualização de gráfico de barras que mostre a métrica e a dimensão desejadas.

1. Clique com o botão direito do mouse na borda superior da janela de chamada e clique em **[!UICONTROL Save]**.
1. Na janela [!DNL Save], clique em ![](assets/btn_folder_up.png), clique duas vezes em **[!UICONTROL Context]** e clique duas vezes em **[!UICONTROL Dimension Legend]**.
1. No campo [!DNL File Name], digite o nome da dimensão.

   O nome do arquivo [!DNL .1d] deve corresponder exatamente ao nome da dimensão. Por exemplo, [!DNL Hour.1d].

1. Altere a extensão do arquivo para &quot;1d&quot; e clique em **[!UICONTROL Save]**.

   O arquivo é salvo no User\*nome do perfil de trabalho*\Context\Dimension Legend folder.

   Na próxima vez que você clicar nessa dimensão em um [!DNL Dataset Schema Interface], a visualização especificada será exibida.

1. (Opcional) Para disponibilizar essa alteração para todos os usuários do perfil de trabalho:

   1. No [!DNL Profile Manager], clique em **[!UICONTROL Context]** e em **[!UICONTROL Dimension Legend]**.

   1. Clique com o botão direito do mouse na marca de seleção ao lado do nome do arquivo da nova chamada na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.
