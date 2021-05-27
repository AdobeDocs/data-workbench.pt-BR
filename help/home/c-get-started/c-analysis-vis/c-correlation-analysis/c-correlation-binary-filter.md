---
description: Um Filtro binário na Matriz de correlação permite que você restrinja valores para uma ou ambas as métricas correlacionadas para concentrar melhor a comparação.
title: Filtro binário na matriz de correlação
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
exl-id: e693fc72-5697-4c47-a498-e0d4d875c688
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 5%

---

# Filtro binário na matriz de correlação{#binary-filter-in-the-correlation-matrix}

Um Filtro binário na Matriz de correlação permite que você restrinja valores para uma ou ambas as métricas correlacionadas para concentrar melhor a comparação.

Para definir um filtro binário em uma Matriz de correlação:

1. Na Matriz de correlação, clique com o botão direito do mouse em um nome de métrica.
1. Selecione **Editar Detalhes de Métrica**.

   ![](assets/correlation_matrix_binary_filter.png)

   A janela **[!UICONTROL Edit Correlation Metric Details]** será aberta.

   ![](assets/correlation_matrix_metric_details.png)

1. Configurar um filtro binário.

   Primeiro, clique na configuração **[!UICONTROL Inactive]** . Ele alternará para definir o filtro como **[!UICONTROL Active]** e exibirá os campos **Comparação** e **Valor**.

   Em seguida, selecione um operador **[!UICONTROL Comparison]** e defina seu **[!UICONTROL Value]** para configurar um filtro para a métrica selecionada.

>[!IMPORTANT]
>
>O Filtro binário para a Data Workbench 6.2 foi atualizado com novos recursos, que exigem a reconstrução de qualquer matriz de correlação com um filtro binário criado em versões anteriores.

## Adicionar elementos de Dimension {#section-f19f4e0368ca488e92d1e28bcc24417c}

Você também pode adicionar um elemento de dimensão para restringir uma métrica. Uma métrica pode ter apenas um elemento associado a ela.

![](assets/correlation_matrix_element.png)

Clique com o botão direito do mouse no espaço de trabalho e selecione **Tabela**. Abra uma dimensão com seus elementos e arraste para a configuração **[!UICONTROL Element]** na janela Editar detalhes de métrica de correlação ou solte em uma métrica na Matriz de correlação.
