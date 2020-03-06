---
description: A Legenda de processamento fornece informações detalhadas sobre o processamento e a transformação de dados de um determinado servidor, permitindo rastrear o progresso dos dados que estão sendo reprocessados e retransformados.
solution: Analytics
title: Legenda de processamento
topic: Data workbench
uuid: 6c082c8f-fbb3-4e48-a249-2a13345fda86
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Legenda de processamento{#processing-legend}

A Legenda de processamento fornece informações detalhadas sobre o processamento e a transformação de dados de um determinado servidor, permitindo rastrear o progresso dos dados que estão sendo reprocessados e retransformados.

![](assets/vis_ProcessingLegend.png)

A tabela a seguir lista as tarefas que podem ser concluídas usando o [!DNL Processing Legend].

<table id="table_6149250C44B14C44A3CB1CEF68B280C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para executar esta tarefa... </th> 
   <th colname="col2" class="entry"> Ação... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Para exibir o tamanho total de todos os seus dados </p> </td> 
   <td colname="col2"> <p>Revise os valores nos campos <span class="wintitle"> Total de entradas</span> de log e Total <span class="wintitle"> de</span> bytes de log. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para verificar se a filtragem está funcionando </p> </td> 
   <td colname="col2"> <p>Revise os valores nos campos <span class="wintitle"> Total de entradas</span> de log filtradas. Se o valor for 0, a filtragem não está funcionando e você deve verificar sua configuração para resolver o problema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para verificar o progresso do processamento de log </p> </td> 
   <td colname="col2"> <p>Revise o valor no campo Andamento <span class="wintitle"> do processamento de</span> log. Essa porcentagem indica quanto do reprocessamento foi concluído. </p> <p>Ao reprocessar para refinar seu conjunto de dados, talvez você queira manter um olho no número de <span class="wintitle"> Total de entradas</span> de log decodificadas em relação ao número de <span class="wintitle"> Total de entradas</span>de log filtradas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para verificar o progresso da transformação </p> </td> 
   <td colname="col2"> <p>Revise o valor no campo <span class="wintitle"> Transformation Progress (Andamento</span> da Transformação). Essa porcentagem indica quanto da transformação está concluída. </p> </td> 
  </tr> 
 </tbody> 
</table>

