---
description: A interface do Monitor do Servidor é útil para solucionar problemas ou simplesmente rastrear os parâmetros de desempenho de computadores do servidor Data Workbench e computadores do Relatório que são clientes de computadores do servidor Data Workbench.
title: Interface do monitor do servidor
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
exl-id: fb8baae9-ac1e-4355-ba38-fef6621e22bb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 2%

---

# Interface do monitor do servidor{#server-monitor-interface}

{{eol}}

A interface do Monitor do Servidor é útil para solucionar problemas ou simplesmente rastrear os parâmetros de desempenho de computadores do servidor Data Workbench e computadores do Relatório que são clientes de computadores do servidor Data Workbench.

A interface do Monitor de servidor exibe um ponto verde ou um ponto vermelho na parte superior, à esquerda do nome do computador. Um ponto verde indica que o computador está funcionando sem problemas. Um ponto vermelho indica que um ou mais erros ocorreram no computador.

A parte inferior da interface do Server Monitor lista o status de processamento de cada um dos perfis disponíveis, bem como os detalhes de desempenho do computador.

Para obter mais informações sobre [!DNL Data Workbench servers], consulte o *Guia de Instalação e Administração de Produtos para Servidores*. Para obter mais informações sobre [!DNL Report], consulte o *Guia de relatório de Data Workbench*.

**Para abrir a interface do Monitor do Servidor**

* No Gerenciador de servidores, clique com o botão direito do mouse no nó do servidor do Data Workbench ou [!DNL Report] computador. t

Clique em **[!UICONTROL Server Monitor]** para exibir detalhes sobre um servidor, ou clique em **[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]** para exibir detalhes sobre um cluster de servidores relacionados.

![](assets/vis_ServerMonitor.png)

O [!DNL Server Monitor]atualizações da interface automaticamente a cada 10 segundos.

A tabela a seguir lista as tarefas que podem ser concluídas usando o [!DNL Server Monitor] interface.

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
   <td colname="col2"> <p>Exibir o perfil <i>Perfil</i> Nomear vetor. No exemplo acima, você visualizaria o vetor ProfileExampleProfile do perfil de exemplo para ver que o perfil ExampleProfile processa em um servidor e seu processamento de log é 100% concluído. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Determinar quanto tempo o computador leva para responder às solicitações </p> </td> 
   <td colname="col2"> <p>Visualize o campo latência da pesquisa. Se este valor for superior a 1000 ms, entre em contato com os Serviços de Suporte do Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para exibir uma estimativa de quanto tempo pode demorar para concluir a transformação ou fazer query </p> </td> 
   <td colname="col2"> <p>Exibir o tempo de varredura (hh:mm:s), que está presente somente durante a transformação ou consulta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para determinar o número atual de conexões de rede com o computador </p> </td> 
   <td colname="col2"> <p>Exibir a última linha do <span class="wintitle"> Monitor de servidor</span> informações. No exemplo acima, você vê que 2 conexões de rede atualmente vêm de um computador. </p> </td> 
  </tr> 
 </tbody> 
</table>
