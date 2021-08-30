---
description: O Gráfico de barras na Data Workbench agora inclui uma comparação de regressão para várias métricas em vários gráficos.
title: Gráfico de análise de regressão
uuid: 8512890e-f42b-4dce-826a-2b4bf2a215f4
exl-id: bfc76c4a-edd5-41fe-b875-c199ea3beab5
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 2%

---

# Gráfico de análise de regressão{#regression-analysis-graph}

O Gráfico de barras na Data Workbench agora inclui uma comparação de regressão para várias métricas em vários gráficos.

[Os ](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/graphs/c-graphs.html) gráficos de barras na Data Workbench permitem que você registre métricas em um gráfico para métricas em outro gráfico. Se você tiver vários gráficos, é possível comparar uma métrica (como a variável independente) com um gráfico de avaliação de outras métricas (como variáveis dependentes). Isso permite determinar a força da relação entre uma variável dependente (a métrica estabelecida primeiro) e uma série de outras métricas em alteração (regressões com a métrica dependente estabelecida).

A análise de regressão em uma visualização de gráfico permite que os analistas executem cenários de &quot;What-if&quot;. Por exemplo, se as visitas aumentarem para esse nível, que impacto terá esse aumento na receita?

**Configuração da análise de regressão**

1. Selecione o gráfico como uma métrica dependente para uma comparação de regressão.

   Clique com o botão direito do mouse no gráfico e selecione **Definir como métrica base para regressão**.

   ![](assets/c_graph_regression_1.png)

1. Defina outros gráficos de métricas como variáveis independentes.

   Clique com o botão direito do mouse na métrica e selecione **[!UICONTROL Regress with `<base metric name>`]** para outras métricas.

   ![](assets/c_graph_regression.png)

1. Visualize a regressão clicando com o botão direito do mouse no gráfico para mover a barra para cima e para baixo.

   Se você clicar com o botão direito do mouse no gráfico de um valor específico, poderá ver as relações de regressão para cada métrica com base em valores para cima ou para baixo.

   ![](assets/c_graph_regression_2.png)

   Por exemplo, se minhas Exibições de página diminuírem para 86.041, as outras métricas terão estes valores: Visitas em 12.183 e Visitantes por Visita em 12.028.

   ![](assets/c_graph_regression_3.png)

   Se os valores de Visitantes por Visita aumentarem para 26.141, as outras métricas serão Visitas em 26.560 e Exibições de página em 189.091.
