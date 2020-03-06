---
description: Etapas para classificar dados.
solution: Analytics
title: Classificar dados em uma tabela
topic: Data workbench
uuid: 66869478-922d-41e1-915d-3ed7bff3b08d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Classificar dados em uma tabela{#sort-data-in-a-table}

Etapas para classificar dados.

Se a tabela tiver apenas uma dimensão, basta clicar no rótulo da métrica na qual deseja que os dados sejam classificados.

1. Clique com o botão direito do mouse em um elemento ou no rótulo da dimensão que deseja classificar e clique em **[!UICONTROL Sort]**.

   ![](assets/mnu_Table_Sort.png)

1. Clique em uma das seguintes opções:

   * **[!UICONTROL By ordinal]** para classificar os elementos de acordo com a ordem natural dos elementos. Por exemplo, os elementos da dimensão Hora são exibidos em ordem cronológica. Se a dimensão não tiver ordem natural, como com referenciador ou URI, a ordem de classificação não será útil, portanto, você deve selecionar para classificar alfabeticamente ou por métrica.
   * **[!UICONTROL Alphabetically]** para classificar a dimensão alfabeticamente por nome de elemento.
   * **[!UICONTROL By metric]** para selecionar uma métrica pela qual deseja que os dados sejam classificados. Por exemplo, você pode classificar a dimensão Referenciador pela métrica Sessões para ver quais referenciadores contribuem com mais sessões no site.

      Quando você classifica por uma métrica, por padrão, a ordem na tabela corresponde aos valores da métrica, conforme afetado pela seleção no momento. Se posteriormente você alterar a seleção, a ordem classificada não será alterada a partir da ordem original, a menos que a dimensão seja reordenada ou que você ative a Seleção dinâmica. Quando você clica em **[!UICONTROL Sort]** > **[!UICONTROL Dynamic Selection]**, a tabela é reordenada sempre que você altera a seleção.
   Para classificar por uma métrica existente na tabela, clique no rótulo da métrica.

1. (Opcional) Para escolher se deseja classificar em ordem crescente ou decrescente, clique com o botão direito do mouse em um elemento ou no rótulo da dimensão que deseja classificar e clique em **[!UICONTROL Sort]** > **[!UICONTROL Order]** > **[!UICONTROL Ascending]** ou **[!UICONTROL Sort]** > **[!UICONTROL Order]** > **[!UICONTROL Descending]**.

   Se a tabela tiver apenas uma dimensão, basta clicar no rótulo da métrica para reverter a ordem de classificação. Clicar no rótulo novamente reverte a ordem de classificação.

