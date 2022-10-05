---
description: Tabela que define os parâmetros do Grupo de usuários.
title: Grupos de usuários da fila de query
uuid: 90d9058c-1809-4579-a8c6-930a07affc83
exl-id: e9586ad4-4c0b-48b7-b533-4d23a0f4a216
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 2%

---

# Grupos de usuários da fila de query{#query-queue-user-groups}

{{eol}}

Tabela que define os parâmetros do Grupo de usuários.

<table id="table_670A47E25A7A43F0B599BD7ABB173E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nome </p> </td> 
   <td colname="col2"> <p>string </p> </td> 
   <td colname="col3"> <p>Um nome definido pelo usuário do grupo de usuários, como Analistas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Políticas </p> </td> 
   <td colname="col2"> <p>vetor </p> </td> 
   <td colname="col3"> <p>Especifica um tipo de política. Clique com o botão direito do mouse para escolher Política padrão ou Programação diária. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Política padrão </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Uma Política Padrão garante que os usuários com prioridade baixa sejam movidos de forma incremental para cima na fila e programados, mesmo que usuários com prioridade mais alta entrem na fila. É possível adicionar várias políticas do mesmo tipo em um grupo e seu efeito é cumulativo. 
     <ul id="ul_F7F60D23DC934F61AF2183177A11FA65"> 
      <li id="li_805ED3E740814FAEBFF2B411BAB3D248"><b>Limite de prioridade:</b> O limite acima do qual a prioridade não é aumentada. O valor máximo de prioridade. Você pode usar esse valor para manter as prioridades geradas por essa política em um intervalo específico (por exemplo, para que as prioridades para alguns outros grupos de usuários sejam sempre mais altas, ou para que não subam acima da Prioridade intocável. </li> 
     </ul> </p> <p> <b>Incrementos de políticas padrão</b> </p> <p>As configurações de incremento da Política padrão aumentam a prioridade de um conjunto de consultas conforme o tempo passa. Isso não força os pacotes a serem agendados, mas você pode usar essas configurações para priorizar usuários que estão esperando por muito tempo. Os parâmetros em fila afetam queries que estão em fila no momento (como em espera devido a recursos insuficientes para concluí-los). Os parâmetros agendados afetam as consultas que estão sendo respondidas. A prioridade de um query aumenta de acordo com o número especificado nos campos de incremento e intervalo de incremento apropriados: 
     <ul id="ul_7A5EE18CE10E4484A203B938525C806C"> 
      <li id="li_4B5CD827AF3848DA811A96C851340518"><b>Incremento em fila:</b> Define o incremento de prioridade por atualização enquanto está na fila. Essa configuração garante que os usuários de baixa prioridade sejam movidos para cima na fila de agendamento. </li> 
      <li id="li_91CA798235234A1CAC7AB32A7FB1CE84"><b>Intervalo de Incremento em Fila:</b> Define o número de segundos entre as atualizações durante a fila. </li> 
      <li id="li_079275E21ABA43B796A853624A6BDC29"><b>Incremento programado:</b> Define o incremento de prioridade por atualização durante a programação. </li> 
      <li id="li_3AE2EC3EBE6C4670BA0FA1BBD03FEBBD"><b>Intervalo de Incremento Programado:</b> Define o número de segundos entre as atualizações enquanto programadas. <p> <p>Observação: Definir as taxas de atualização de incremento e intervalo como mais altas para pacotes em fila do que para pacotes programados pode causar oscilação. (Por exemplo, suponha que você defina o valor do Incremento em fila como 100 e o Incremento agendado como 0 e defina o valor do Intervalo de incremento em fila como 1 e a Prioridade intocável como alta. Se dois pacotes de query chegarem com uma prioridade básica de 0 e não houver recursos suficientes para executar ambos os queries ao mesmo tempo, um deles será agendado. Após um segundo, o query que não foi agendado tem uma prioridade de 100 e antecede aquele que foi agendado. Depois de mais dois segundos, o que foi preemptado agora tem uma prioridade de 200, e os dois interruptores voltam a ser colocados. Nenhuma das consultas é concluída, pois a cada dois segundos a consulta que está sendo computada é antecipada para que a outra consulta possa ser executada.) </p> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Política de Programação Diária </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Permite alterar a prioridade em horários específicos do dia. Essa programação é útil para clientes automatizados, como <span class="wintitle"> Servidor de relatórios</span>e quando os usuários do sistema estiverem em fusos horários diferentes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alterações </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Clique com o botão direito do mouse para adicionar uma alteração de prioridade agendada. O Tempo de Alteração é a hora do dia em que a alteração ocorre. O formato é hora:minutos AM/PM. Se AM ou PM não for inserido, o sistema usará tempo militar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite de prioridade </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>O valor máximo de prioridade resultante de uma alteração. A Alteração de prioridade é o valor adicionado à prioridade. Por exemplo, um valor de 0 retorna para uma prioridade padrão. Qualquer outro valor resulta em uma prioridade da prioridade padrão mais esse número. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usuários </p> </td> 
   <td colname="col2"> <p>vetor </p> </td> 
   <td colname="col3"> <p>Lista os usuários que são membros do grupo. </p> <p> <b>Nome:</b> O nome do usuário como aparece no campo Nome comum no certificado do usuário. </p> <p> <b>Prioridade extra:</b> Fornece prioridade adicional à prioridade básica do grupo de usuários para determinar a prioridade inicial desse usuário. </p> </td> 
  </tr> 
 </tbody> 
</table>
