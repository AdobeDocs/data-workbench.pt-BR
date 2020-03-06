---
description: Um Filtro binário na Matriz de correlação permite que você restrinja valores para uma ou ambas as métricas correlacionadas para focalizar melhor a comparação.
solution: Analytics
title: Filtro binário na matriz de correlação
topic: Data workbench
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Filtro binário na matriz de correlação{#binary-filter-in-the-correlation-matrix}

Um Filtro binário na Matriz de correlação permite que você restrinja valores para uma ou ambas as métricas correlacionadas para focalizar melhor a comparação.

Para definir um filtro binário em uma Matriz de correlação:

1. Na Matriz de correlação, clique com o botão direito do mouse no nome de uma métrica.
1. Selecione **Editar detalhes** de métricas.

   ![](assets/correlation_matrix_binary_filter.png)

   A **[!UICONTROL Edit Correlation Metric Details]** janela abrirá.

   ![](assets/correlation_matrix_metric_details.png)

1. Configure um filtro binário.

   Primeiro, clique na **[!UICONTROL Inactive]** configuração. Ele alternará para definir o filtro como **[!UICONTROL Active]** e exibir os campos **Comparação** e **Valor** .

   Em seguida, selecione um **[!UICONTROL Comparison]** operador e configure-o **[!UICONTROL Value]** para configurar um filtro para a métrica selecionada.

>[!IMPORTANT]
>
>O Filtro binário para o Análise de big data 6.2 foi atualizado com novos recursos, exigindo a reconstrução de qualquer matriz de correlação com um filtro binário criado em versões anteriores.

## Adicionar elementos de dimensão {#section-f19f4e0368ca488e92d1e28bcc24417c}

Você também pode adicionar um elemento de dimensão para restringir uma métrica. Uma métrica pode ter apenas um elemento associado a ela.

![](assets/correlation_matrix_element.png)

Clique com o botão direito do mouse no espaço de trabalho e selecione **Tabela**. Abra uma dimensão com seus elementos e arraste para a **[!UICONTROL Element]** configuração na janela Editar detalhes de métrica de correlação ou solte em uma métrica na Matriz de correlação.
