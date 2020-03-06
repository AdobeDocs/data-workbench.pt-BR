---
description: As seguintes dimensões estão disponíveis para uso no perfil histórico da análise de big data.
solution: Analytics
title: Dimensões no perfil Histórico da Análise de big data
topic: Data workbench
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensões no perfil Histórico da Análise de big data{#dimensions-in-the-data-workbench-historic-profile}

As seguintes dimensões estão disponíveis para uso no perfil histórico da análise de big data.

## Dimensões no perfil Histórico da Análise de big data {#section-96f1b64f5cb84411b630f97f227d888d}

As seguintes dimensões estão disponíveis para uso no perfil histórico da análise de big data.

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Bloco</b> </td> 
   <td colname="col2">Esta é a única contável nesta configuração, é a raiz de todas as dimensões. Um bloco pode ser considerado um servidor. Está usando o campo x-trackingid. <p>Observação:  A ID de bloco é um hash do nome do servidor mais o nome do host, portanto haverá aproximadamente um bloco por servidor por perfil. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> Esta é uma dimensão contável construída a partir da contagem de blocos. Cada linha de dados no perfil é um ping do agente de monitoramento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Alerta crítico</b> </td> 
   <td colname="col2"> Dimensão numérica criada a partir do valor cs-uri-query(ad). Ele é construído no nível de Ping, desde que cs-uri-query(a) corresponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Alerta para baixo</b> </td> 
   <td colname="col2"> Dimensão numérica criada a partir do valor cs-uri-query(ac). Ele é construído no nível de Ping, desde que cs-uri-query(a) corresponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Aviso de alerta</b> </td> 
   <td colname="col2"> Dimensão numérica criada a partir do valor cs-uri-query(ae). Ele é construído no nível de Ping, desde que cs-uri-query(a) corresponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Qualquer reprocessamento de perfil</b> </td> 
   <td colname="col2"> Dimensão numérica criada a partir do valor cs-uri-query(aa). Ele é construído no nível de Ping, desde que cs-uri-query(a) corresponda a "1" e cs-uriquery(k) não esteja vazio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Minutos de atraso</b> </td> 
   <td colname="col2"> cs-uri-query(bi) é colocado no campo x-as-of-delay-minutos e arredondado para o minuto mais próximo. Ele é construído no nível de Ping, desde que cs-uri-query(a) corresponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem da Linha de Capacidade</b> </td> 
   <td colname="col2"> Dimensão numérica criada a partir do valor cs-uri-query(r). Ele é construído no nível de Ping, desde que cs-uri-query(a) corresponda a "1" e cs-uriquery(k) não esteja vazio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem do Tamanho da Capacidade</b> </td> 
   <td colname="col2"> Dimensão numérica criada a partir do valor cs-uri-query(n). Ele é construído no nível de Ping, desde que cs-uri-query(a) corresponda a "1" e cs-uriquery(k) não esteja vazio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Êxito na verificação do componente</b> </td> 
   <td colname="col2"> Dimensão simples criada a partir do valor cs-uri-query(v). Ele é criado no nível de Ping e está condicionado à correspondência de cs-uri-query(a) com "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Componentes em erro</b> </td> 
   <td colname="col2"> cs-uri-query(ao) é dividido pelo delimitador "|" e copiado no campo x-components-in-error. Muitas para muitas dimensões criadas a partir do campo x-components-in-error. Construído no nível de Ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segundos de verificação detalhados</b> </td> 
   <td colname="col2"> Dimensão numérica criada a partir do valor cs-uri-query(l). Ele é construído no nível de Ping, desde que cs-uri-query(k) não esteja vazio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Êxito na verificação detalhada</b> </td> 
   <td colname="col2"> Dimensão simples criada a partir do valor cs-uri-query(k). Ele é construído no nível de Ping, desde que cs-uri-query(a) corresponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimension GigaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bc) é copiado para o campo x-dimension-gigabytes. O campo x-dimension-gigabytes é um usuário para essa Dimensão Simples, condicionada em cs-uri-query(a) correspondente a "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de disco "x" usada</b> </td> 
   <td colname="col2"> Essas Dimensões Numéricas são configuradas a partir dos valores cs-uri-query(ah, ai, aj, ak, al). Eles são criados no nível de Ping e condicionados em cs-uri-query(a) corresponde a "1" e cs-uri-query(k) não está vazio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Estimativa de Dekasegundos de Varredura</b> </td> 
   <td colname="col2"> O campo x-estimated-sweep-dekasegundo é usado nesta Dimensão Numérica. Esse é o tempo de varredura estimado dos servidores dividido por dez (resolução reduzida de medição de varredura para aumentar o tamanho da dimensão). <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaBytes de Entrada Rápida por Minuto</b> </td> 
   <td colname="col2"> O valor cs-uri-query(bj) é usado para essa dimensão. A Última linha de um bloco é usada como o valor da dimensão. Se o conjunto de dados estiver em Fast Input, esse valor de Dimensão Numérica exibirá o MB por minuto em que o sistema está inserindo dados. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaBytes de Mesclagem Rápida por Minuto</b> </td> 
   <td colname="col2">O valor cs-uri-query(bk) é usado para essa dimensão. A última linha de um bloco é usada como o valor da dimensão. Se o conjunto de dados estiver na Mesclagem rápida, o valor dessa dimensão numérica exibirá o MB por minuto em que o sistema está se mesclando. <p><p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>GigaBytes de campo</b> </td> 
   <td colname="col2">O valor cs-uri-query(bg) é usado para essa dimensão. O valor é dividido por 1000 e arredondado para o número inteiro mais próximo. O valor desta Dimensão Numérica exibirá a quantidade de espaço que os Campos no conjunto de dados estão usando. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Grupo</b> </td> 
   <td colname="col2"> Dimensão simples criada no nível de Ping a partir do valor cs-uri-query(x). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> O valor cs-uri-query(b) é usado para essa dimensão. O valor da dimensão Simples é a Última Linha para um Bloco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Último Ping</b> </td> 
   <td colname="col2"> o campo x-unixtime é copiado em x-last-ping e dividido por 10 para reduzir a cardinalidade. A Dimensão Numérica é criada no nível de Bloco e usa o campo x-last-ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Média de carga</b> </td> 
   <td colname="col2"> Esta é uma dimensão numérica que usa a Última linha para um determinado valor de cs-uri-query(i) do servidor. Ela está condicionada se cs-uri-query(k) não estiver vazia. Essa dimensão é usada para calcular a carga média nos servidores no sistema que está sendo monitorado. <p><p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de leitura de registro</b> </td> 
   <td colname="col2">o valor cs-uri-query(be) é usado para essa dimensão numérica, criada no nível de Ping. Essa dimensão é usada para calcular a porcentagem de logs que estão sendo lidos. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem do Arquivo de Página de Memória</b> </td> 
   <td colname="col2"> Esta é uma dimensão Numérica usando o valor cs-uri-query(o), criado no nível de Ping. Ela está condicionada se cs-uri-query(k) não estiver vazia e se cs-uri-query(a) corresponder a "1". Essa dimensão é usada para calcular a porcentagem de uso da memória do arquivo de página. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Total de megabits físicos de memória</b> </td> 
   <td colname="col2">Esta é uma dimensão Numérica usando o valor cs-uri-query(ag), criado no nível de Ping. Ela está condicionada se cs-uri-query(k) não estiver vazia e se cs-uri-query(a) corresponder a "1. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem física da memória</b> </td> 
   <td colname="col2">Esta é uma dimensão Numérica usando o valor cs-uri-query(ag), criado no nível de Ping. Ela está condicionada se cs-uri-query(k) não estiver vazia e se cs-uri-query(a) corresponder a "1. Essa dimensão é usada para calcular a porcentagem de uso de memória física de cada Servidor. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de Consulta de Memória</b> </td> 
   <td colname="col2"> Esta é uma dimensão Numérica usando o valor cs-uri-query(s) no nível Ping. Ela é condicionada em cs-uri-query(k) não sendo vazia e cs-uri-query(a) correspondendo a "1. Essa dimensão é usada para calcular a porcentagem do uso da memória de consulta de cada Servidor. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Conexões de rede</b> </td> 
   <td colname="col2"> Esta é uma dimensão Numérica usando o valor cs-uri-query(q) criado no nível de Ping. Ela é condicionada em cs-uri-query(k) não sendo vazia e cs-uri-query(a) correspondendo a "1. Isso é usado para mostrar o número de conexões de rede que existem para um determinado servidor. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Linhas de saída</b> </td> 
   <td colname="col2"> o valor cs-uri-query(bh) é dividido por 100000 e copiado no campo x-output-lines para reduzir o tamanho da dimensão. X-output-lines é usado em uma Dimensão numérica criada no nível de Ping, desde que cs-uri-query(a) corresponda a "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID do tipo de ping</b> </td> 
   <td colname="col2"> Dimensão simples criada usando o valor cs-uri-query(a) no nível de Ping. Isto mostra que tipo de Ping foi gravado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Centisegundos de latência da pesquisa</b> </td> 
   <td colname="col2">O valor cs-uri-query(m) é dividido por 10 para reduzir o tamanho da dimensão e copiado no campo x-poll-latency-centisegundos. Esta é uma dimensão Numérica criada no nível Ping, desde que cs-uri-query(k) não esteja vazia e que cs-uri-query(a) corresponda a "1"/ Essa dimensão é usada para calcular a latência da pesquisa. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID do modo de processamento</b> </td> 
   <td colname="col2"> O valor cs-uri-query(bb) é usado para essa Dimensão Simples, criada no nível de Ping. É condicionado que cs-uri-query(bb) não esteja vazio e que cs-uri-query(a) corresponda à ID do modo de processamento "2" permite ver em que modo de processamento o sistema está (Entrada Rápida, Intercalação Rápida, Tempo Real). <p>Observação:  Essa dimensão é ocultada e re-exposta com valores amigáveis no modo de processamento de dimensão do cliente. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Perfil</b> </td> 
   <td colname="col2"> O valor cs-uri-query(ba) é usado para essa Dimensão Simples, é criado no nível de Ping. Essa dimensão exibe os nomes dos perfis que estão sendo monitorados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segundos de verificação rápida</b> </td> 
   <td colname="col2"> O valor cs-uri-query(h) é usado para essa Dimensão Numérica. Ele é construído no nível de Ping, desde que cs-uri-query(a) corresponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Sucesso na verificação rápida</b> </td> 
   <td colname="col2"> Esta é uma dimensão Simples criada a partir do valor cs-uri-query(g) criado no nível de Ping. É usado para calcular a métrica de verificação rápida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de processamento em tempo real</b> </td> 
   <td colname="col2"> Dimensão numérica usando o valor cs-uri-query(t) criado no nível de Ping. É condicionado que cs-uri-query(a) corresponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fonte mais atrasada</b> </td> 
   <td colname="col2"> Dimensão simples criada a partir do valor cs-uri-query(bl) criado no nível de Ping. Essa dimensão exibe o quando ocorreu o último contato com uma fonte de dados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de Espaço Temporário do Banco de Dados</b> </td> 
   <td colname="col2">Dimensão numérica criada usando o valor cs-uri-query(an), criado no nível de Ping. É condicionado que cs-uri-query(k) não esteja vazio e que cs-uri-query(a) corresponda a "1". Ele é usado para calcular a porcentagem do espaço do banco de dados temporário usado em um determinado servidor. <p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de transformação</b> </td> 
   <td colname="col2">o valor cs-uri-query(bf) é usado para essa dimensão numérica. É construído no nível de Ping. Essa dimensão é usada para calcular a porcentagem da transformação completa de dados. <p><p>Observação:  Essa dimensão está oculta, pois só é útil quando usada como média em uma métrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versão do Análise de big data</b> </td> 
   <td colname="col2"> O valor cs-uri-query(ab) é usado para essa Dimensão Simples. Ele é construído no nível de Ping e está condicionado de que cs-uri-query(ab) não esteja vazio e cs-uri-query(a) corresponda a "1". Isso exibe as versões do servidor de análise de big data em execução em cada servidor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versão Principal do Análise de big data</b> </td> 
   <td colname="col2"> O valor cs-uri-query(ab) é dividido e o valor principal da versão é copiado no campo x-insight-version-major. É uma Dimensão Simples criada no nível de Ping e condicionada pelo fato de x-insight-version-major não estar vazia e cs-uri-query(a) corresponder a "1". </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->

