---
description: As chamadas estatísticas avaliam relacionamentos significativos para identificar oportunidades ocultas e variáveis de interesse para recursos mais avançados de mineração de dados no agrupamento de público-alvo e na pontuação de resposta do visitante.
solution: Analytics
title: Chamadas estatísticas
topic: Data workbench
uuid: 04911ac4-bc3f-4813-800b-087d9668a782
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Chamadas estatísticas{#statistical-callouts}

As chamadas estatísticas avaliam relacionamentos significativos para identificar oportunidades ocultas e variáveis de interesse para recursos mais avançados de mineração de dados no agrupamento de público-alvo e na pontuação de resposta do visitante.

As chamadas estatísticas expandem os algoritmos para que mais tipos de dados possam ser correlacionados, como variáveis binomiais (sim/não, 0/1 ou comprador/não-comprador), correlacionados a métricas contáveis (visitas, pedidos ou downloads).

Para adicionar avisos estatísticos:

1. Em uma tabela, clique com o botão direito do mouse no cabeçalho da métrica.
1. Selecione **[!UICONTROL Statistics]** e, em seguida, selecione ou desmarque as marcas de seleção para cada configuração necessária. Todos na opção Exibir chamada são selecionados como a configuração padrão.

   ![](assets/statistical_callouts.png)

O texto explicativo pode retornar valores estatísticos fatorados nas colunas do conjunto de dados.

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
   <td colname="col2"><p> Identifica o valor Métrico mínimo em todos os elementos da dimensão. </p></td>
  </tr>
  <tr>
   <td colname="col1"> Média </td>
   <td colname="col2"><p> A média é a média aritmética dos valores de Métrica dos elementos na Dimensão, calculada pela soma total dividida pela contagem (soma/contagem). </p></td>
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
   <td colname="col2"><p> Uma medida da variação dos valores de Métrica da média de Métrica para essa dimensão. É igual ao quadrado do desvio padrão. </p></td>
  </tr>
 </tbody>
</table>

