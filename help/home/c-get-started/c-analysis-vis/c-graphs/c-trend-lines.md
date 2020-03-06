---
description: As linhas de tendência permitem sobrepor gráficos para comparar e interpretar dados.
title: Linhas de tendência
uuid: b1d81973-2181-4507-a0a5-adf5eeb9f926
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Linhas de tendência{#trend-lines}

As linhas de tendência permitem sobrepor gráficos para comparar e interpretar dados.

Assim como a visualização do Gráfico de [dispersão](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/c-scat-plots.html) , agora é possível definir linhas de tendência em uma visualização de gráfico para exibir a taxa de alteração com base em linhas lineares, exponenciais, de energia ou polinomiais. O recurso Linha de tendência permite sobrepor linhas de tendência em um gráfico, mais comumente em uma dimensão de Tempo.

Por exemplo, nesta comparação de gráfico, podemos ver que as Visitas estão com tendência para cima, mas os Pedidos estão com tendência para baixo.

![](assets/trend_line.png)

Para adicionar uma Linha de Tendência

1. Abra um gráfico e clique com o botão direito do mouse no nome da métrica no canto superior esquerdo.
1. Clique **[!UICONTROL Trend Lines]** e selecione uma das opções.

   ![](assets/trend_line_graph.png)

   Você pode selecionar a linha de tendência para aparecer sobre o gráfico como Linear **** Simples, **Exponencial**, **Energia** ou **Polinomial**. O polinomial criará uma linha de tendência de regressão polinomial. Linear simples criará uma linha de tendência como a taxa de mudança ao longo da linha de regressão. Exponencial calcula uma linha de tendência como y = b*exp( a*x ) e Power como y = b*x`<sup>a</sup>`.

   A tendência será calculada e renderizada no gráfico, e um texto explicativo abrirá exibindo informações detalhadas da equação de tendência.

   ![](assets/trend_line_detail.png)

