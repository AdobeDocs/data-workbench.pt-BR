---
description: A visualização de Corda de associação permite mostrar a proporção e a associação entre métricas, dimensões e elementos, exibindo acordes maiores como uma indicação de uma associação mais forte.
title: Visualização de corda de associação
uuid: c656ffc8-e45a-44c0-a29b-cdc10dcbd1f2
exl-id: e71394ef-4895-4a3e-912d-d6f56ca8f001
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 1%

---

# Visualização de corda de associação{#association-chord-visualization}

{{eol}}

A visualização de Corda de associação permite mostrar a proporção e a associação entre métricas, dimensões e elementos, exibindo acordes maiores como uma indicação de uma associação mais forte.

A Tabela de Associações compara valores com o cálculo V de Cramer em vez de usar o coeficiente de correlação de Pearson, como empregado na variável [Matriz de correlação](/help/home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md) e [Correlação de corda](/help/home/c-get-started/c-analysis-vis/associations-visualization.md) visualizações (essas podem apenas comparar métricas, enquanto a Tabela de associação e a Corda podem comparar métricas, dimensões e elementos). O Gráfico de Associações também fornece outra exibição em um relatório criado anteriormente [Tabela Associações](../../../home/c-get-started/c-analysis-vis/associations-visualization.md#concept-9d937dda38174875b32095c6eaf22f2f).

**Para criar uma corda de associação**

1. Em um espaço de trabalho, clique com o botão direito do mouse **Visualização > Análise preditiva > Corda de associação**.

   Um menu será aberto, permitindo selecionar uma dimensão estendida na lista.

   ![](assets/association_chord1.png)

   Depois de selecionada, a Tabela de Associação em branco será aberta com a Dimension selecionada identificada no título. ![](assets/association_chord2.png)

1. **Selecione uma métrica, dimensão ou elemento de dimensão**.

   Clique com o botão direito do mouse na visualização de acorde e selecione **Adicionar métrica** ou **Adicionar Dimension**. Selecione itens no menu para adicionar ao acorde.

   Também é possível arrastar métricas e dimensões do **[!UICONTROL Finder]** clicando em **[!UICONTROL Ctrl-Alt]** e arrastar métricas e dimensões para o acorde. Ou arraste elementos de dimensão diretamente de uma tabela aberta para a visualização de acorde.

1. **Escolha métricas, dimensões e elementos adicionais para associar**.

   Após dois ou mais valores serem selecionados, o gráfico será atualizado automaticamente e começará a exibir os dados de associação. Continue adicionando métricas conforme necessário para associar pontos de dados.

   ![](assets/association_chord.png)

   A visualização de Corda exibe a proporção do todo representado pela área de cada segmento. Continue a adicionar métricas/dimensões/elementos conforme necessário para identificar e investigar relacionamentos significativos.

1. **Exibir a visualização Corda**.

   Passe o mouse sobre cada valor na visualização para ver os relacionamentos.

1. **Alterar configurações.** Clique com o botão direito do mouse na visualização de acorde para abrir um menu para alterar a métrica, a dimensão ou os elementos exibem as dimensões como números absolutos ou porcentagens, remover a métrica selecionada ou todas as métricas, editar cores e detalhes e exportar valores para uma Tabela de associações.

**Para criar um Corda de Associação a partir de uma Tabela de Associação:**

1. Abra um **Tabela de Associação** visualização.
1. Clique com o botão direito do mouse e selecione **Visualização de corda de exportação**. Um diagrama de Corda de Associação será aberto com valores selecionados na Tabela de Associação. ![](assets/association_table_to_chord.png)

>[!IMPORTANT]
>
>Exportar uma Tabela de Associação a partir de um Diagrama de Corda de Associação que contenha pelo menos uma métrica resultará em elementos duplicados nas linhas/colunas da Tabela de Associação. Para evitar elementos duplicados, crie uma nova Tabela de Associação e adicione os elementos desejados em vez de exportar os elementos de um Diagrama de Corda de Associação.
