---
description: A interface do Monitor do servidor é útil para solucionar problemas ou simplesmente rastrear os parâmetros de desempenho dos computadores do servidor Análise de big data e computadores do Relatório que são clientes dos computadores do servidor Análise de big data.
solution: Analytics
title: Interface do monitor do servidor
topic: Data workbench
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Interface do monitor do servidor{#server-monitor-interface}

A interface do Monitor do servidor é útil para solucionar problemas ou simplesmente rastrear os parâmetros de desempenho dos computadores do servidor Análise de big data e computadores do Relatório que são clientes dos computadores do servidor Análise de big data.

A interface do Monitor de servidor exibe um ponto verde ou um ponto vermelho na parte superior, à esquerda do nome do computador. Um ponto verde indica que o computador está funcionando sem problemas. Um ponto vermelho indica que um ou mais erros ocorreram no computador.

A parte inferior da interface do Monitor de servidor lista o status de processamento de cada um dos perfis disponíveis, bem como os detalhes de desempenho do computador.

Para obter mais informações sobre [!DNL Data Workbench servers], consulte o Guia *de Instalação e Administração de Produtos para* Servidor. Para obter mais informações sobre [!DNL Report], consulte o Guia *de relatórios da Análise de* big data.

**Para abrir a interface do Monitor do servidor**

* No Gerenciador de servidores, clique com o botão direito do mouse no nó do servidor ou [!DNL Report] computador da Análise de big data. t

Clique **[!UICONTROL Server Monitor]** para exibir detalhes sobre um servidor ou clique em **[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]** para exibir detalhes sobre um cluster de servidores relacionados.

![](assets/vis_ServerMonitor.png)

A [!DNL Server Monitor]interface é atualizada automaticamente a cada 10 segundos.

A tabela a seguir lista as tarefas que podem ser concluídas usando a [!DNL Server Monitor] interface.

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
   <td colname="col2"> <p>Exiba o vetor Nome do <i>perfil</i> do perfil. No exemplo acima, você veria o vetor Profile ExampleProfile para ver se o perfil ExampleProfile processa em um servidor e seu processamento de log está 100% concluído. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para determinar quanto tempo o computador leva para responder às solicitações </p> </td> 
   <td colname="col2"> <p>Exibir o campo de latência da pesquisa. Se esse valor for superior a 1000 ms, entre em contato com os Serviços de suporte da Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para exibir uma estimativa de quanto tempo pode levar para concluir a transformação ou consultar </p> </td> 
   <td colname="col2"> <p>Visualize o campo de tempo de varredura (hh:mm:ss), que está presente somente durante a transformação ou consulta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para determinar o número atual de conexões de rede com o computador </p> </td> 
   <td colname="col2"> <p>Ver a última linha das informações do Monitor <span class="wintitle"></span> de servidor do computador. No exemplo acima, você verá que 2 conexões de rede vêm atualmente de um computador. </p> </td> 
  </tr> 
 </tbody> 
</table>

