---
description: A visualização de Tabela de associação permite associar métricas com métricas, dimensões e elementos de dimensão usando o algoritmo V de Cramer.
title: Visualização de tabela de associação
uuid: 4563c336-3377-4929-8694-8c0d00866825
exl-id: 3fc2c025-d369-45ed-8c9e-eb4a0ac412b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 2%

---

# Visualização de tabela de associação{#association-table-visualization}

{{eol}}

A visualização de Tabela de associação permite associar métricas com métricas, dimensões e elementos de dimensão usando o algoritmo V de Cramer.

A Tabela de Associação compara valores com o cálculo V de Cramer em vez de usar o coeficiente de correlação de Pearson, como usado na variável [Matriz de correlação](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html) e [Correlação de corda](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/c-chord-visualization.html) visualizações (elas podem apenas comparar métricas, enquanto a Tabela de associação e [Corda de Associação](../../../home/c-get-started/c-analysis-vis/associations-chord.md#concept-51d0bda998474dd5946cc2a9b8393445) O pode comparar métricas, dimensões e elementos.

## Criar uma tabela de associação {#section-87ed12ccc1af4196a1b6534e621c4cbb}

A Tabela de associação compara métricas sobre uma dimensão contável ou não contável. A tabela pode ser modificada para realçar associações dentro da visualização por meio da separação de cores ou para renderizá-la como um mapa de texto, mapa de calor ou ambos.

1. Abra uma Tabela de Associação.

   Clique com o botão direito do mouse em [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Association Table].

   ![](assets/association_table.png)

1. Selecione uma dimensão estendida: uma dimensão de Clickthrough, Ocorrência, Produto, Visita ou Visitante. Uma Tabela de associação será aberta com a dimensão estendida identificada no canto e sua métrica associada colocada na linha e na coluna.

   ![](assets/association_table1.png)

   A Tabela de associações usa o V de Cramer como uma correlação simétrica, resultando em métricas, dimensões e valores de elementos selecionados refletidos nas colunas e linhas de uma Tabela de associação. Por exemplo, selecionar a variável **Produto** a dimensão estendida usa a variável **[!UICONTROL Visits]** métrica como a métrica associada na linha e na coluna da tabela, resultando em uma comparação perfeita, mas inútil (1,00), pois os valores comparados são idênticos.

1. Adicione mais valores à Tabela de Associação.

   Clique com o botão direito do mouse em uma coluna ou linha e selecione **Adicionar métrica** ou **Adicionar Dimension**. Também é possível arrastar métricas e dimensões de uma **Localizador** painel. Os elementos de Dimension também podem ser arrastados e soltos de uma tabela aberta para a visualização da tabela.

   ![](assets/association_table2.png)

   >[!NOTE]
   >
   >Há um limite de dez linhas e colunas permitidas na Tabela de Associação.
