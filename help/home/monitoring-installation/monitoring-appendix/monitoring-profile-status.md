---
description: As seguintes dimensões estão disponíveis para uso no perfil de status do perfil do Data Workbench.
title: Dimensões no perfil de status do perfil do Data Workbench
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
exl-id: 57b3ff16-26db-4292-819b-f6cd8e024c2a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 2%

---

# Dimensões no perfil de status do perfil do Data Workbench{#dimensions-in-the-data-workbench-profile-status-profile}

As seguintes dimensões estão disponíveis para uso no perfil de status do perfil do Data Workbench.

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Bloco</b> </td> 
   <td colname="col2"> Essa é a única contável nessa configuração e existe como a raiz de todas as dimensões. Um bloco pode ser considerado um servidor. Ele está usando o campo x-trackingid . A ID de bloco é um hash do nome do servidor mais o nome do host, portanto, haverá aproximadamente um bloco por servidor por perfil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Atraso das atas</b> </td> 
   <td colname="col2"> cs-uri-query(bi) é colocado no campo x-as-of-delay-minutes e arredondado para o minuto mais próximo. A partir de Atraso de minutos é uma dimensão numérica que obtém a Última linha de x como atraso-minutos para um bloco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ambiente</b> </td> 
   <td colname="col2"> O valor cs-uri-query(c) é usado para a ID do ambiente. A Última linha de um bloco é usada como o valor da dimensão. Este Dimension Simples exibirá o Ambiente no qual seus Servidores estão sendo executados (desde que esteja configurado corretamente). <p>Isso pode ser definido no arquivo insight_monitor_agent.cfg </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaBytes de Entrada Rápida por Minuto</b> </td> 
   <td colname="col2"> O valor cs-uri-query(bj) é usado para essa dimensão. A Última linha de um bloco é usada como o valor da dimensão. Se o conjunto de dados estiver em Fast Input, esse valor numérico será exibido na MB por minuto, no qual o sistema está inserindo dados. <p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaBytes de Mesclagem Rápida por Minuto</b> </td> 
   <td colname="col2">O valor cs-uri-query(bk) é usado para essa dimensão. A Última linha de um bloco é usada como o valor da dimensão. Se o conjunto de dados estiver em Fast Merge Este valor Numérico de Mesclagem exibirá o MB por minuto no qual o sistema está se mesclando. <p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Campo GigaBytes</b> </td> 
   <td colname="col2"> O valor cs-uri-query(bg) é usado para essa dimensão. O valor é dividido por 1000 e arredondado para o número inteiro mais próximo. Esse valor Numérico de Dimension exibirá a quantidade de espaço que os Campos no conjunto de dados estão usando. <p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> O valor cs-uri-query(b) é usado para essa dimensão. O valor da dimensão Simples é a Última Linha de um Bloco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Último ping</b> </td> 
   <td colname="col2">O x-last-ping é o x-unixtime dividido por 10 (para acomodar restrições de tamanho de dimensões numéricas). Último Ping é a Última Linha de um Bloco específico e representa a última vez que o agente de monitoramento registrou o funcionamento do sistema. <p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de Leitura de Log</b> </td> 
   <td colname="col2">o valor cs-uri-query(be) é usado para essa dimensão numérica. É a última linha de um determinado bloco. Essa dimensão é usada para calcular a porcentagem de logs que estão sendo lidos. <p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID do modo de processamento</b> </td> 
   <td colname="col2"> O valor cs-uri-query(bb) é usado para esse Dimension Simple. É a última linha de um determinado bloco. A ID do modo de processamento permite que você veja em que modo de processamento o sistema está (Fast Input, Fast Merge, Tempo Real). <p>Observação:  Essa dimensão é oculta e re-exposta com valores amigáveis na dimensão do cliente Modo de processamento. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Processamento interrompido</b> </td> 
   <td colname="col2"> O campo paralisado de processamento x é criado por meio de várias condições para indicar se o perfil está ou não em execução no momento. É uma dimensão simples. <p>Observação:  Essa dimensão funciona melhor quando há um grande número de logs de entrada para distribuir de forma justa entre as DPUs. Se houver, por exemplo, apenas um arquivo grande carregado por dia, o Data Workbench poderá parecer "parado" por uma hora ou mais, resultando em uma leitura falso positiva dessa dimensão. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Perfil</b> </td> 
   <td colname="col2"> O valor cs-uri-query(ba) é usado para esse Dimension Simple. Essa dimensão exibe os nomes dos perfis que estão sendo monitorados no momento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fonte mais atrasada</b> </td> 
   <td colname="col2"> A última linha de cs-uri-query(bl) é copiada para o campo x-source-furthest-behind. O Dimension Simple usa a Última linha para um determinado Bloco. Essa dimensão exibe o quando o último contato com uma fonte de dados ocorreu. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de transformação</b> </td> 
   <td colname="col2"> o valor cs-uri-query(bf) é usado para essa dimensão numérica. É a última linha de um determinado bloco. Essa dimensão é usada para calcular a porcentagem da transformação completa de dados. <p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensões de tempo</b> </td> 
   <td colname="col2"> Hora, dia, semana, mês, hora do dia e dia da semana são todos derivados do campo x-timestamp. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Grupo</b> </td> 
   <td colname="col2"> Agrupamento de palavra que oferece outra maneira de filtrar o conjunto de dados resultante. Defina no arquivo insight_monitor_agent.cfg. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Métricas</b> </td> 
   <td colname="col2"> A seguir são listadas as métricas incluídas no Perfil de monitoramento de perfil do Data Workbench e como elas são derivadas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Em Minutos De Atraso</b> </td> 
   <td colname="col2"> Essa métrica é a soma dos Minutos de atraso de início para cada Bloco e, em seguida, dividida pela métrica Blocos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>A Partir De Segundos De Atraso</b> </td> 
   <td colname="col2"> Essa métrica é a soma dos segundos de atraso de início para cada bloco e dividida pelo número total de blocos. (Dimension a partir de Delay Seconds não configurado para uso imediato) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Blocos</b> </td> 
   <td colname="col2"> Soma um para cada Bloco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Entrada Rápida MB por Minuto</b> </td> 
   <td colname="col2"> A soma dos megabytes de entrada rápida por minuto para cada bloco dividido pelo número de blocos quando os megabytes de entrada rápida por minuto são maiores que zero. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mesclagem rápida MB por minuto</b> </td> 
   <td colname="col2"> A soma dos megabytes de unificação rápida por minuto para cada bloco dividido pelo número de blocos quando os megabytes de unificação rápida por minuto são maiores que zero. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Campo GigaBytes</b> </td> 
   <td colname="col2"> A soma de Gigabytes de campo para cada Bloco dividido pela métrica Blocos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Última idade do ping</b> </td> 
   <td colname="col2"> A Hora de início menos a Hora do último ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Hora do último ping</b> </td> 
   <td colname="col2"> A soma do Último Ping para cada Bloco dividido por Blocos, em seguida multiplicado por 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Leitura de registro</b> </td> 
   <td colname="col2"> Quando a Porcentagem de Leitura de Log é maior que zero, a Leitura de Log é a soma da Porcentagem de Leitura de Log para cada Bloco, dividida pela métrica Blocos, sendo todos divididos por 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Processamento interrompido</b> </td> 
   <td colname="col2"> A soma do Dimension Processamento Paralisado para cada Bloco, dividida pela métrica Blocos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Transformação</b> </td> 
   <td colname="col2"> A soma da Porcentagem de transformação para cada Bloco dividido pela métrica Blocos, quando a Porcentagem de transformação é maior que zero, todos divididos por 10. </td> 
  </tr> 
 </tbody> 
</table>
