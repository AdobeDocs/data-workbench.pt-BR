---
description: A interface de Status detalhado é útil para solucionar erros ou outros problemas com os computadores de servidor da Análise de big data.
solution: Analytics
title: Interface de status detalhada
topic: Data workbench
uuid: c4d375d9-431f-4b0a-ba15-b7a10501b2e2
translation-type: tm+mt
source-git-commit: fd3afa80250d5ae20b7758ba840fd4d436545cf2

---


# Interface de status detalhada{#detailed-status-interface}

A interface de Status detalhado é útil para solucionar erros ou outros problemas com os computadores de servidor da Análise de big data.

Isso inclui quaisquer [!DNL Transform] perfis em execução nesses computadores ou [!DNL Report] computadores que sejam clientes do servidor da Análise de big data. Você pode acessar [!DNL Master Server] e [!DNL Query Server Detailed Status] interfaces pelo [!DNL Admin] menu. Para acessar a [!DNL Detailed Status] interface de outros computadores, no [!DNL Servers Manager], clique com o botão direito do mouse no nó do servidor para o qual deseja exibir o status e clique em **[!UICONTROL Detailed Status]**. Consulte [O Gerenciador](../../../home/c-get-started/c-admin-intrf/c-svrs-mgr.md#concept-2dfff1ca5bce470a8ee854ed57cbe5ba)De Servidores.

Para obter mais informações sobre o servidor do Análise de big data, consulte o Guia *de Instalação e Administração de Produtos para* Servidor.

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>Para atualizar as informações em uma [!DNL Detailed Status] interface, clique com o botão direito do mouse no **[!UICONTROL Detailed Status]** cabeçalho e clique em **[!UICONTROL Refresh]**.

A tabela a seguir lista as tarefas que podem ser concluídas usando a [!DNL Detailed Status] interface.

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
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Status</span>do componente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para exibir a quantidade de memória usada no computador </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Memory Status</span> &gt; <span class="uicontrol"> Address Space Load</span>. </p> <p>Para obter mais informações sobre como monitorar a carga do espaço de endereço, consulte o Guia <i>de Instalação e Administração de Produtos para</i>Servidor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para determinar se o computador está configurado para usar o switch /3GB </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Memory Status</span> &gt; <span class="uicontrol"> Process Address Space</span>. </p> <p>Se o campo <span class="wintitle"> Total</span> exibir mais de 3000000 KB, o computador será configurado para usar o Switch /3GB. </p> <p>Para obter mais informações sobre o switch /3GB, consulte o Guia <i>de Instalação e Administração de Produtos para</i>Servidor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para monitorar a quantidade de espaço em disco e memória usada para armazenar cada dimensão, bem como a usada para armazenar os nomes de seus elementos </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Desempenho</span> &gt; <span class="uicontrol"> Dimensões</span> &gt; Uso <span class="uicontrol"> do disco &gt;</span> &lt; <i>nome<span class="uicontrol"> do perfil&gt; ou em Desempenho</span></i><span class="uicontrol"></span> <span class="uicontrol"></span> <span class="uicontrol"></span> <i><span class="uicontrol"></span></i>&gt; Dimensões &gt; Uso de Memória &gt; &lt;nome do perfil&gt;. </p> <p>Os campos Uso <span class="wintitle"> de</span> disco fornecem o nome e a quantidade de espaço em disco (em MB) necessários para armazenar cada dimensão. Números grandes de uso de disco podem afetar negativamente os tempos de consulta, pois o servidor do Análise de big data precisa ler todos os dados para concluir as consultas relacionadas. Reduzir o uso do disco para uma dimensão pode reduzir o tempo necessário para concluir as consultas relacionadas. </p> <p>Os campos Uso <span class="wintitle"> de</span> memória fornecem o número de elementos em cada dimensão e a quantidade de memória necessária para armazenar a lista de nomes de elementos. Um grande número de elementos pode afetar negativamente a quantidade de memória que está sendo usada durante uma consulta, pois o servidor da Análise de big data precisa ler cada elemento. A redução do número de elementos em uma dimensão pode reduzir o tempo necessário para concluir consultas relacionadas. </p> <p>Exemplo: <code>+&nbsp;Performance
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
   <td colname="col1"> <p>Para monitorar o uso da CPU para os estágios no Processamento de log e Transformação </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Desempenho</span> &gt; Uso <span class="uicontrol"> da CPU &gt;</span> Processamento <span class="uicontrol"> de log &gt;</span> &lt; <i>nome<span class="uicontrol"> do perfil&gt;</span></i> <span class="uicontrol"></span> <span class="uicontrol"></span> <span class="uicontrol"></span><span class="uicontrol"></span>ou  Desempenho &gt;  Uso da CPU &gt; Transformação &gt; &lt;nome do perfil&gt;. </p> <p>Cada um desses conjuntos de campos fornece o Uso da CPU (em segundos) para cada um dos estágios no Processamento de log e Transformação. </p> <p>Exemplo: <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;CPU&nbsp;Usage&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName&nbsp;158.9&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Built-in&nbsp;158.1&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;13.0&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing\ProfileName&nbsp;0.8&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;0.8&nbsp;sec</code> </p> <p>O tempo necessário para concluir uma consulta é geralmente proporcional ao tamanho total de todas as suas dimensões. Depois de revisar o tamanho de cada dimensão, você pode avaliar se uma dimensão específica é útil o suficiente e usada com frequência o suficiente para justificar o custo de desempenho da dimensão. Caso contrário, você poderá excluir a dimensão no <span class="wintitle"> Gerenciador</span>de perfis.<p>Uma dimensão cuja lista de nomes de elementos é excessivamente grande (ou seja, mais de 128 MB) pode causar erros de "Memória insuficiente" mesmo se o uso total do espaço de endereço não estiver perto do limite. </p> <p>Além disso, se você estiver usando um cluster de servidores da Análise de big data, mas não estiver usando a normalização centralizada, uma dimensão cuja lista de nomes de elementos é grande terá um impacto significativo nos orçamentos de memória de envio. Para obter mais informações sobre a normalização centralizada, consulte o Guia <i>de configuração de</i>conjuntos de dados. Se a quantidade de memória necessária para armazenar todas as listas de nomes de elementos combinadas for superior a 100 MB em todos os servidores do cluster, você poderá receber erros de "Enviar orçamento de memória excedido" mesmo quando a atividade de consulta for leve. Por exemplo, se você tiver um cluster de quatro servidores com mais de 25 MB em cada servidor sendo usado para armazenar as listas de nomes de elementos, poderá receber erros. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para monitorar o tempo gasto no processamento e transformação de log </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Desempenho</span> &gt; Uso <span class="uicontrol"> da CPU &gt;</span> Processamento <span class="uicontrol"> de log &gt;</span> &lt; <i>nome<span class="uicontrol"> do perfil&gt;</span></i> <span class="uicontrol"></span> <span class="uicontrol"></span> <span class="uicontrol"></span> <i><span class="uicontrol"></span></i>ou  Desempenho &gt;  Uso da CPU &gt; Transformação &gt;&lt;nome do perfil&gt;. </p> <p>A revisão dos campos nessas seções permite identificar filtros e transformações que podem afetar negativamente a quantidade de tempo necessária para o processamento e transformação do log. Em seguida, você pode tomar decisões de design relacionadas a filtros e transformações individuais com longos tempos de processamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para monitorar o uso do espaço em disco e aumentar a velocidade da consulta </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Desempenho</span> &gt; <span class="uicontrol"> Campos</span> de processamento de log &gt; <i>&lt;<span class="uicontrol"> nome</span>do perfil&gt;</i>. </p> <p>Cada item de linha nesta seção corresponde a um parâmetro no arquivo <span class="filepath"> Log Processing.cfg</span> . A revisão desses campos permite que você veja quanta memória cada parâmetro está usando. Em seguida, você pode tomar decisões de design com relação a itens individuais que são bastante grandes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para determinar o tempo decorrido de reprocessamento ou transformação anterior </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Status</span> de processamento &gt; <i>&lt;<span class="uicontrol"> nome</span>do perfil&gt;</i> &gt; Histórico <span class="uicontrol"></span>do modo de processamento. </p> <p> 
     <ul id="ul_B7CC0DF54E004C72B220F928CF223F8E"> 
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">Tempo real - tempo em que o servidor do Análise de big data estava disponível para fazer consultas. </li> 
      <li id="li_3A3B490D70864A259780FC9FFC9AC15E">Entrada rápida - desta vez mais o tempo de Mesclagem rápida é o tempo total necessário para processar o conjunto de dados. </li> 
      <li id="li_B754C6DECD924170A15721EA4C942E3D">Mesclagem rápida - tempo total necessário para transformar o conjunto de dados. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para diagnosticar problemas de "Hora" </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Status</span> de processamento &gt; <i>&lt;<span class="uicontrol"> nome</span>do perfil&gt;</i> &gt; <span class="uicontrol"> A partir do tempo</span> &gt; <span class="uicontrol"> Fontes como de início</span>. </p> <p>A revisão das horas de cada fonte pode ajudar a determinar quais fontes podem estar afetando negativamente as Como geral. Você pode então resolver os problemas com essas fontes específicas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para estimar quanto tempo uma consulta em execução leva para ser concluída </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Execution Engine</span>. </p> <p>A revisão do campo Tempo <span class="wintitle"> de varredura de</span> dados fornece uma estimativa do tempo necessário para a conclusão de uma consulta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para listar todos os perfis disponíveis neste computador e detalhes sobre seu status </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Perfis</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para exibir o status da Replicação </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Status</span>do componente. </p> <p>Verifique o status do componente Replicar. Se Replicação estiver em execução, OK será exibido. Se o componente Replicate falhar, uma mensagem de erro será exibida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para exibir <span class="wintitle"> o status do Servidor</span> de Relatório para um computador do <span class="keyword"> Relatório</span> que se conecta ao servidor da Análise de big data </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Status</span>do Servidor de Relatórios. </p> <p>Esta seção da interface de Status <span class="wintitle"> Detalhado inclui uma cópia do arquivo</span> Report Server.cfg <span class="filepath"></span> , informações sobre o número de relatórios que estão sendo executados (Fatia Atual) e informações sobre o erro mais recente (Último Erro). </p> <p>Para obter etapas para editar o arquivo <span class="filepath"> Report Server.cfg</span> , consulte o Guia <i></i>de relatórios da Análise de big data. </p> <p> <p>Observação: Se a seção Status <span class="wintitle"> do Servidor de</span> Relatório não for exibida na interface de Status <span class="wintitle"> Detalhado, talvez seja necessário configurar o servidor do Análise de big data para exibir o Status</span> do <span class="wintitle"></span>Servidor de Relatório. Para obter etapas, consulte o Guia <i></i>de relatórios da Análise de big data. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para exibir informações de uso de memória para Transformar </p> </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Status</span> de processamento &gt; <span class="uicontrol"> Transformar</span>. </p> <p>Para obter mais informações sobre a Transformação, consulte o Guia <i>de Instalação e Administração de Produtos</i> de Servidor e o Guia <i>de Configuração de</i>Conjunto de Dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para salvar a interface de Status <span class="wintitle"> Detalhado como um arquivo</span> *.cfg <span class="filepath"></span> que pode ser aberto em um editor de texto como o Bloco de notas ou distribuído para outras pessoas </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse no cabeçalho Status <span class="uicontrol"> detalhado e clique em</span> Salvar cópia como <span class="uicontrol"></span>. </p> <p>Observação:  <p>Clicar com o botão direito do mouse no cabeçalho Status <span class="uicontrol"> Detalhado e clicar em</span> Salvar <span class="uicontrol"> no nome</span> /Status/ do <i>servidor não funciona na interface</i>Status <span class="wintitle"></span> Detalhado. A seguinte mensagem de erro é exibida: </p> <p>Não é possível salvar /Status/. 403 Proibido </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para exibir <span class="uicontrol"> a métrica Linhas por Fonte</span> de Log </p> </td> 
   <td colname="col2"> <p>Se a métrica Linhas por Fonte de Log precisar ser relatada em Status Detalhado, o Administrador da Análise de big data deverá definir a "ID da Fonte de Log" e fornecer um nome exclusivo no Log Processing.cfg do Perfil Personalizado. </p> </td> 
  </tr> 
 </tbody> 
</table>

