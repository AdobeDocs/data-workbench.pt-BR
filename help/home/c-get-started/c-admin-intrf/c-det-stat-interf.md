---
description: A interface de Status Detalhado é útil para solucionar erros ou outros problemas com computadores do servidor Data Workbench.
title: Interface de status detalhada
uuid: c4d375d9-431f-4b0a-ba15-b7a10501b2e2
exl-id: 6a460ebd-fb8f-4486-9849-dad2ff745cb5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1223'
ht-degree: 0%

---

# Interface de status detalhada{#detailed-status-interface}

{{eol}}

A interface de Status Detalhado é útil para solucionar erros ou outros problemas com computadores do servidor Data Workbench.

Isso inclui qualquer [!DNL Transform] perfis em execução nesses computadores, ou [!DNL Report] computadores que são clientes do servidor Data Workbench. Você pode acessar [!DNL Master Server] e [!DNL Query Server Detailed Status] por meio de [!DNL Admin] menu. Para acessar o [!DNL Detailed Status] interface para outros computadores, na [!DNL Servers Manager], clique com o botão direito do mouse no nó do servidor para o qual deseja visualizar o status e clique em **[!UICONTROL Detailed Status]**. Consulte [O Gerenciador de Servidores](../../../home/c-get-started/c-admin-intrf/c-svrs-mgr.md#concept-2dfff1ca5bce470a8ee854ed57cbe5ba).

Para obter mais informações sobre o servidor do Data Workbench, consulte o *Guia de Instalação e Administração de Produtos para Servidores*.

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>Para atualizar as informações em um [!DNL Detailed Status] , clique com o botão direito do mouse no **[!UICONTROL Detailed Status]** e clique em **[!UICONTROL Refresh]**.

A tabela a seguir lista as tarefas que podem ser concluídas usando o [!DNL Detailed Status] interface.

<table id="table_E685F31DCDB343F49FFA1019F2E8DA85"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para executar esta tarefa... </th> 
   <th colname="col2" class="entry"> Ação... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Para exibir cada componente do computador e seu status atual </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Status do componente</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para exibir a quantidade de memória no computador que está sendo usada </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Status da memória</span> &gt; <span class="uicontrol"> Carregamento de espaço de endereço</span>. </p> <p>Para obter mais informações sobre o monitoramento da carga do espaço de endereço, consulte o <i>Guia de Instalação e Administração de Produtos para Servidores</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para determinar se o computador está configurado para usar o Switch /3GB </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Status da memória</span> &gt; <span class="uicontrol"> Espaço de endereço do processo</span>. </p> <p>Se a variável <span class="wintitle"> Total</span> O campo exibe mais de 300000 KB, seu computador está configurado para usar o Switch /3GB. </p> <p>Para obter mais informações sobre o Switch /3GB, consulte o <i>Guia de Instalação e Administração de Produtos para Servidores</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para monitorar a quantidade de espaço em disco e memória usada para armazenar cada dimensão, bem como aquela usada para armazenar os nomes de seus elementos </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Desempenho</span> &gt; <span class="uicontrol"> Dimension</span> &gt; <span class="uicontrol"> Uso de disco</span> &gt; <i>&lt;<span class="uicontrol"> nome do perfil</span>&gt; </i>ou <span class="uicontrol"> Desempenho</span> &gt; <span class="uicontrol"> Dimension</span> &gt; <span class="uicontrol"> Uso de memória</span> &gt; <i>&lt;<span class="uicontrol"> nome do perfil</span>&gt;</i>. </p> <p>O <span class="wintitle"> Uso de disco</span> Os campos fornecem o nome e a quantidade de espaço em disco (em MB) necessários para armazenar cada dimensão. Grandes números de uso de disco podem afetar negativamente os tempos de consulta, pois o servidor do Data Workbench precisa ler todos os dados para concluir consultas relacionadas. Diminuir o uso do disco para uma dimensão pode reduzir o tempo necessário para concluir consultas relacionadas. </p> <p>O <span class="wintitle"> Uso de memória</span> Os campos fornecem o número de elementos em cada dimensão e a quantidade de memória necessária para armazenar a lista de nomes de elementos. Um grande número de elementos pode afetar negativamente a quantidade de memória que está sendo usada durante um query, pois o servidor do Data Workbench precisa ler cada elemento. A redução do número de elementos em uma dimensão pode reduzir o tempo necessário para concluir consultas relacionadas. </p> <p>Exemplo: <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Dimensions&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Disk&nbsp;Usage
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;1.386&nbsp;MB
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Memory&nbsp;Usage
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;21&nbsp;elements,&nbsp;0.001&nbsp;MB
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para monitorar o uso da CPU para os estágios em Processamento e Transformação de Log </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Desempenho</span> &gt; <span class="uicontrol"> Uso da CPU</span> &gt; <span class="uicontrol"> Processamento de log</span> &gt; <i>&lt;<span class="uicontrol"> nome do perfil</span>&gt;</i> ou <span class="uicontrol"> Desempenho</span> &gt; <span class="uicontrol"> Uso da CPU</span> &gt; <span class="uicontrol"> Transformação</span> &gt; &lt;<span class="uicontrol"> nome do perfil</span>&gt;. </p> <p>Cada um desses conjuntos de campos fornece o Uso da CPU (em segundos) para cada um dos estágios em Processamento e Transformação de Log. </p> <p>Exemplo: <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;CPU&nbsp;Usage&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName&nbsp;158.9&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Built-in&nbsp;158.1&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;13.0&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing\ProfileName&nbsp;0.8&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;0.8&nbsp;sec</code> </p> <p>O tempo necessário para concluir uma consulta geralmente é proporcional ao tamanho total de todas as suas dimensões. Após revisar o tamanho de cada dimensão, você pode avaliar se uma determinada dimensão é útil o suficiente e usada com frequência o suficiente para justificar o custo de desempenho da dimensão. Caso contrário, você poderá excluir a dimensão no <span class="wintitle"> Gerenciador de perfis</span>.<p>Uma dimensão cuja lista de nomes de elementos é excessivamente grande (ou seja, mais de 128 MB) pode causar erros de "Memória insuficiente" mesmo se o uso total do espaço de endereço não estiver próximo do limite. </p> <p>Além disso, se estiver usando um cluster de servidores Data Workbench, mas não estiver usando normalização centralizada, uma dimensão cuja lista de nomes de elementos é grande terá um impacto significativo nos orçamentos de memória de envio. Para obter mais informações sobre a normalização centralizada, consulte o <i>Guia de configuração do conjunto de dados</i>. Se a quantidade de memória necessária para armazenar todas as listas de nomes de elementos combinadas for superior a 100 MB em todos os servidores do cluster, você poderá receber erros de "Enviar orçamento de memória excedido" mesmo quando a atividade de consulta for leve. Por exemplo, se você tiver um cluster de quatro servidores com mais de 25 MB em cada servidor sendo usado para armazenar as listas de nomes de elementos, poderá receber erros. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para monitorar o tempo gasto no processamento e transformação de log </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Desempenho</span> &gt; <span class="uicontrol"> Uso da CPU</span> &gt; <span class="uicontrol"> Processamento de log</span> &gt; <i>&lt;<span class="uicontrol"> nome do perfil</span>&gt;</i> ou <span class="uicontrol"> Desempenho</span> &gt; <span class="uicontrol"> Uso da CPU</span> &gt; <span class="uicontrol"> Transformação</span> &gt; <i>&lt;<span class="uicontrol"> nome do perfil</span>&gt;</i>. </p> <p>A revisão dos campos nessas seções permite identificar filtros e transformações que podem estar afetando negativamente a quantidade de tempo necessária para o Processamento de log e a Transformação. Em seguida, você pode tomar decisões de design relacionadas a filtros e transformações individuais com longos tempos de processamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para monitorar o uso do espaço em disco e aumentar a velocidade da consulta </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Desempenho</span> &gt; <span class="uicontrol"> Campos de processamento de log</span> &gt; <i>&lt;<span class="uicontrol"> nome do perfil</span>&gt;</i>. </p> <p>Cada item de linha nesta seção corresponde a um parâmetro na função <span class="filepath"> Log Processing.cfg</span> arquivo. A revisão desses campos permite que você veja a quantidade de memória que cada parâmetro está usando. Em seguida, você pode tomar decisões de design em relação a itens individuais que são muito grandes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para determinar o tempo decorrido do reprocessamento ou da transformação anterior </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Status do processamento</span> &gt; <i>&lt;<span class="uicontrol"> nome do perfil</span>&gt;</i> &gt; <span class="uicontrol"> Histórico do modo de processamento</span>. </p> <p> 
     <ul id="ul_B7CC0DF54E004C72B220F928CF223F8E"> 
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">Tempo real - tempo em que o servidor do Data Workbench estava disponível para fazer consultas. </li> 
      <li id="li_3A3B490D70864A259780FC9FFC9AC15E">Entrada rápida - desta vez mais o tempo de Mesclagem rápida é o tempo total necessário para processar o conjunto de dados. </li> 
      <li id="li_B754C6DECD924170A15721EA4C942E3D">Fast Merge - tempo total necessário para transformar o conjunto de dados. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para diagnosticar problemas de "a partir do tempo" </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Status do processamento</span> &gt; <i>&lt;<span class="uicontrol"> nome do perfil</span>&gt;</i> &gt; <span class="uicontrol"> Hora</span> &gt; <span class="uicontrol"> Fontes como de</span>. </p> <p>Revisar as horas de cada origem pode ajudar você a determinar quais fontes podem estar afetando negativamente as ocorrências gerais. Você pode então resolver os problemas com essas fontes específicas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para estimar quanto tempo uma consulta em execução leva para ser concluída </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Mecanismo de execução</span>. </p> <p>Revisão da <span class="wintitle"> Tempo de varredura de dados</span> fornece uma estimativa de quanto tempo leva para uma consulta ser concluída. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para listar todos os perfis disponíveis neste computador e detalhes sobre seu status </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Perfis</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para exibir o status de Replicação </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Status do componente</span>. </p> <p>Verifique o status do componente Replicar. Se Replicação estiver em execução, OK será exibido. Se o componente Replicar falhar, uma mensagem de erro será exibida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para exibir <span class="wintitle"> Servidor de relatórios</span> status para um <span class="keyword"> Relatório</span> computador que se conecta ao servidor do Data Workbench </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Status do servidor de relatórios</span>. </p> <p>Esta seção do <span class="wintitle"> Status detalhado</span> inclui uma cópia da <span class="filepath"> Report Server.cfg</span> , informações sobre o número de relatórios em execução (Fração atual) e informações sobre o erro mais recente (Último erro). </p> <p>Para ver as etapas para editar o <span class="filepath"> Report Server.cfg</span> consulte o <i>Guia de relatório de Data Workbench</i>. </p> <p> <p>Observação: Se a variável <span class="wintitle"> Status do servidor de relatórios</span> não é exibida no <span class="wintitle"> Status detalhado</span> pode ser necessário configurar o servidor do Data Workbench para exibir <span class="wintitle"> Status do servidor de relatórios</span>. Para ver as etapas, consulte a <i>Guia de relatório de Data Workbench</i>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para exibir informações de uso de memória para Transformar </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Status do processamento</span> &gt; <span class="uicontrol"> Transformar</span>. </p> <p>Para obter mais informações sobre Transformar, consulte o <i>Guia de Instalação e Administração de Produtos para Servidores</i> e <i>Guia de configuração do conjunto de dados</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para salvar o <span class="wintitle"> Status detalhado</span> interface como <span class="filepath"> *.cfg</span> arquivo que pode ser aberto em um editor de texto, como o Bloco de notas ou distribuído para outros </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse no <span class="uicontrol"> Status detalhado</span> e clique em <span class="uicontrol"> Salvar cópia como</span>. </p> <p>Observação:  <p>Clicando com o botão direito do mouse no botão <span class="uicontrol"> Status detalhado</span> e clicando em <span class="uicontrol"> Salvar</span> para <i>nome do servidor</i>/Status/ não funciona na variável <span class="wintitle"> Status detalhado</span> interface. A seguinte mensagem de erro é exibida: </p> <p>Não é possível salvar /Status/. 403 Proibido </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para exibir <span class="uicontrol"> Linhas por Origem de Log</span> métrica </p> </td> 
   <td colname="col2"> <p>Se a métrica Linhas por Fonte de Log precisar ser relatada em Status Detalhado, o Administrador do Data Workbench deverá definir a "ID da Fonte de Log" e fornecer um nome exclusivo em Log Processing.cfg do Perfil Personalizado. </p> </td> 
  </tr> 
 </tbody> 
</table>
