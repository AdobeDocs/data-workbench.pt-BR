---
description: Um Filtro binário na Matriz de correlação permite que você restrinja valores para uma ou ambas as métricas correlacionadas para concentrar melhor a comparação.
title: Filtro binário na matriz de correlação
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
exl-id: e693fc72-5697-4c47-a498-e0d4d875c688
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 5%

---

# Filtro binário na matriz de correlação{#binary-filter-in-the-correlation-matrix}

{{eol}}

Um Filtro binário na Matriz de correlação permite que você restrinja valores para uma ou ambas as métricas correlacionadas para concentrar melhor a comparação.

Para definir um filtro binário em uma Matriz de correlação:

1. Na Matriz de correlação, clique com o botão direito do mouse em um nome de métrica.
1. Selecionar **Editar detalhes da métrica**.

   ![](assets/correlation_matrix_binary_filter.png)

   O **[!UICONTROL Edit Correlation Metric Details]** será aberta.

   ![](assets/correlation_matrix_metric_details.png)

1. Configurar um filtro binário.

   Primeiro, clique no botão **[!UICONTROL Inactive]** configuração. Ela alternará para definir o filtro como **[!UICONTROL Active]** e exibir o **Comparação** e **Valor** campos.

   Em seguida, selecione uma **[!UICONTROL Comparison]** e defina seu **[!UICONTROL Value]** para configurar um filtro para a métrica selecionada.

>[!IMPORTANT]
>
>O Filtro binário para a Data Workbench 6.2 foi atualizado com novos recursos, que exigem a reconstrução de qualquer matriz de correlação com um filtro binário criado em versões anteriores.

## Adicionar elementos de Dimension {#section-f19f4e0368ca488e92d1e28bcc24417c}

Você também pode adicionar um elemento de dimensão para restringir uma métrica. Uma métrica pode ter apenas um elemento associado a ela.

![](assets/correlation_matrix_element.png)

Clique com o botão direito do mouse no espaço de trabalho e selecione **Tabela**. Abra uma dimensão com seus elementos e arraste para a **[!UICONTROL Element]** na janela Editar detalhes da métrica de correlação ou soltar em uma métrica na Matriz de correlação.
