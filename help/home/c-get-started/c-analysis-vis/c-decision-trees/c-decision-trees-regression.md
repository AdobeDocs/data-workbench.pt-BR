---
description: Avalie uma Árvore de decisão usando a opção Árvore de regressão com novos recursos de amostragem e visualização.
title: Opção de árvore de regressão para árvore de decisão
uuid: 1e3b5d5f-1fed-49c9-9a4d-d220c28075ac
exl-id: e5f8d525-1530-4169-b246-cdaf30e984c0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 3%

---

# Opção de árvore de regressão para árvore de decisão{#regression-tree-option-for-decision-tree}

{{eol}}

Avalie uma Árvore de decisão usando a opção Árvore de regressão com novos recursos de amostragem e visualização.

Avalie uma Árvore de decisão usando a opção Árvore de regressão clicando com o botão direito do mouse e selecionando Opções > **Árvore de regressão** em uma visualização Árvore de decisão.

**Construtor de árvore de decisão atualizado**: O novo algoritmo foi introduzido para criar um [Árvore de decisão](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/decision-trees/c-decision-trees.html). Ele trata dados mais gerais e fornece uma visualização mais informativa para melhorar a precisão da previsão.

**Módulo de amostragem de dados aprimorado**: Um esquema de amostragem adaptável atualizado ajuda a Árvore de decisão e Pontuação de propensão a obter resultados de precisão mais altos.

![](assets/CART-RegressionTreeOptions.jpg)

Verde e vermelho indicam verdadeiro ou falso. A saturação de cor — como vermelho profundo versus vermelho claro — é usada para indicar probabilidade. Por exemplo, um nó com vermelho profundo tem uma probabilidade muito alta de ser falso, enquanto um nó com vermelho claro tem uma probabilidade menor de ser falso. Um nó com verde profundo tem uma probabilidade muito alta de ser verdadeiro.

Todas as Árvores de decisão têm larguras de ramificação variáveis para indicar o nível de tráfego para essa ramificação da árvore.

Em uma visualização da Árvore de decisão, clique com o botão direito do mouse e selecione Opções > **Árvore de regressão**. Quando selecionada, configurações adicionais são fornecidas:

<table id="table_39E025A3E0B549B4BEDCE0D30A499211"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuração de regressão </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Use cada recurso apenas uma vez</b> </p> </td> 
   <td colname="col2"> <p>Selecionar essa opção não usará um recurso mais de uma vez (como a árvore de decisão original); portanto, se você tiver cinco entradas, a árvore não terá mais de cinco níveis e a estrutura da árvore será semelhante a uma Árvore de decisão (mas um pouco mais complicada). Essa opção agilizará a criação da árvore usando cada recurso apenas uma vez (como uma Árvore de decisão original). Usar esse recurso é uma configuração padrão. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Configuração de nível de árvore de regressão </b> </p> </td> 
   <td colname="col2"> <p>Essa opção controla a complexidade da Árvore de regressão. Dependendo dos dados, talvez seja necessário criar um <i>Fine</i> árvore (com uma estrutura complicada com mais nós) para obter uma classificação de árvore mais significativa. Se você tiver muitos dados, então um <i>Arroz</i> a árvore (menos complicada com menos nós de árvore) poderia funcionar bem. </p> <p> <p>Observação: <i>Típica</i> é a configuração padrão. Há alguns casos extremos em que a variável <i>Típica</i> não funciona bem e a configuração do <i>Arroz</i> ou <i>Fine</i> pode fornecer uma melhor visualização dos dados. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Fine</i>: A árvore mais complexa com os níveis mais granulares do relatório e a maioria das ramificações. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Típica</i>: O nível médio de granularidade e ramificações. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Arroz</i>: A árvore menos complexa com menos categorias definidas e menos ramos. </p> </td> 
  </tr> 
 </tbody> 
</table>
