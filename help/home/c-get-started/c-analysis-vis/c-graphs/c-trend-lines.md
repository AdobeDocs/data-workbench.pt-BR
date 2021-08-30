---
description: As linhas de tendência permitem sobrepor gráficos para comparar e interpretar dados.
title: Linhas de tendência
uuid: b1d81973-2181-4507-a0a5-adf5eeb9f926
exl-id: 3e7e9218-49b2-4877-a4bd-318b838089e8
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 1%

---

# Linhas de tendência{#trend-lines}

As linhas de tendência permitem sobrepor gráficos para comparar e interpretar dados.

Assim como a visualização de [Gráfico de dispersão](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/c-scat-plots.html), agora é possível definir linhas de tendência em uma visualização de gráfico para exibir a taxa de alteração com base em linhas lineares, exponenciais, de energia ou polinômicas. O recurso Linha de tendência permite sobrepor linhas de tendência em um gráfico, mais comumente em uma dimensão de Tempo.

Por exemplo, nessa comparação de gráfico, podemos ver que as Visitas estão com tendência, mas os Pedidos estão com tendência decrescente.

![](assets/trend_line.png)

Para adicionar uma Linha de Tendência

1. Abra um gráfico e clique com o botão direito do mouse no nome da métrica no canto superior esquerdo.
1. Clique em **[!UICONTROL Trend Lines]** e selecione uma das opções.

   ![](assets/trend_line_graph.png)

   Você pode selecionar a linha de tendência a ser exibida sobre o gráfico como **Linear Simples**, **Exponencial**, **Power** ou **Polynomial**. O polinômio criará uma linha de tendência de regressão polinômica. Linear Simples criará uma linha de tendência como a taxa de alteração ao longo da linha de regressão. Exponencial calcula uma linha de tendência como y = b*exp( a*x ) e Power como y = b*x`<sup>a</sup>`.

   A tendência será calculada e renderizada no gráfico, e uma chamada será aberta exibindo informações detalhadas da equação de tendência.

   ![](assets/trend_line_detail.png)
