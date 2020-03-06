---
description: O vetor do monitor de recursos contém o Monitor de orçamento de memória e o Monitor de número de consultas.
solution: Analytics
title: Monitores de recursos da fila de consulta
topic: Data workbench
uuid: 6b516bed-7f9a-4821-869e-19e720f20313
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Monitores de recursos da fila de consulta{#query-queue-resource-monitors}

O vetor do monitor de recursos contém o Monitor de orçamento de memória e o Monitor de número de consultas.

A tabela a seguir descreve os campos do monitor de recursos usados para o enfileiramento de consulta.

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
   <td colname="col3"> <p>Monitora a memória de consulta usada pelo grupo de usuários atual. Se o uso atual estiver entre o Limite Inferior e o Limite Superior, nenhum grupo novo será agendado até que o uso da memória retorne para abaixo do Valor Limite Inferior, por exemplo, como resultado do fechamento dos espaços de trabalho pelos usuários. Os pacotes agendados podem crescer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite alto </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>O limite alto para uso de memória (bytes). Se o uso da memória estiver acima desse valor, nenhum agendamento ocorrerá e os pacotes de prioridade mais baixa não serão agendados um de cada vez, por um período de tempo, até que o uso da memória fique abaixo desse valor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite baixo </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>O limite baixo para uso de memória (bytes). Se <span class="wintitle"> o valor do Monitor</span> de orçamento de memória estiver abaixo desse valor, novos pacotes poderão ser programados e pacotes programados poderão crescer. Por exemplo, os pacotes crescem quando um usuário adiciona uma visualização a um espaço de trabalho. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo de reação </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>A constante de tempo para a suavização da estimativa de uso da memória. Valores de suavização evitam a reação a picos de uso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Número de Consultas do Monitor </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Monitora o número total de consultas programadas para o perfil no momento. Esse monitor de recursos permite programar pacotes se o número total de consultas permanecer abaixo do valor no campo Limite baixo. Este monitor permite que os pacotes programados no momento cresçam se o número total de consultas permanecer abaixo do valor no campo Limite alto. Além disso, este monitor remove os pacotes de prioridade baixa para permitir que os pacotes de prioridade mais alta sejam programados ou expandidos. No entanto, essa configuração não impede que os pacotes com prioridade maior do que a especificada no campo Prioridade intocável. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite alto </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>O limite alto para uso de memória (bytes). Se o uso da memória estiver acima desse valor, nenhum agendamento ocorrerá e os pacotes programados de prioridade mais baixa não serão agendados um de cada vez, por um período de tempo, até que o uso da memória fique abaixo desse valor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite baixo </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>O limite baixo para uso de memória (bytes). Se <span class="wintitle"> o valor do Monitor</span> de orçamento de memória estiver abaixo desse valor, os novos pacotes poderão ser programados e os pacotes programados poderão crescer. </p> </td> 
  </tr> 
 </tbody> 
</table>

