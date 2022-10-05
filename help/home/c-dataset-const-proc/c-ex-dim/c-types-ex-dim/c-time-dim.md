---
description: Uma dimensão de tempo permite criar um conjunto de dimensões de hora local periódicas ou absolutas (como Dia, Dia da semana, Hora do dia, Tempo de reserva, etc.) com base em qualquer campo de carimbo de data/hora especificado para o parâmetro Tempo de entrada (época de 1970).
title: Dimensões de tempo
uuid: b633cf4f-0db4-4378-9e59-43b6ad8f772d
exl-id: f9534b24-3a16-4220-bac2-bc541e121005
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 10%

---

# Dimensões de tempo{#time-dimensions}

{{eol}}

Uma dimensão de tempo permite criar um conjunto de dimensões de hora local periódicas ou absolutas (como Dia, Dia da semana, Hora do dia, Tempo de reserva, etc.) com base em qualquer campo de carimbo de data/hora especificado para o parâmetro Tempo de entrada (época de 1970).

Ao definir dimensões de hora, você também pode escolher um dia diferente de Segunda para ser usado como início da semana especificando a parâmetro Dia de início da semana. Você pode definir mais de um conjunto de dimensões de tempo em seu conjunto de dados, desde que as dimensões tenham nomes diferentes.

As dimensões de tempo são definidas pelos seguintes parâmetros:

<table id="table_9734F6CD7ABA4661A2F9A5FB948A7282"> 
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
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Observações sobre a dimensão estendida. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensões </td> 
   <td colname="col2"> <p>Você pode especificar nomes de dimensão para qualquer um dos seguintes períodos: </p> <p> 
     <ul id="ul_EB0837DD66BE4004A615A6029EEF4CD5"> 
      <li id="li_2E46E6DB004E443C8CC831DCEE743D60"> Dia </li> 
      <li id="li_F59A27779EBE4E2A84E0972EE8BCDFA7"> Dia da semana </li> 
      <li id="li_7D74CD547ED1449091EF7B2E0E8C46DE"> Hora </li> 
      <li id="li_706AF9D385CB44C098DEBACA3BA2CD4B"> Hora do dia </li> 
      <li id="li_76FBF69B25954885A0192D308A155E41"> Mês </li> 
      <li id="li_3C16955BE5C54291A25E25CD31259661"> Semana </li> 
     </ul> </p> <p> Os nomes inseridos aqui são os que aparecem nos menus de dimensão e nas visualizações no Data Workbench. Se você deixar o nome de uma dimensão de tempo em branco, a dimensão não será criada no conjunto de dados. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Determina se a dimensão aparece na interface do Data Workbench. Por padrão, esse parâmetro é definido como false. Se, por exemplo, a dimensão for usada apenas como a base de uma métrica, você poderá definir esse parâmetro como true para ocultar a dimensão na exibição do Data Workbench. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tempo de entrada (época de 1970) </td> 
   <td colname="col2"> <p>O nome do campo de carimbo de data e hora a ser usado como entrada. </p> <p> <p>Observação: Os valores do campo devem representar o número de segundos desde 1º de janeiro de 1970, em 00:00:01. Se o tempo de entrada não for um tempo válido (1970 a 2037), o processo de transformação falhará e o servidor do Data Workbench gerará um erro. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pai </td> 
   <td colname="col2"> O nome da dimensão pai. Qualquer dimensão contável pode ser uma dimensão principal. Para dados da Web, o pai é Sessão. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dia de início da semana </td> 
   <td colname="col2"> <p>O dia a ser usado como o primeiro dia de uma semana. </p> <p> Esse parâmetro afeta a dimensão Semana, o dia da semana e qualquer dimensão de tempo do relatório definida em termos de semanas. </p> </td> 
   <td colname="col3"> Luz </td> 
  </tr> 
 </tbody> 
</table>

Este exemplo cria um conjunto de dimensões de tempo com base no campo de entrada definido pelo usuário x-time-1970. O conjunto de dimensões de tempo é chamado de &quot;Hora da sessão&quot;. Como o pai de cada dimensão é a dimensão Sessão , cada elemento das dimensões de tempo corresponde ao horário em que uma sessão começou. O parâmetro Week Start Day especifica que cada semana da dimensão Semana começa na segunda-feira.

![](assets/cfg_Transformation_Dim_TimeDim.png)
