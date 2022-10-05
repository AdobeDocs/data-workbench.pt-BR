---
description: As seguintes dimensões estão disponíveis para uso no perfil de status do servidor do Data Workbench.
title: Dimensões no perfil de status do servidor do Data Workbench
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
exl-id: 002f6b95-f151-41d9-ae28-9c01c1f621ee
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 1%

---

# Dimensões no perfil de status do servidor do Data Workbench{#dimensions-in-the-data-workbench-server-status-profile}

{{eol}}

As seguintes dimensões estão disponíveis para uso no perfil de status do servidor do Data Workbench.

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Servidor</b> </td> 
   <td colname="col2"> Criada a partir do campo x-trackingid , essa dimensão contável representa os Servidores que estão executando o Data Workbench no momento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versão do agente</b> </td> 
   <td colname="col2"> O valor cs-uri-query(af) é usado para este Dimension Simple. É o último valor não em branco de um servidor. Isso exibe a data e a hora de criação das versões do agente de monitoramento em execução. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Qualquer reprocessamento de perfil</b> </td> 
   <td colname="col2"> O campo cs-uri-query(aa) é usado para esse Dimension numérico, é o valor da Última Linha para um determinado Servidor, condicional para cs-uri-query(k) não está vazio. Essa dimensão é usada para indicar se algum perfil está reprocessando. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem da Linha de Capacidade</b> </td> 
   <td colname="col2"> O campo cs-uri-query(r) é usado para esse Dimension numérico, é o valor da Última Linha para um determinado Servidor, condicional para cs-uri-query(k) não está vazia. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem do Tamanho da Capacidade</b> </td> 
   <td colname="col2"> O campo cs-uri-query(n) é usado para esse Dimension numérico, é o valor da Última Linha para um determinado Servidor, condicional para cs-uri-query(k) não está vazia. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nome comum</b> </td> 
   <td colname="col2"> O campo sc-ur-query(am) é usado para esse Dimension Simples, é o valor do último não vazio para um determinado servidor. Ele exibe o Common Name dos servidores que estão sendo monitorados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Êxito na verificação do componente</b> </td> 
   <td colname="col2"> O campo cs-uri-query(v) é usado para esse Dimension Simples, é o valor da Última Linha para um determinado Servidor. Essa dimensão verifica os componentes do servidor para verificar se estão funcionando corretamente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Componentes no erro</b> </td> 
   <td colname="col2"> Uma transformação Crossrows pega o valor de Last Row do cs-uri-query(ao) e o copia no campo x-components-in-error . Essa dimensão Muitos para muitos exibe todos os componentes com erro nos servidores que estão sendo monitorados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ambiente</b> </td> 
   <td colname="col2">O valor cs-uri-query(c) é usado para a ID do ambiente. A Última linha de um bloco é usada como o valor da dimensão. Este Dimension Simples exibirá o Ambiente no qual seus Servidores estão sendo executados (desde que esteja configurado corretamente). <p><p>Observação: Essa dimensão é definida em insight_monitor_agent.cfg. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Estimativa de segundos de varredura</b> </td> 
   <td colname="col2"> O campo x-estimated-sweep-dekaseconds é usado neste Dimension numérico. Esse é o tempo estimado de varredura dos servidores dividido por dez (resolução reduzida de medição de varredura para tornar a dimensão mais razoavelmente dimensionada). <p><p>Observação: Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> O valor cs-uri-query(b) é usado para essa dimensão. O valor da dimensão Simples é a Última Linha para um Bloco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Último ping</b> </td> 
   <td colname="col2"> O x-last-ping é o x-unixtime dividido por 10 (para acomodar restrições de tamanho de dimensões numéricas). Último Ping é a Última Linha de um Bloco específico e representa a última vez que o agente de monitoramento registrou o funcionamento do sistema. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Carga média</b> </td> 
   <td colname="col2"> Esta é uma dimensão Numérica usando a Última linha para um determinado valor cs-uri-query(i) de servidor. Está condicionado em cs-uri-query(k) não estar vazio. Essa dimensão é usada para calcular a carga média nos servidores do sistema que está sendo monitorado. <p>Observação: Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem do Arquivo da Página de Memória</b> </td> 
   <td colname="col2"> Esta é uma dimensão Numérica usando a Última linha para um determinado valor cs-uri-query(o) de servidor. Está condicionado em cs-uri-query(k) não estar vazio. Essa dimensão é usada para calcular a porcentagem do uso de memória do arquivo de página. <p>Observação: Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Total de megabytes físicos de memória</b> </td> 
   <td colname="col2"> Esta é uma dimensão Numérica usando a Última linha para um determinado valor cs-uri-query(ag) de servidor. Está condicionado em cs-uri-query(k) não estar vazio. <p>Observação: Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem física da memória</b> </td> 
   <td colname="col2"> Esta é uma dimensão Numérica usando a Última linha para um determinado valor cs-uri-query(ag) de servidor. Está condicionado em cs-uri-query(k) não estar vazio. Essa dimensão é usada para calcular a porcentagem do uso de memória física de cada Servidor. <p>Observação: Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de Consulta de Memória</b> </td> 
   <td colname="col2"> Esta é uma dimensão Numérica usando a Última linha para um valor de consulta cs-uri-s de um determinado servidor. Está condicionado em cs-uri-query(k) não estar vazio. Essa dimensão é usada para calcular a porcentagem do uso de memória de consulta de cada Servidor. <p>Observação: Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Conexões de rede</b> </td> 
   <td colname="col2"> Esta é uma dimensão Numérica usando a Última linha para um determinado valor cs-uri-query(q) de servidor. Está condicionado em cs-uri-query(k) não estar vazio. Isso é usado para mostrar o número de conexões de rede que existem para um determinado servidor. <p>Observação: Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segundos da Latência da Pesquisa</b> </td> 
   <td colname="col2"> Essa dimensão é usada para calcular a latência da pesquisa. O valor cs-uri-query(m) é dividido por 10 para reduzir o tamanho da dimensão e copiado para o campo x-poll-latency-centiseconds. Esta é uma dimensão numérica que utiliza a Última linha para um determinado servidor. <p>Observação: Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Sucesso da verificação rápida</b> </td> 
   <td colname="col2"> Esta é uma dimensão Simples criada a partir do valor cs-uri-query(g) da Última Linha para um determinado Servidor. É usada para calcular a métrica de verificação rápida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de Espaço de Banco de Dados Temp</b> </td> 
   <td colname="col2"> A última linha do valor cs-uri-query(an) é copiada para o campo x-temp-db-space-percentage . Este é um Dimension numérico usado para calcular a porcentagem do espaço de banco de dados Temp usado em um determinado servidor. <p>Observação: Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versão do Insight</b> </td> 
   <td colname="col2"> O valor cs-uri-query(ab) é usado para esse Dimension Simple. É o último valor não em branco de um servidor. Isso exibe as versões do servidor do Data Workbench em execução em cada servidor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Grupo</b> </td> 
   <td colname="col2"> Agrupamento de palavra que oferece outra maneira de filtrar o conjunto de dados resultante. <p>Observação: Essa dimensão é definida em insight_monitor_agent.cfg. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Métricas</b> </td> 
   <td colname="col2"> A seguir são listadas as métricas incluídas no Perfil de monitoramento de perfil do Data Workbench e como elas são derivadas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Capacidade geral</b> </td> 
   <td colname="col2"> Essa é a métrica Tamanho da capacidade vezes dois mais a métrica Linha de capacidade dividida por 3. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Linha de Capacidade</b> </td> 
   <td colname="col2"> Essa é a soma da Porcentagem da Linha de Capacidade para cada Servidor dividida pela métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tamanho da capacidade</b> </td> 
   <td colname="col2"> Esta é a soma da Porcentagem de Tamanho da Capacidade para cada Servidor dividida pela métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Verificação do componente</b> </td> 
   <td colname="col2"> Este é o número de Servidores onde o Sucesso de Verificação de Componentes é igual a um, dividido pelo Servidor onde o Serviço é DPU ou FSU, todos multiplicados por 100 (para torná-lo uma porcentagem). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Disco "x"</b> </td> 
   <td colname="col2"> As métricas de Disco são calculadas considerando a soma da Porcentagem de Uso de Disco para cada Servidor, dividida pela métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Estimativa de minutos de varredura</b> </td> 
   <td colname="col2"> Essa é a soma dos Dekaseconds de Varredura Estimados para cada Servidor, dividida pela métrica Servidores, onde os Dekaseconds de Varredura Estimada são maiores que zero, todos divididos por 6. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Hora do último ping</b> </td> 
   <td colname="col2"> A soma do Último Ping para cada Bloco dividido por Blocos, em seguida multiplicado por 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Carregar</b> </td> 
   <td colname="col2"> Esta é a soma da Média de Carga para cada Servidor, dividida pela métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Arquivo da página de memória</b> </td> 
   <td colname="col2"> Essa é a soma da porcentagem de arquivo da página de memória para cada servidor, dividida pela métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Memória física</b> </td> 
   <td colname="col2"> Esta é a soma da Porcentagem Física de Memória para cada Servidor, dividida pela métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Consulta de memória</b> </td> 
   <td colname="col2"> Essa é a soma da Porcentagem de Consulta de Memória para cada Servidor, dividida pela métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Conexões de rede</b> </td> 
   <td colname="col2"> Soma das Conexões de Rede para cada Servidor dividida pela métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Milissegundos de Latência da Pesquisa</b> </td> 
   <td colname="col2"> Essa é a soma dos centavos da latência de pesquisa para cada servidor, dividida pela métrica Servidores, todos multiplicados por 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Verificação rápida</b> </td> 
   <td colname="col2"> Esse é o número de Servidores em que o sucesso da verificação rápida é igual a um, dividido pela métrica Servidores, sendo todos multiplicados por 100. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Servidores</b> </td> 
   <td colname="col2"> É a soma de um para cada Servidor ou o número total de Servidores monitorados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Banco de dados Temp</b> </td> 
   <td colname="col2"> Essa é a soma da Porcentagem de Espaço de Banco de Dados Temp para cada Servidor, dividida pela métrica Servidores. </td> 
  </tr> 
 </tbody> 
</table>
