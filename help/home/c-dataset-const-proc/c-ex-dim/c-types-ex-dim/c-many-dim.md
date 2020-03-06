---
description: Uma dimensão muitas para muitas tem uma relação muitas para muitas com sua dimensão pai contável.
solution: Analytics
title: Dimensões de muitos para muitos
topic: Data workbench
uuid: 42c909e8-1228-4210-9406-ffc0d92372fa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensões de muitos para muitos{#many-to-many-dimensions}

Uma dimensão muitas para muitas tem uma relação muitas para muitas com sua dimensão pai contável.

Você pode considerar uma dimensão muitas para muitas como uma representação de um conjunto de valores para cada elemento em sua dimensão pai. Por exemplo, a dimensão muitas para muitas Frase de pesquisa é uma dimensão em nível de Sessão (tem um pai de Sessão). Representa o conjunto de frases de pesquisa associadas a cada sessão na dimensão Sessão. Uma única frase de pesquisa pode ser usada em qualquer número de sessões, e uma única sessão pode incluir zero ou mais frases de pesquisa. Portanto, a dimensão Frase de pesquisa tem uma relação muitos para muitos com a dimensão Sessão.

As dimensões muitas para muitas são definidas pelos seguintes parâmetros:

<table id="table_A6D495008DFF4DD28A3ECD718D775E54"> 
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
   <td colname="col2"> Nome descritivo da dimensão como aparece para o usuário na análise de big data. O nome da dimensão não pode incluir um hífen (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Notas sobre a dimensão estendida. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição </td> 
   <td colname="col2"> As condições em que a relação entre o pai e o valor do campo de entrada deve ser criada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Determina se a dimensão aparece na interface da análise de big data. Por padrão, esse parâmetro é definido como false. Se, por exemplo, a dimensão for usada apenas como base de uma métrica, você poderá definir esse parâmetro como verdadeiro para ocultar a dimensão da exibição da análise de big data. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> <p>O valor relacionado à dimensão pai (Pai). Se esse campo for um vetor de sequências de caracteres, cada elemento do vetor terá sua própria relação com o pai. </p> <p> <p>Observação:  Se o valor de entrada para cada entrada de log de um elemento da dimensão pai estiver vazio, nenhum elemento da dimensão muitos para muitos se relacionará a esse elemento da dimensão pai. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pai </td> 
   <td colname="col2"> O nome da dimensão pai. Qualquer dimensão contável pode ser uma dimensão pai. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Este exemplo ilustra a definição de uma dimensão muitas para muitas usando dados de evento coletados do tráfego do site. Essa dimensão muitas para muitas, chamada de &quot;Produto selecionado&quot;, relaciona as sessões aos produtos comprados pelo visitante durante essa sessão. O campo x-products contém um vetor de valores, cada um dos quais está associado a uma exibição de página, que, por sua vez, está associado a uma sessão.

![](assets/cfg_Transformation_Dim_ManytoMany.png)

Ao criar tal transformação, você pode criar uma visualização na análise de big data que descreve a relação entre a dimensão do produto selecionado e o número de sessões que envolvem cada um dos produtos.
