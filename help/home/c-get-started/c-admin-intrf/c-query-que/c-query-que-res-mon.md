---
description: O vetor do monitor de recursos contém o Monitor de Orçamento de Memória e o Monitor de Número de Consultas.
title: Monitores de recursos da fila de query
uuid: 6b516bed-7f9a-4821-869e-19e720f20313
exl-id: 6d445a4d-a415-41ce-9d45-1bdd0e726edd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 2%

---

# Monitores de recursos da fila de query{#query-queue-resource-monitors}

{{eol}}

O vetor do monitor de recursos contém o Monitor de Orçamento de Memória e o Monitor de Número de Consultas.

A tabela a seguir descreve os campos do monitor de recursos usados para fila de query.

<table id="table_9991EED2647A460FACA2DC80D4973A8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Monitor de orçamento de memória </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Monitora a memória de consulta usada pelo grupo de usuários atual. Se o uso atual estiver entre o Limite baixo e o Limite alto, nenhum pacote novo será agendado até que o uso da memória retorne para um valor abaixo do Limite baixo, por exemplo, como resultado de usuários fechando seus espaços de trabalho. Os pacotes agendados podem crescer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite alto </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>O limite alto para uso de memória (bytes). Se o uso de memória estiver acima desse valor, nenhum agendamento ocorrerá e os pacotes de prioridade mais baixa agendados não serão agendados um de cada vez, durante um período de tempo, até que o uso de memória seja trazido para abaixo desse valor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite baixo </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>O limite baixo para uso de memória (bytes). If <span class="wintitle"> Monitor de orçamento de memória</span> estiver abaixo desse valor, novos pacotes poderão ser agendados e pacotes agendados poderão crescer. Por exemplo, os pacotes aumentam quando um usuário adiciona uma visualização a um espaço de trabalho. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo de reação </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>A constante de tempo para a suavização da estimativa de uso de memória. Valores de suavização evitam a reação a picos de uso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Número do Monitor de Consultas </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Monitora o número total de consultas que estão agendadas atualmente para o perfil. Esse monitor de recursos permite agendar pacotes se o número total de consultas permanecer abaixo do valor no campo Baixo limite . Esse monitor permite o crescimento de pacotes programados no momento se o número total de consultas permanecer abaixo do valor no campo Alto Limite . Além disso, esse monitor remove pacotes de prioridade baixa para permitir que pacotes de prioridade mais alta sejam agendados ou expandidos. No entanto, essa configuração não impede pacotes com prioridade maior do que a especificada no campo Prioridade intocável . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite alto </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>O limite alto para uso de memória (bytes). Se o uso de memória estiver acima desse valor, nenhum agendamento ocorrerá e os pacotes agendados de prioridade mais baixa não serão agendados um de cada vez, durante um período de tempo, até que o uso de memória seja trazido para abaixo desse valor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite baixo </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>O limite baixo para uso de memória (bytes). If <span class="wintitle"> Monitor de orçamento de memória</span> estiver abaixo desse valor, novos pacotes poderão ser agendados e os pacotes agendados poderão crescer. </p> </td> 
  </tr> 
 </tbody> 
</table>
