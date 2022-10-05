---
description: Uma dimensão numérica consiste em elementos ordenados e numéricos e tem uma relação um para muitos com sua dimensão contável.
title: Dimensões numéricas
uuid: 19fab770-1535-41b2-bad1-811eba5f3575
exl-id: 69a4dfa6-8402-4c2b-8b04-e6e1a0fd5ccb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 2%

---

# Dimensões numéricas{#numeric-dimensions}

{{eol}}

Uma dimensão numérica consiste em elementos ordenados e numéricos e tem uma relação um para muitos com sua dimensão contável.

Você pode considerar uma dimensão numérica como uma representação das propriedades numéricas dos elementos da dimensão pai. Por exemplo, se você estiver trabalhando com dados da Web, poderá definir a dimensão numérica Receita da sessão, que define uma quantidade de receita, em dólares, para cada sessão na dimensão Sessão . Cada sessão tem uma única quantia de receita associada, mas várias sessões podem ter a mesma quantidade de receita associada. Portanto, a dimensão Receita da sessão tem uma relação um para muitos com a dimensão Sessão .

Normalmente, as dimensões numéricas são usadas para definir métricas que somam valores, contam ocorrências de uma condição ou localizam um valor mínimo ou máximo. Por exemplo, uma métrica chamada &quot;Receita&quot; pode ser definida usando a dimensão Receita da sessão: sum(Session_Revenue, Sessão). Definida dessa forma, a métrica Receita daria a quantidade total de receita para as sessões selecionadas.

As dimensões numéricas não podem ser pais de outras dimensões.

As dimensões numéricas são definidas pelos seguintes parâmetros:

