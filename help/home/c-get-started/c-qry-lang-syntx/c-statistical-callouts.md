---
description: As chamadas estatísticas avaliam relacionamentos significativos para identificar oportunidades ocultas e variáveis de interesse para recursos de mineração de dados mais avançados em clustering de público-alvo e pontuação de resposta do visitante.
title: Chamadas estatísticas
uuid: 04911ac4-bc3f-4813-800b-087d9668a782
exl-id: d4ed540e-f837-4db9-a81e-b8a30c15f270
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 22%

---

# Chamadas estatísticas{#statistical-callouts}

{{eol}}

As chamadas estatísticas avaliam relacionamentos significativos para identificar oportunidades ocultas e variáveis de interesse para recursos de mineração de dados mais avançados em clustering de público-alvo e pontuação de resposta do visitante.

As chamadas estatísticas expandem os algoritmos para que mais tipos de dados possam ser correlacionados, como variáveis binômicas (sim/não, 0/1 ou comprador/não comprador), correlacionadas com métricas contáveis (visitas, pedidos ou downloads).

Para adicionar chamadas estatísticas:

1. Em uma tabela, clique com o botão direito do mouse no cabeçalho da métrica.
1. Selecionar **[!UICONTROL Statistics]** e, em seguida, selecione ou desmarque as marcas de seleção de cada configuração necessária. Todas as chamadas de exibição são selecionadas como a configuração padrão.

   ![](assets/statistical_callouts.png)

A chamada pode retornar valores estatísticos fatorados nas colunas do conjunto de dados.

<table id="table_B2A4F9D5938D4756A81ACF6F4D77E63D">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Cálculo </th>
   <th colname="col2" class="entry"> Descrição </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Contagem </td>
   <td colname="col2"><p>Retorna o número de linhas em um conjunto de dados. </p></td>
  </tr>
  <tr>
   <td colname="col1"> Máximo </td>
   <td colname="col2"><p> Identifica o valor máximo de Métrica em todos os elementos da dimensão. </p></td>
  </tr>
  <tr>
   <td colname="col1"> Mínimo </td>
   <td colname="col2"><p> Identifica o valor de Métrica mínimo em todos os elementos da dimensão. </p></td>
  </tr>
  <tr>
   <td colname="col1"> Média </td>
   <td colname="col2"><p> A média é a média aritmética dos valores de Métrica de elementos no Dimension, calculada pela soma total dividida pela contagem (soma/contagem). </p></td>
  </tr>
  <tr>
   <td colname="col1"> Desvio padrão </td>
   <td colname="col2"> O desvio padrão mostra quantas variações existem a partir da média esperada. Um desvio padrão inferior mostra os pontos de dados próximos à média. Um desvio padrão superior mostra que os pontos de dados estão distribuídos por uma ampla gama de valores. </td>
  </tr>
  <tr>
   <td colname="col1"> Total </td>
   <td colname="col2"><p> Retorna a soma total dos valores de Métrica. </p></td>
  </tr>
  <tr>
   <td colname="col1"> Variação </td>
   <td colname="col2"><p> Uma medida da variação dos valores de Métrica da média da Métrica para essa dimensão. É igual ao quadrado do desvio padrão. </p></td>
  </tr>
 </tbody>
</table>
