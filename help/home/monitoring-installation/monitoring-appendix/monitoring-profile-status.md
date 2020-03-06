---
description: As seguintes dimensões estão disponíveis para uso no perfil Status do perfil da análise de big data.
solution: Analytics
title: Dimensões no perfil Status do perfil da Análise de big data
topic: Data workbench
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensões no perfil Status do perfil da Análise de big data{#dimensions-in-the-data-workbench-profile-status-profile}

As seguintes dimensões estão disponíveis para uso no perfil Status do perfil da análise de big data.

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Bloco</b> </td> 
   <td colname="col2"> Esta é a única contável nesta configuração e existe como raiz para todas as dimensões. Um bloco pode ser considerado um servidor. Está usando o campo x-trackingid. A ID de bloco é um hash do nome do servidor mais o nome do host, portanto haverá aproximadamente um bloco por servidor por perfil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Minutos de atraso</b> </td> 
   <td colname="col2"> cs-uri-query(bi) é colocado no campo x-as-of-delay-minutos e arredondado para o minuto mais próximo. A partir de Atraso de minutos é uma dimensão numérica que retira a Última linha de x-as-de-atraso-minutos para um bloco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ambiente</b> </td> 
   <td colname="col2"> O valor cs-uri-query(c) é usado para a ID de ambiente. A última linha de um bloco é usada como o valor da dimensão. Esta Dimensão Simples exibirá o Ambiente no qual seus Servidores estão sendo executados (desde que esteja configurada corretamente). <p>Isso pode ser definido no arquivo insight_monitor_agent.cfg </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaBytes de Entrada Rápida por Minuto</b> </td> 
   <td colname="col2"> O valor cs-uri-query(bj) é usado para essa dimensão. A Última linha de um bloco é usada como o valor da dimensão. Se o conjunto de dados estiver em Fast Input, esse valor de Dimensão Numérica exibirá o MB por minuto em que o sistema está inserindo dados. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaBytes de Mesclagem Rápida por Minuto</b> </td> 
   <td colname="col2">O valor cs-uri-query(bk) é usado para essa dimensão. A última linha de um bloco é usada como o valor da dimensão. Se o conjunto de dados estiver na Mesclagem rápida, o valor dessa dimensão numérica exibirá o MB por minuto em que o sistema está se mesclando. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>GigaBytes de campo</b> </td> 
   <td colname="col2"> O valor cs-uri-query(bg) é usado para essa dimensão. O valor é dividido por 1000 e arredondado para o número inteiro mais próximo. O valor desta Dimensão Numérica exibirá a quantidade de espaço que os Campos no conjunto de dados estão usando. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> O valor cs-uri-query(b) é usado para essa dimensão. O valor da dimensão Simples é a Última Linha para um Bloco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Último Ping</b> </td> 
   <td colname="col2">x-last-ping é x-unixtime dividido por 10 (para acomodar restrições de tamanho de dimensões numéricas). O último ping é a última linha de um determinado bloco e representa a última vez que o agente de monitoramento registrou a integridade do sistema. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de leitura de registro</b> </td> 
   <td colname="col2">o valor cs-uri-query(be) é usado para essa dimensão numérica. É a Última Linha para um Bloco específico. Essa dimensão é usada para calcular a porcentagem de logs que estão sendo lidos. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID do modo de processamento</b> </td> 
   <td colname="col2"> O valor cs-uri-query(bb) é usado para essa Dimensão Simples. É a Última Linha para um Bloco específico. A ID do modo de processamento permite que você veja em qual modo de processamento o sistema está (Fast Input, Fast Merge, Tempo real). <p>Observação:  Essa dimensão é ocultada e re-exposta com valores amigáveis no modo de processamento de dimensão do cliente. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Processamento parado</b> </td> 
   <td colname="col2"> O campo parado de x-processing é criado por meio de várias condições para indicar se o perfil está em execução ou não no momento. É uma dimensão simples. <p>Observação:  Essa dimensão funciona melhor quando há um grande número de registros de entrada para distribuição justa entre as DPUs. Por exemplo, se houver apenas um arquivo grande carregado por dia, a análise de big data pode parecer "parada" por uma hora ou mais, resultando em uma leitura falsa positiva dessa dimensão. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Perfil</b> </td> 
   <td colname="col2"> O valor cs-uri-query(ba) é usado para essa Dimensão Simples. Essa dimensão exibe os nomes dos perfis que estão sendo monitorados no momento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fonte mais atrasada</b> </td> 
   <td colname="col2"> A última linha de cs-uri-query(bl) é copiada para o campo x-source-furthest-behind. A Dimensão simples usa a Última linha para um determinado Bloco. Essa dimensão exibe o quando ocorreu o último contato com uma fonte de dados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de transformação</b> </td> 
   <td colname="col2"> o valor cs-uri-query(bf) é usado para essa dimensão numérica. É a Última Linha para um Bloco específico. Essa dimensão é usada para calcular a porcentagem da transformação completa de dados. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensões de tempo</b> </td> 
   <td colname="col2"> Hora, Dia, Semana, Mês, Hora do dia e Dia da semana são todos derivados do campo x-timestamp. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Grupo</b> </td> 
   <td colname="col2"> Agrupamento de palavras que oferece outra maneira de filtrar o conjunto de dados resultante. Definido no arquivo insight_monitor_agent.cfg. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Métricas</b> </td> 
   <td colname="col2"> A seguir, são mostradas as métricas incluídas no Perfil de monitoramento de perfil da análise de big data e como elas são derivadas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Em minutos de atraso</b> </td> 
   <td colname="col2"> Essa métrica é a soma dos minutos de início de atraso para cada bloco e dividida pela métrica Blocos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Em segundos de atraso</b> </td> 
   <td colname="col2"> Essa métrica é a soma dos segundos de atraso de início de cada bloco e dividida pelo número total de blocos. (A partir de Segundos de Atraso, a Dimensão não está configurada na caixa) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Blocos</b> </td> 
   <td colname="col2"> Soma um para cada bloco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Entrada rápida MB por minuto</b> </td> 
   <td colname="col2"> A soma de MegaBytes de Entrada Rápida por Minuto para cada Bloco dividida pelo número de Blocos quando MegaBytes de Entrada Rápida por Minuto é maior que zero. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mesclagem rápida MB por minuto</b> </td> 
   <td colname="col2"> A soma de MegaBytes de Mesclagem Rápida por Minuto para cada Bloco dividida pelo número de Blocos quando MegaBytes de Mesclagem Rápida por Minuto é maior que zero. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>GigaBytes de campo</b> </td> 
   <td colname="col2"> A soma dos Gigabytes de campo para cada bloco dividida pela métrica Blocos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Última Idade do Ping</b> </td> 
   <td colname="col2"> A Data de início menos a Hora do último ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Hora do último ping</b> </td> 
   <td colname="col2"> A soma do Último Ping para cada Bloco dividida por Blocos e depois multiplicada por 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Leitura do registro</b> </td> 
   <td colname="col2"> Quando a porcentagem de leitura do log for maior que zero, a leitura do log será a soma da porcentagem de leitura do log para cada bloco, dividida pela métrica Blocos, dividida por 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Processamento parado</b> </td> 
   <td colname="col2"> A soma da Dimensão de Processamento Estacionado para cada Bloco, dividida pela métrica Blocos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Transformação</b> </td> 
   <td colname="col2"> A soma da porcentagem de transformação para cada bloco dividida pela métrica Blocos, quando a porcentagem de transformação é maior que zero, todos divididos por 10. </td> 
  </tr> 
 </tbody> 
</table>