<table id="table_15B849DD0BFC4D57AD6CF28898901324"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Nome descritivo da dimensão conforme ela aparece no Data Workbench. O nome da dimensão não pode incluir um hífen (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valores do clipe </td> 
   <td colname="col2"> Verdadeiro ou falso. Especifica se o valor de entrada (após Operação ) deve ser cortado para ficar entre os valores de Min e Max. Se Clip Values for true, o valor será recortado para esse intervalo. Se os Valores de clipe forem falsos, nenhum valor será retornado para o elemento da dimensão pai. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Observações sobre a dimensão estendida. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição </td> 
   <td colname="col2"> As condições em que o campo de entrada contribui para a criação da dimensão numérica. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tamanho fixo </td> 
   <td colname="col2"> Verdadeiro ou falso. Controla o número de elementos em uma dimensão (cardinalidade). Se true, todos os elementos de Min a Max serão incluídos na dimensão. Se falso, o tamanho da dimensão cresce à medida que os valores são adicionados. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Determina se a dimensão aparece na interface do Data Workbench. Por padrão, esse parâmetro é definido como false. Se, por exemplo, a dimensão for usada apenas como a base de uma métrica, você poderá definir esse parâmetro como true para ocultar a dimensão na exibição do Data Workbench. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> <p>O valor a ser usado com a Operação especificada ou o valor de entrada para o qual você deseja contar ocorrências. </p> <p> Se esse campo for um vetor de strings, a avaliação ocorrerá para cada elemento no vetor. Por exemplo, um vetor com comprimento 3 e uma Operação de CONTAGEM adicionam 3 à contagem. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Versão mín </td> 
   <td colname="col2"> Limite mais baixo no resultado final da dimensão. </td> 
   <td colname="col3"> 0 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Máx </td> 
   <td colname="col2"> Limite superior no resultado final da dimensão. </td> 
   <td colname="col3"> 1e6 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Deslocamento </td> 
   <td colname="col2"> Consulte Escala nesta tabela. </td> 
   <td colname="col3"> 0 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operação </td> 
   <td colname="col2"> <p>As operações disponíveis são as seguintes: </p> <p> 
     <ul id="ul_E04733E5E8824A2BAAB90D9356078D99"> 
      <li id="li_CAEE9167D45540BEAC538345F250B509"> CONTAGEM: O número total de valores que não estão em branco na variável <span class="wintitle"> Entrada</span> em todas as entradas de log que atendem à condição da dimensão é usada. Se a variável <span class="wintitle"> Entrada</span> for um campo de vetor, o número total de valores que não estão em branco em cada entrada de log será contado. </li> 
      <li id="li_64A4D671E78642BD9A9334F8098450B9"> PRIMEIRO NÃO EM BRANCO: O primeiro valor de entrada que não está em branco é usado, independentemente de ser proveniente da primeira entrada de log. If <span class="wintitle"> Entrada</span> é um campo de vetor, a primeira linha no vetor para a entrada de log relevante é usada. Se o valor não for um número, nenhum valor será usado. </li> 
      <li id="li_C967964729BD4A638FF78D8883CE513F"> PRIMEIRA LINHA: O valor da primeira entrada de log relacionada ao elemento da dimensão pai é usado, mesmo se a entrada estiver em branco. If <span class="wintitle"> Entrada</span> é um campo de vetor, a primeira linha no vetor para a entrada de log relevante é usada. Se esse valor estiver em branco ou não for um número, ou se a entrada de log relevante não atender à condição da dimensão, nenhum valor será usado. </li> 
      <li id="li_74171B17F480478B8547E1A361B22DA4"> ÚLTIMO NONBLANK: O último valor de entrada que não está em branco é usado, independentemente de ser proveniente da última entrada de log. If <span class="wintitle"> Entrada</span> é um campo de vetor, a primeira linha no vetor para a entrada de log relevante é usada. Se o valor não for um número, nenhum valor será usado. </li> 
      <li id="li_1253ECF507BD4BBF97CBB2FA12915045"> ÚLTIMA LINHA: O valor da última entrada de log relacionada ao elemento da dimensão pai é usado, mesmo se a entrada estiver em branco. If <span class="wintitle"> Entrada</span> é um campo de vetor, a primeira linha no vetor para a entrada de log relevante é usada. Se esse valor estiver em branco ou não for um número, ou se a entrada de log relevante não atender à condição da dimensão, nenhum valor será usado. </li> 
      <li id="li_20819E3944544F98853D6A02814F47B2"> SOMA: O total de todos os valores numéricos na variável <span class="wintitle"> Entrada</span> em todas as entradas de log que atendem à condição da dimensão é usada. Se não houver essas entradas de log ou nenhum valor numérico encontrado, o valor numérico 0 será usado. </li> 
      <li id="li_086C2E57604B4645A9203A984C6F9A04">MIN ou MAX: O valor numérico mínimo ou máximo encontrado na variável <span class="wintitle"> Entrada</span> em todas as entradas de log que atendem à condição da dimensão é usada. Se não houver essas entradas de log ou nenhum valor numérico, nenhum valor será usado. </li> 
     </ul> </p> <p> <p>Observação: Você deve especificar uma operação para garantir que a dimensão seja definida conforme esperado. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pai </td> 
   <td colname="col2"> O nome da dimensão pai. Qualquer dimensão contável pode ser uma dimensão principal. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Escala </td> 
   <td colname="col2"> <p>Para produzir o valor ordinal da dimensão, o resultado de Operation é transformado da seguinte maneira: </p> <p> (escala * entrada) + desvio </p> </td> 
   <td colname="col3"> 1.0 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>If [!DNL Operation] não produza qualquer valor, ou [!DNL Clip Values] é falso e o valor não está entre [!DNL Min] e [!DNL Max], nenhum elemento da dimensão numérica está relacionado ao elemento da dimensão pai.

Este exemplo ilustra a definição de uma dimensão numérica usando dados de evento coletados do tráfego do site. Essa dimensão numérica, chamada de &quot;Contador de exibição de anúncio&quot;, conta o número de vezes que o visitante vê um anúncio durante uma determinada sessão. A suposição é que todos os recursos de anúncio sejam solicitados do servidor da Web com ad= como parte da consulta cs-uri-query. No exemplo, o número de vezes (COUNT) em que o visitante é apresentado com um anúncio é o valor do interesse, não o valor real no campo .

![](assets/cfg_Transformation_Dim_Numeric.png)
