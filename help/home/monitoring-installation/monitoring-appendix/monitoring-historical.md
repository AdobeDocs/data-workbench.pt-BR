---
description: As seguintes dimensões estão disponíveis para uso no perfil Histórico do Data Workbench.
title: Dimensões no perfil histórico do Data Workbench
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
exl-id: 9df1f317-a985-4132-b32e-f2263e0c23b2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 1%

---

# Dimensões no perfil histórico do Data Workbench{#dimensions-in-the-data-workbench-historic-profile}

As seguintes dimensões estão disponíveis para uso no perfil Histórico do Data Workbench.

## Dimensões no perfil histórico do Data Workbench {#section-96f1b64f5cb84411b630f97f227d888d}

As seguintes dimensões estão disponíveis para uso no perfil Histórico do Data Workbench.

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Bloco</b> </td> 
   <td colname="col2">Essa é a única contável nessa configuração, ela é a raiz de todas as dimensões. Um bloco pode ser considerado um servidor. Ele está usando o campo x-trackingid . <p>Observação:  A ID de bloco é um hash do nome do servidor mais o nome do host, portanto, haverá aproximadamente um bloco por servidor por perfil. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> Esta é uma dimensão contável criada a partir do Bloqueio contável. Cada linha de dados no perfil é um ping do agente de monitoramento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Alerta crítico</b> </td> 
   <td colname="col2"> Dimension numérico criado a partir do valor cs-uri-query(ad) . Ele é criado no nível de Ping sob condição de que cs-uri-query(a) corresponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Alerta desativado</b> </td> 
   <td colname="col2"> Dimension numérico criado a partir do valor cs-uri-query(ac) . Ele é criado no nível de Ping, sob condição de que cs-uri-query(a) corresponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Aviso de Alerta</b> </td> 
   <td colname="col2"> Dimension numérico criado a partir do valor cs-uri-query(ae) . Ele é criado no nível de Ping sob condição de que cs-uri-query(a) corresponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Qualquer reprocessamento de perfil</b> </td> 
   <td colname="col2"> Dimension numérico criado a partir do valor cs-uri-query(aa) . Ele é criado no nível de Ping sob condição de que cs-uri-query(a) corresponda a "1" e cs-uriquery(k) não esteja vazio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Atraso das atas</b> </td> 
   <td colname="col2"> cs-uri-query(bi) é colocado no campo x-as-of-delay-minutes e arredondado para o minuto mais próximo. Ele é criado no nível de Ping sob condição de que cs-uri-query(a) corresponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem da Linha de Capacidade</b> </td> 
   <td colname="col2"> Dimension numérico criado a partir do valor cs-uri-query(r). Ele é criado no nível de Ping sob condição de que cs-uri-query(a) corresponda a "1" e cs-uriquery(k) não esteja vazio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem do Tamanho da Capacidade</b> </td> 
   <td colname="col2"> Dimension numérico criado a partir do valor cs-uri-query(n). Ele é criado no nível de Ping sob condição de que cs-uri-query(a) corresponda a "1" e cs-uriquery(k) não esteja vazio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Êxito na verificação do componente</b> </td> 
   <td colname="col2"> Dimension simples criado a partir do valor cs-uri-query(v). Ele é criado no nível de Ping e está condicionado à correspondência de cs-uri-query(a) com "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Componentes no erro</b> </td> 
   <td colname="col2"> cs-uri-query(ao) é dividido pelo delimitador "|" e copiado para o campo x-components-in-error . Muitos para muitos Dimension criados a partir do campo x-components-in-error . Construído no nível de Ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segundos de Verificação Detalhada</b> </td> 
   <td colname="col2"> Dimension numérico criado a partir do valor cs-uri-query(l). Ele é criado no nível de Ping sob condição de que cs-uri-query(k) não esteja vazio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Sucesso da verificação detalhada</b> </td> 
   <td colname="col2"> Dimension simples criado a partir do valor cs-uri-query(k). Ele é criado no nível de Ping sob condição de que cs-uri-query(a) corresponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimension GigaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bc) é copiado para o campo x-dimension-gigabytes . O campo x-dimension-gigabytes é o usuário para esse Dimension Simple, condicionado em cs-uri-query(a) correspondente a "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de Disco "x" Usada</b> </td> 
   <td colname="col2"> Essas Dimension numéricas são configuradas a partir dos valores cs-uri-query(ah, ai, aj, ak, al). Eles são criados no nível de Ping e condicionados em cs-uri-query(a) corresponde a "1" e cs-uri-query(k) não está vazio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Estimativa de segundos de varredura</b> </td> 
   <td colname="col2"> O campo x-estimated-sweep-dekaseconds é usado neste Dimension numérico. Esse é o tempo estimado de varredura dos servidores dividido por dez (resolução reduzida de medição de varredura para tornar a dimensão mais razoavelmente dimensionada). <p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaBytes de Entrada Rápida por Minuto</b> </td> 
   <td colname="col2"> O valor cs-uri-query(bj) é usado para essa dimensão. A Última linha de um bloco é usada como o valor da dimensão. Se o conjunto de dados estiver em Fast Input, esse valor numérico será exibido na MB por minuto, no qual o sistema está inserindo dados. <p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaBytes de Mesclagem Rápida por Minuto</b> </td> 
   <td colname="col2">O valor cs-uri-query(bk) é usado para essa dimensão. A Última linha de um bloco é usada como o valor da dimensão. Se o conjunto de dados estiver em Fast Merge Este valor Numérico de Mesclagem exibirá o MB por minuto no qual o sistema está se mesclando. <p><p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Campo GigaBytes</b> </td> 
   <td colname="col2">O valor cs-uri-query(bg) é usado para essa dimensão. O valor é dividido por 1000 e arredondado para o número inteiro mais próximo. Esse valor Numérico de Dimension exibirá a quantidade de espaço que os Campos no conjunto de dados estão usando. <p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Grupo</b> </td> 
   <td colname="col2"> Dimension simples criado no nível de Ping a partir do valor cs-uri-query(x). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> O valor cs-uri-query(b) é usado para essa dimensão. O valor da dimensão Simples é a Última Linha de um Bloco. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Último ping</b> </td> 
   <td colname="col2"> o campo x-unixtime é copiado em x-last-ping e dividido por 10 para reduzir a cardinalidade. O Dimension numérico é criado no nível de Bloco e usa o campo x-last-ping . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Carga média</b> </td> 
   <td colname="col2"> Esta é uma dimensão Numérica usando a Última linha para um determinado valor cs-uri-query(i) de servidor. Está condicionado em cs-uri-query(k) não estar vazio. Essa dimensão é usada para calcular a carga média nos servidores do sistema que está sendo monitorado. <p><p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de Leitura de Log</b> </td> 
   <td colname="col2">o valor cs-uri-query(be) é usado para essa dimensão numérica, criada no nível de Ping. Essa dimensão é usada para calcular a porcentagem de logs que estão sendo lidos. <p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem do Arquivo da Página de Memória</b> </td> 
   <td colname="col2"> Esta é uma dimensão Numérica usando o valor cs-uri-query(o), criado no nível Ping. Está condicionado em cs-uri-query(k) não estando vazio e cs-uri-query(a) correspondendo a "1". Essa dimensão é usada para calcular a porcentagem do uso de memória do arquivo de página. <p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Total de megabytes físicos de memória</b> </td> 
   <td colname="col2">Esta é uma dimensão Numérica usando o valor cs-uri-query(ag), criado no nível Ping. Está condicionado em cs-uri-query(k) não estando vazio e cs-uri-query(a) correspondendo a "1. <p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem física da memória</b> </td> 
   <td colname="col2">Esta é uma dimensão Numérica usando o valor cs-uri-query(ag), criado no nível Ping. Está condicionado em cs-uri-query(k) não estando vazio e cs-uri-query(a) correspondendo a "1. Essa dimensão é usada para calcular a porcentagem do uso de memória física de cada Servidor. <p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de Consulta de Memória</b> </td> 
   <td colname="col2"> Esta é uma dimensão Numérica usando o valor cs-uri-query(s) no nível Ping. Está condicionado em cs-uri-query(k) não estando vazio e cs-uri-query(a) correspondendo a "1. Essa dimensão é usada para calcular a porcentagem do uso de memória de consulta de cada Servidor. <p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Conexões de rede</b> </td> 
   <td colname="col2"> Esta é uma dimensão Numérica usando o valor cs-uri-query(q) criado no nível Ping. Está condicionado em cs-uri-query(k) não estando vazio e cs-uri-query(a) correspondendo a "1. Isso é usado para mostrar o número de conexões de rede que existem para um determinado servidor. <p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Linhas de saída</b> </td> 
   <td colname="col2"> O valor cs-uri-query(bh) é dividido por 100000 e copiado para o campo x-output-rows para reduzir o tamanho da dimensão. X-output-rows é usado em um Dimension numérico criado no nível de Ping, condicionado a cs-uri-query(a) corresponder a "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID do tipo de ping</b> </td> 
   <td colname="col2"> Dimension simples criado usando o valor cs-uri-query(a) no nível de Ping. Isto mostra que tipo de Ping foi gravado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segundos da Latência da Pesquisa</b> </td> 
   <td colname="col2">O valor cs-uri-query(m) é dividido por 10 para reduzir o tamanho da dimensão e copiado para o campo x-poll-latency-centiseconds. Esta é uma dimensão Numérica criada no nível de Ping, condicionada pelo fato de cs-uri-query(k) não estar vazia e cs-uri-query(a) corresponder a "1"/ Essa dimensão é usada para calcular a latência da pesquisa. <p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID do modo de processamento</b> </td> 
   <td colname="col2"> O valor cs-uri-query(bb) é usado para esse Dimension Simple, criado no nível Ping. Está condicionado que cs-uri-query(bb) não está vazio e que cs-uri-query(a) corresponde à ID de modo de processamento "2" permite ver em que modo de processamento o sistema está (Fast Input, Fast Merge, Tempo Real). <p>Observação:  Essa dimensão é oculta e re-exposta com valores amigáveis na dimensão do cliente Modo de processamento. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Perfil</b> </td> 
   <td colname="col2"> O valor cs-uri-query(ba) é usado para esse Dimension Simple, ele é criado no nível Ping. Essa dimensão exibe os nomes dos perfis que estão sendo monitorados no momento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segundos de verificação rápida</b> </td> 
   <td colname="col2"> O valor cs-uri-query(h) é usado para esse Dimension numérico. Ele é criado no nível de Ping sob condição de que cs-uri-query(a) corresponda a "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Sucesso da verificação rápida</b> </td> 
   <td colname="col2"> Esta é uma dimensão Simples criada a partir do valor cs-uri-query(g) criado no nível Ping. É usada para calcular a métrica de verificação rápida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de processamento em tempo real</b> </td> 
   <td colname="col2"> Dimension numérico usando o valor cs-uri-query(t) criado no nível de Ping. Está condicionado à correspondência de cs-uri-query(a) com "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fonte mais atrasada</b> </td> 
   <td colname="col2"> Dimension simples criado a partir do valor cs-uri-query(bl) criado no nível de Ping. Essa dimensão exibe o quando o último contato com uma fonte de dados ocorreu. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de Espaço de Banco de Dados Temp</b> </td> 
   <td colname="col2">Dimension numérico criado usando o valor cs-uri-query(an), criado no nível de Ping. Está condicionado que cs-uri-query(k) não está vazio e cs-uri-query(a) corresponde a "1". Ele é usado para calcular a porcentagem do espaço de banco de dados Temp usado em um determinado servidor. <p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentagem de transformação</b> </td> 
   <td colname="col2">o valor cs-uri-query(bf) é usado para essa dimensão numérica. Ele é criado no nível do Ping. Essa dimensão é usada para calcular a porcentagem da transformação completa de dados. <p><p>Observação:  Essa dimensão é oculta, pois só é útil quando avaliada como média em uma métrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versão do Data Workbench</b> </td> 
   <td colname="col2"> O valor cs-uri-query(ab) é usado para esse Dimension Simple. Ele é criado no nível de Ping e está condicionado de que cs-uri-query(ab) não está vazio e cs-uri-query(a) corresponde a "1". Isso exibe as versões do servidor do Data Workbench em execução em cada servidor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versão principal do Data Workbench</b> </td> 
   <td colname="col2"> O valor cs-uri-query(ab) é dividido e o valor principal da versão é copiado para o campo x-insight-version-major. É um Dimension Simple criado no nível de Ping e condicionado que x-insight-version-major não está vazio e cs-uri-query(a) corresponde a "1". </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->
