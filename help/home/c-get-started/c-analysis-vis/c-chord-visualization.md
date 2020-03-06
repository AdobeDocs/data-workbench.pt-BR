---
description: A visualização de Corda permite mostrar a proporção e a correlação entre as métricas, exibindo acordes maiores como uma indicação de uma correlação mais forte.
title: Exibição de corda
uuid: 3f322f58-f8f5-4d91-bdf8-4b5f9d7fb072
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Exibição de corda{#chord-visualization}

A visualização de Corda permite mostrar a proporção e a correlação entre as métricas, exibindo acordes maiores como uma indicação de uma correlação mais forte.

A visualização de Corda permite que você veja identificar correlações entre métricas, permitindo que você adicione e avalie facilmente possíveis correlações. Ele também fornece outra exibição em qualquer Matriz de [correlação](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html)previamente criada. Usando a visualização de Corda, não é possível identificar uma correlação positiva ou negativa entre as métricas — somente a existência de uma correlação. Em certos casos, determinar uma relação direta ou inversa pode ser identificado aplicando métricas de contador.

1. **Abra a **[!UICONTROL Chord]**visualização**.

   No espaço de trabalho, clique com o botão direito do mouse [!DNL Visualization > Predictive Analytics > Chord].

1. **Selecione uma Dimensão no menu**.

   Uma visualização em branco será aberta permitindo que você selecione uma dimensão. O nome da dimensão aparecerá na parte superior da visualização do acorde em branco.

   >[!NOTE]
   >
   >Se você já tiver uma Matriz de correlação aberta no espaço de trabalho, também poderá renderizá-la como uma visualização de Corda.

1. **Escolha métricas para correlacionar**.

   Arraste as métricas do **[!UICONTROL Finder]** e clique **[!UICONTROL Ctrl-Alt]** para arrastar as métricas da tabela para o gráfico. Depois que duas ou mais métricas forem selecionadas, o gráfico será atualizado automaticamente e começará a exibir os dados de correlação. Continue adicionando métricas conforme necessário para correlacionar pontos de dados.

   ![](assets/chord_drag_metric.png)

   A visualização de Corda exibe a proporção do todo representado pela área de cada segmento. Continue a adicionar métricas conforme necessário para identificar e investigar relações significativas.

   ![](assets/chord_selected.png)

1. **Visualize a visualização** de Corda.

   Passe o cursor do mouse sobre cada métrica na visualização para ver os relacionamentos. No exemplo, você pode ver uma correlação entre Unidades e a maioria das outras métricas (exceto a métrica Duração **da** visita).

   ![](assets/chord_visualization_1.png)

   Ao passar o mouse sobre a métrica Duração **da** visita na visualização de Corda, você pode ver que há uma correlação muito pequena ou no máximo fraca entre todas as outras métricas.

   ![](assets/chord_visualization_2.png)

1. **Alterar Configurações.** Clique com o botão direito do mouse na visualização de Corda para abrir um menu para alterar a dimensão, exibir as dimensões como números absolutos ou percentuais, remover a métrica selecionada ou todas as métricas, editar cores e detalhes e exportar valores para uma Matriz de correlação.

   ![](assets/chord_menu.png)

