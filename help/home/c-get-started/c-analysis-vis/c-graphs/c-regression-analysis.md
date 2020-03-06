---
description: O Gráfico de barras na Análise de big data agora inclui uma comparação de regressão para várias métricas em vários gráficos.
title: Gráfico de análise de regressão
uuid: 8512890e-f42b-4dce-826a-2b4bf2a215f4
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Regression Analysis Graph{#regression-analysis-graph}

O Gráfico de barras na Análise de big data agora inclui uma comparação de regressão para várias métricas em vários gráficos.

[Os gráficos](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/graphs/c-graphs.html) de barras na Análise de big data permitem que você registre as métricas em um gráfico para as métricas em outro gráfico. Se você tiver vários gráficos, é possível comparar uma métrica (como a variável independente) a um gráfico que avalia outras métricas (como variáveis dependentes). Isso permite determinar a intensidade da relação entre uma variável dependente (a métrica estabelecida primeiro) e uma série de outras métricas em alteração (regressões com a métrica dependente estabelecida).

A análise de regressão em uma visualização de gráfico permite que os analistas executem cenários de &quot;What-if&quot;. Por exemplo, se as visitas aumentarem para esse nível, que impacto terá esse aumento na receita?

**Configuração da Análise de Regressão**

1. Selecione o gráfico como uma métrica dependente para uma comparação de regressão.

   Clique com o botão direito do mouse no gráfico e selecione **Definir como métrica base para regressão**.

   ![](assets/c_graph_regression_1.png)

1. Defina outros gráficos de métricas como variáveis independentes.

   Clique com o botão direito do mouse na métrica e selecione **[!UICONTROL Regress with `<base metric name>`]** para outras métricas.

   ![](assets/c_graph_regression.png)

1. Visualize a regressão clicando com o botão direito do mouse no gráfico para mover a barra para cima e para baixo.

   Se você clicar com o botão direito do mouse no gráfico para obter um valor específico, poderá ver as taxas de regressão para cada métrica com base em valores para cima ou para baixo.

   ![](assets/c_graph_regression_2.png)

   Por exemplo, se minhas Exibições de página diminuírem para 86.041, as outras métricas terão estes valores: Visitas em 12.183 e Visitantes por Visita em 12.028.

   ![](assets/c_graph_regression_3.png)

   Se os valores de Visitantes por Visitas aumentarem para 26.141, então as outras métricas serão Visitas em 26.560 e Exibições de página em 189.091.

