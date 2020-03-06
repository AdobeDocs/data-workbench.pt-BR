---
description: Etapas para alterar a visualização padrão.
solution: Analytics
title: Configurar a interface do esquema do conjunto de dados
topic: Data workbench
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# Configurar a interface do esquema do conjunto de dados{#configure-the-dataset-schema-interface}

Etapas para alterar a visualização padrão.

Você pode controlar que tipo de visualização é exibido ao clicar em um nome de dimensão em uma [!DNL Dataset Schema Interface] adicionando arquivos ao perfil Perfis\*nome do perfil*\Context\Dimension Legend folder of the Data Workbench server installation folder. O [!DNL Default.1d] arquivo desta pasta controla o tipo de visualização padrão para todas as dimensões. Ao adicionar um arquivo name *.1d de* dimensão (como [!DNL Hour.1d]) a essa pasta, você pode controlar a visualização padrão dessa dimensão específica.

Para obter mais informações sobre [!DNL Dataset Schema Interfaces], consulte [A Interface](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175)do Esquema de Conjunto de Dados.

**Alteração da visualização padrão**

1. Em qualquer espaço de trabalho, crie uma visualização que contenha os dados que você deseja que apareçam na nova visualização padrão.

   Por exemplo, se você deseja que a dimensão seja exibida em um gráfico de barras, crie uma visualização em gráfico de barras que mostre a métrica e a dimensão desejadas.

1. Clique com o botão direito do mouse na borda superior da janela de chamada e clique em **[!UICONTROL Save]**.
1. Na [!DNL Save] janela, clique em ![](assets/btn_folder_up.png), clique duas vezes **[!UICONTROL Context]** e clique duas vezes **[!UICONTROL Dimension Legend]**.
1. No [!DNL File Name] campo, digite o nome da dimensão.

   The name of the [!DNL .1d] file must match the name of the dimension exactly. Por exemplo, [!DNL Hour.1d].

1. Altere a extensão do arquivo para &quot;1d&quot; e clique em **[!UICONTROL Save]**.

   O arquivo é salvo no nome do perfil de trabalho do usuário\*\Context\Dimension Legend folder.

   Na próxima vez que você clicar nessa dimensão em uma visualização [!DNL Dataset Schema Interface], a visualização especificada será exibida.

1. (Opcional) Para disponibilizar essa alteração para todos os usuários do perfil de trabalho:

   1. In the [!DNL Profile Manager], click **[!UICONTROL Context]**, then click **[!UICONTROL Dimension Legend]**.

   1. Clique com o botão direito do mouse na marca de seleção ao lado do nome do arquivo da nova chamada na [!DNL User] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

