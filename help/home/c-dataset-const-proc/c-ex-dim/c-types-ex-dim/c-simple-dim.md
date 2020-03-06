---
description: Uma dimensão simples tem uma relação um para muitos com sua dimensão pai contável.
solution: Analytics
title: Dimensões simples
topic: Data workbench
uuid: 3bca2354-02c4-4739-a7da-acccdb0efdfd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensões simples{#simple-dimensions}

Uma dimensão simples tem uma relação um para muitos com sua dimensão pai contável.

Uma dimensão simples é sempre um filho de uma dimensão contável. Você pode considerar uma dimensão simples como uma representação de uma propriedade dos elementos em sua dimensão pai. Por exemplo, se você estiver trabalhando com dados da Web, poderá definir a dimensão Referenciador de visitantes, que é uma dimensão simples com uma dimensão pai de Visitante. Representa o primeiro referenciador HTTP para cada visitante na dimensão Visitante. Cada visitante na dimensão Visitante tem apenas um referenciador de visitante, mas muitos visitantes podem ter o mesmo referenciador de visitantes. Portanto, a dimensão Referenciador de visitantes tem uma relação um para muitos com a dimensão Visitante.

As dimensões simples são definidas pelos seguintes parâmetros:

<table id="table_E6F729DFA226459DBFC1776CE8CB81F8"> 
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
   <td colname="col2"> Nome descritivo da dimensão como aparece na análise de big data. O nome da dimensão não pode incluir um hífen (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Notas sobre a dimensão estendida. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição </td> 
   <td colname="col2"> As condições em que a relação entre o Pai e o valor do campo de entrada deve ser criada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Determina se a dimensão aparece na interface da análise de big data. Por padrão, esse parâmetro é definido como false. Se, por exemplo, a dimensão for usada apenas como base de uma métrica, você poderá definir esse parâmetro como verdadeiro para ocultar a dimensão da exibição da análise de big data. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> O campo de valores relacionado à dimensão pai (Pai). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Carregar arquivo </td> 
   <td colname="col2"> <p>Opcional. Um arquivo de valores disponíveis para a relação. Use um arquivo de carregamento quando uma das seguintes situações se aplicar: </p> <p> 
     <ul id="ul_056C4A8E46AA479397DC63173C035D5C"> 
      <li id="li_C26EB5A4AB3C4BEB8EB3A217A5A2377E"> Os valores têm uma ordem de classificação específica que você deseja preservar na exibição da análise de big data. Por exemplo, você pode querer criar uma dimensão Trimestre cujos elementos (os trimestres do ano) sempre são exibidos em ordem cronológica. </li> 
      <li id="li_5D4DF56BC6124D038A7260131B1F3DB3"> Você deseja criar espaços reservados para valores que podem não ser encontrados nos dados, mas que precisam aparecer na exibição da análise de big data. </li> 
     </ul> </p> <p> Se for encontrado um valor que não está presente no arquivo, ele será adicionado ao final dos valores quando exibido na análise de big data. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operação </td> 
   <td colname="col2"> <p>As operações disponíveis são as seguintes: </p> <p> 
     <ul id="ul_88AE4279413C42609D8B53EC64B5E913"> 
      <li id="li_DD9623D006844BC28B2AAA8E12AA04E1"> PRIMEIRO NÃO EM BRANCO: O primeiro valor de entrada que não está em branco é usado, independentemente de ser proveniente da primeira entrada do registro. Se Input for um campo de vetor, a primeira linha no vetor para a entrada de log relevante será usada. </li> 
      <li id="li_0FBE7F0B7B9744D994ECEDAA08F0045C"> PRIMEIRA LINHA: O valor da primeira entrada de log relacionada ao elemento de dimensão pai é usado, mesmo se a entrada estiver em branco. Se Input for um campo de vetor, a primeira linha no vetor para a entrada de log relevante será usada. Se esse valor estiver em branco ou não for um número, ou se a entrada de log relevante não atender à Condição da dimensão, nenhum valor será usado. </li> 
      <li id="li_C17190BC699D4A099DC5326C07D1044D"> ÚLTIMO NÃO BRANCO: O último valor de entrada que não está em branco é usado, independentemente de ser proveniente da última entrada do registro. Se Input for um campo de vetor, a primeira linha no vetor para a entrada de log relevante será usada. </li> 
      <li id="li_00BAE86F12004C098F6A455908DB7062"> ÚLTIMA LINHA: O valor da última entrada de log relacionada ao elemento de dimensão pai é usado, mesmo se a entrada estiver em branco. Se Input for um campo de vetor, a primeira linha no vetor para a entrada de log relevante será usada. Se esse valor estiver em branco ou não for um número, ou se a entrada de log relevante não atender à Condição da dimensão, nenhum valor será usado. </li> 
     </ul> </p> <p> <p>Observação:  Se a Operação não gerar nenhum valor ou um valor em branco para uma entrada de log específica, o elemento correspondente da dimensão pai se relacionará ao elemento "Nenhum" da dimensão simples. </p> </p> <p> Você deve especificar uma operação para garantir que a dimensão seja definida conforme desejado. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pai </td> 
   <td colname="col2"> O nome da dimensão pai. Qualquer dimensão contável pode ser uma dimensão pai. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Este exemplo ilustra a definição de uma dimensão simples usando dados de evento coletados do tráfego do site e um arquivo de carregamento.

Considere o exemplo de uma pesquisa com os cookies favoritos de escoteiro dos visitantes do site. Uma página da Web captura esse voto e o retorna ao servidor da Web no favorito par nome-valor. Somente um voto por visitante é contado, mas os visitantes podem mudar de ideia e votar novamente, se desejado. Esta é uma relação um para muitos: um visitante pode ter muitos votos, mas cada voto está associado a apenas um visitante. Portanto, o pai da dimensão são os visitantes (somente um voto por visitante) e a operação é ÚLTIMA LINHA (para que eles possam mudar de ideia e votar novamente).

Os marcadores de posição devem existir para todos os tipos de cookies para que os tipos de cookies que não recebem votos sejam exibidos na exibição da análise de big data. Por esses motivos, foi definido um arquivo de carregamento que contém a lista de tipos de cookies que podem ser selecionados. O conteúdo desse arquivo, salvo em um arquivo chamado [!DNL cookietypes.txt], é semelhante ao seguinte:

Tesouros animais

Delícias de caramelo

Limão de pastelaria

Pedaços de Manteiga de amendoim

Atalhos

Miniaturas finas

A dimensão final é definida como mostrado aqui:

![](assets/cfg_Transformation_Dim_Simple.png)

