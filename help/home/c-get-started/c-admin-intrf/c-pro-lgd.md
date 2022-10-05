---
description: A Legenda de processamento fornece informações detalhadas sobre o processamento e a transformação de dados de um determinado servidor, permitindo que você acompanhe o progresso dos dados que estão sendo reprocessados e retransformados.
title: Legenda de processamento
uuid: 6c082c8f-fbb3-4e48-a249-2a13345fda86
exl-id: a83ce514-c92b-4cf8-a3cc-bff4e2ba63f1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---

# Legenda de processamento{#processing-legend}

{{eol}}

A Legenda de processamento fornece informações detalhadas sobre o processamento e a transformação de dados de um determinado servidor, permitindo que você acompanhe o progresso dos dados que estão sendo reprocessados e retransformados.

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
   <td colname="col1"> <p>Para visualizar o tamanho total de todos os dados </p> </td> 
   <td colname="col2"> <p>Revise os valores na <span class="wintitle"> Total de Entradas de Log</span> e <span class="wintitle"> Total de Bytes de Log</span> campos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para verificar se a filtragem está funcionando </p> </td> 
   <td colname="col2"> <p>Revise os valores na <span class="wintitle"> Total de Entradas de Log Filtradas</span> campos. Se o valor for 0, a filtragem não está funcionando e você deve verificar sua configuração para resolver o problema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para verificar o progresso do processamento de log </p> </td> 
   <td colname="col2"> <p>Revise o valor na <span class="wintitle"> Andamento do processamento de log</span> campo. Essa porcentagem indica quanto do reprocessamento está concluído. </p> <p>Ao reprocessar para refinar seu conjunto de dados, convém manter um olho no número de <span class="wintitle"> Total de entradas de log decodificadas</span> versus o número de <span class="wintitle"> Total de Entradas de Log Filtradas</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para verificar o progresso da transformação </p> </td> 
   <td colname="col2"> <p>Revise o valor na <span class="wintitle"> Andamento da transformação</span> campo. Essa porcentagem indica quanto da transformação está concluída. </p> </td> 
  </tr> 
 </tbody> 
</table>
