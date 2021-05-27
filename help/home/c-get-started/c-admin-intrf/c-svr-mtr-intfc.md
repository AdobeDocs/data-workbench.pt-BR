---
description: A interface do Monitor do Servidor é útil para solucionar problemas ou simplesmente rastrear os parâmetros de desempenho de computadores do servidor Data Workbench e computadores do Relatório que são clientes de computadores do servidor Data Workbench.
title: Interface do monitor do servidor
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
exl-id: fb8baae9-ac1e-4355-ba38-fef6621e22bb
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 2%

---

# Interface do monitor do servidor{#server-monitor-interface}

A interface do Monitor do Servidor é útil para solucionar problemas ou simplesmente rastrear os parâmetros de desempenho de computadores do servidor Data Workbench e computadores do Relatório que são clientes de computadores do servidor Data Workbench.

A interface do Monitor de servidor exibe um ponto verde ou um ponto vermelho na parte superior, à esquerda do nome do computador. Um ponto verde indica que o computador está funcionando sem problemas. Um ponto vermelho indica que um ou mais erros ocorreram no computador.

A parte inferior da interface do Server Monitor lista o status de processamento de cada um dos perfis disponíveis, bem como os detalhes de desempenho do computador.

Para obter mais informações sobre [!DNL Data Workbench servers], consulte o *Server Products Installation and Administration Guide*. Para obter mais informações sobre [!DNL Report], consulte o *Guia de Relatório de Data Workbench*.

**Para abrir a interface do Monitor do Servidor**

* No Gerenciador de Servidores, clique com o botão direito do mouse no nó do servidor do Data Workbench ou no computador [!DNL Report]. t

Clique em **[!UICONTROL Server Monitor]** para visualizar detalhes sobre um servidor, ou clique em **[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]** para visualizar detalhes sobre um cluster de servidores relacionados.

![](assets/vis_ServerMonitor.png)

A interface [!DNL Server Monitor]é atualizada automaticamente a cada 10 segundos.

A tabela a seguir lista as tarefas que podem ser concluídas usando a interface [!DNL Server Monitor].

<table id="table_A65426669ADE44B5A6BAD9D4E99A5CAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para executar esta tarefa... </th> 
   <th colname="col2" class="entry"> Ação... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Para verificar o status de processamento de log de um perfil </p> </td> 
   <td colname="col2"> <p>Visualize o vetor de Nome <i>Perfil</i>. No exemplo acima, você visualizaria o vetor ProfileExampleProfile do perfil de exemplo para ver que o perfil ExampleProfile processa em um servidor e seu processamento de log é 100% concluído. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Determinar quanto tempo o computador leva para responder às solicitações </p> </td> 
   <td colname="col2"> <p>Visualize o campo latência da pesquisa. Se este valor for superior a 1000 ms, entre em contato com os Serviços de Suporte do Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para exibir uma estimativa de quanto tempo pode demorar para concluir a transformação ou fazer query </p> </td> 
   <td colname="col2"> <p>Visualize o campo de tempo de varredura (hh:mm:ss), que está presente somente durante a transformação ou consulta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para determinar o número atual de conexões de rede com o computador </p> </td> 
   <td colname="col2"> <p>Veja a última linha das informações do <span class="wintitle"> Server Monitor</span> do computador. No exemplo acima, você vê que 2 conexões de rede atualmente vêm de um computador. </p> </td> 
  </tr> 
 </tbody> 
</table>
