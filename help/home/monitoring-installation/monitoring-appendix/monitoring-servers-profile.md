---
description: As seguintes dimensões estão disponíveis para uso no perfil de Status do Servidor da análise de big data.
solution: Analytics
title: Dimensões no perfil Status do Servidor da Análise de big data
topic: Data workbench
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensões no perfil Status do Servidor da Análise de big data{#dimensions-in-the-data-workbench-server-status-profile}

As seguintes dimensões estão disponíveis para uso no perfil de Status do Servidor da análise de big data.

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Servidor</b> </td> 
   <td colname="col2"> Construída a partir do campo x-trackingid, essa dimensão contável representa os Servidores que estão executando a análise de big data no momento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versão do agente</b> </td> 
   <td colname="col2"> O valor cs-uri-query(af) é usado para essa Dimensão Simples. É o Último valor Não em branco para um Servidor. Isso exibe a data e a hora de criação das versões do agente de monitoramento em execução. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Qualquer reprocessamento de perfil</b> </td> 
   <td colname="col2"> O campo cs-uri-query(aa) é usado para essa Dimensão Numérica, é o valor da Última Linha para um determinado Servidor, condicional em cs-uri-query(k) não está vazio. Essa dimensão é usada para indicar se algum perfil está sendo reprocessado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem da Linha de Capacidade</b> </td> 
   <td colname="col2"> O campo cs-uri-query(r) é usado para essa Dimensão Numérica, é o valor da Última Linha para um determinado Servidor, condicional em cs-uri-query(k) não está vazio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem do Tamanho da Capacidade</b> </td> 
   <td colname="col2"> O campo cs-uri-query(n) é usado para essa Dimensão Numérica, é o valor da Última Linha para um determinado Servidor, condicional em cs-uri-query(k) não está vazio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nome comum</b> </td> 
   <td colname="col2"> O campo sc-ur-query(am) é usado para essa Dimensão Simples, é o valor do Último valor Não em branco para um determinado Servidor. Ele exibe o Nome comum dos servidores que estão sendo monitorados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Êxito na verificação do componente</b> </td> 
   <td colname="col2"> O campo cs-uri-query(v) é usado para essa Dimensão Simples, é o valor da Última Linha para um determinado Servidor. Essa dimensão verifica os componentes do servidor para verificar se eles estão funcionando corretamente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Componentes em erro</b> </td> 
   <td colname="col2"> Uma transformação de Linhas cruzadas pega o valor da Última linha da consulta cs-uri(ao) e a copia no campo x-components-in-error. Essa dimensão Muitos para Muitos exibe qualquer componente com erro nos servidores que estão sendo monitorados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ambiente</b> </td> 
   <td colname="col2">O valor cs-uri-query(c) é usado para a ID de ambiente. A última linha de um bloco é usada como o valor da dimensão. Esta Dimensão Simples exibirá o Ambiente no qual seus Servidores estão sendo executados (desde que esteja configurada corretamente). <p><p>Observação:  Essa dimensão é definida em insight_monitor_agent.cfg. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Estimativa de Dekasegundos de Varredura</b> </td> 
   <td colname="col2"> O campo x-estimated-sweep-dekasegundo é usado nesta Dimensão Numérica. Esse é o tempo de varredura estimado dos servidores dividido por dez (resolução reduzida de medição de varredura para aumentar o tamanho da dimensão). <p><p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> O valor cs-uri-query(b) é usado para essa dimensão. O valor da dimensão Simples é a Última Linha para um Bloco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Último Ping</b> </td> 
   <td colname="col2"> x-last-ping é x-unixtime dividido por 10 (para acomodar restrições de tamanho de dimensões numéricas). O último ping é a última linha de um determinado bloco e representa a última vez que o agente de monitoramento registrou a integridade do sistema. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Média de carga</b> </td> 
   <td colname="col2"> Esta é uma dimensão numérica que usa a Última linha para um determinado valor de cs-uri-query(i) do servidor. Ela está condicionada se cs-uri-query(k) não estiver vazia. Essa dimensão é usada para calcular a carga média nos servidores no sistema que está sendo monitorado. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem do Arquivo de Página de Memória</b> </td> 
   <td colname="col2"> Esta é uma dimensão numérica que usa a Última linha para um determinado valor de cs-uri-query(o) do servidor. Ela está condicionada se cs-uri-query(k) não estiver vazia. Essa dimensão é usada para calcular a porcentagem de uso da memória do arquivo de página. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Total de megabits físicos de memória</b> </td> 
   <td colname="col2"> Esta é uma dimensão Numérica que usa a Última linha para um determinado valor de cs-uri-query(ag) do servidor. Ela está condicionada se cs-uri-query(k) não estiver vazia. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem física da memória</b> </td> 
   <td colname="col2"> Esta é uma dimensão Numérica que usa a Última linha para um determinado valor de cs-uri-query(ag) do servidor. Ela está condicionada se cs-uri-query(k) não estiver vazia. Essa dimensão é usada para calcular a porcentagem de uso de memória física de cada Servidor. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de Consulta de Memória</b> </td> 
   <td colname="col2"> Esta é uma dimensão numérica que usa a Última linha para um determinado valor de consulta cs-uri-query(s) do servidor. Ela está condicionada se cs-uri-query(k) não estiver vazia. Essa dimensão é usada para calcular a porcentagem do uso da memória de consulta de cada Servidor. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Conexões de rede</b> </td> 
   <td colname="col2"> Esta é uma dimensão Numérica usando a Última linha para um determinado valor de cs-uri-query(q) do servidor. Ela está condicionada se cs-uri-query(k) não estiver vazia. Isso é usado para mostrar o número de conexões de rede que existem para um determinado servidor. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Centisegundos de latência da pesquisa</b> </td> 
   <td colname="col2"> Essa dimensão é usada para calcular a latência da pesquisa. O valor cs-uri-query(m) é dividido por 10 para reduzir o tamanho da dimensão e copiado no campo x-poll-latency-centisegundos. Esta é uma dimensão Numérica que utiliza a Última linha para um determinado servidor. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Sucesso na verificação rápida</b> </td> 
   <td colname="col2"> Esta é uma dimensão Simples criada a partir do valor cs-uri-query(g) da Última Linha para um determinado Servidor. É usado para calcular a métrica de verificação rápida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de Espaço Temporário do Banco de Dados</b> </td> 
   <td colname="col2"> A última linha do valor cs-uri-query(an) é copiada para o campo x-temp-db-space-percent. Esta é uma Dimensão Numérica que é usada para calcular a porcentagem do espaço temporário de DB usado em um determinado servidor. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versão do Insight</b> </td> 
   <td colname="col2"> O valor cs-uri-query(ab) é usado para essa Dimensão Simples. É o Último valor Não em branco para um Servidor. Isso exibe as versões do servidor de análise de big data em execução em cada servidor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Grupo</b> </td> 
   <td colname="col2"> Agrupamento de palavras que oferece outra maneira de filtrar o conjunto de dados resultante. <p>Observação:  Essa dimensão é definida em insight_monitor_agent.cfg. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Métricas</b> </td> 
   <td colname="col2"> A seguir, são mostradas as métricas incluídas no Perfil de monitoramento de perfil da análise de big data e como elas são derivadas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Capacidade geral</b> </td> 
   <td colname="col2"> Esta é a métrica Tamanho da capacidade vezes dois mais a métrica Linha da capacidade dividida por 3. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Linha de capacidade</b> </td> 
   <td colname="col2"> Essa é a soma da porcentagem da linha de capacidade para cada servidor dividida pela métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tamanho da capacidade</b> </td> 
   <td colname="col2"> Essa é a soma da porcentagem do tamanho da capacidade para cada servidor dividida pela métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Verificação do componente</b> </td> 
   <td colname="col2"> Este é o número de Servidores em que a Verificação de Componentes é igual a um, dividido pelo Servidor em que o Serviço é DPU ou FSU, todos multiplicados por 100 (para torná-lo uma porcentagem). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Disco "x"</b> </td> 
   <td colname="col2"> As métricas de Disco são calculadas utilizando a soma da porcentagem de uso de disco para cada servidor, dividida pela métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Estimativa de minutos de varredura</b> </td> 
   <td colname="col2"> Essa é a soma dos Dekasegundos de Varredura Estimados para cada Servidor, dividida pela métrica Servidores, onde os Dekasegundos de Varredura Estimada são maiores que zero, todos divididos por 6. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Hora do último ping</b> </td> 
   <td colname="col2"> A soma do Último Ping para cada Bloco dividida por Blocos e depois multiplicada por 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Carregar</b> </td> 
   <td colname="col2"> Essa é a soma da Média de Carga para cada Servidor, dividida pela métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Arquivo de página de memória</b> </td> 
   <td colname="col2"> Essa é a soma da porcentagem do arquivo da página de memória para cada servidor, dividida pela métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Memória física</b> </td> 
   <td colname="col2"> Essa é a soma da porcentagem física da memória para cada servidor, dividida pela métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Consulta de memória</b> </td> 
   <td colname="col2"> Essa é a soma da porcentagem de consulta de memória para cada servidor, dividida pela métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Conexões de rede</b> </td> 
   <td colname="col2"> Essa é a soma das Conexões de rede para cada Servidor dividida pela métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Milissegundos de latência da pesquisa</b> </td> 
   <td colname="col2"> Essa é a soma dos centésimos de latência de pesquisa para cada servidor, dividida pela métrica Servidores, todos multiplicados por 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Verificação rápida</b> </td> 
   <td colname="col2"> Este é o número de Servidores onde o sucesso da verificação rápida é igual a um, dividido pela métrica Servidores, todos multiplicados por 100. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Servidores</b> </td> 
   <td colname="col2"> Essa é a soma de um para cada Servidor, ou o número total de Servidores monitorados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>DB temporário</b> </td> 
   <td colname="col2"> Essa é a soma da porcentagem de espaço temporário no banco de dados para cada servidor, dividida pela métrica Servidores. </td> 
  </tr> 
 </tbody> 
</table>

