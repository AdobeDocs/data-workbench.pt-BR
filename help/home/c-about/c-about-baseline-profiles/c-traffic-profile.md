---
description: O perfil de tráfego contém as seguintes métricas para identificar o tráfego do visitante.
solution: Analytics
title: Métricas de perfil de tráfego
topic: Data workbench
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Métricas de perfil de tráfego{#traffic-profile-metrics}

O perfil de tráfego contém as seguintes métricas para identificar o tráfego do visitante.

<table id="table_D981FB9F8B734E3C845A9628548565F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Fórmula de métrica e nível </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Entradas </td> 
   <td colname="col2">Fórmula: <span class="filepath"> Page_Views[sem shift(None,Page_View, Session,-1)]</span><p>Nível: Exibição de página </p></td> 
   <td colname="col3"> O número de sessões que entraram no site em cada página. Essa métrica é avaliada somente na dimensão Página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Taxa de saída </td> 
   <td colname="col2">Fórmula: <span class="filepath"> Saídas/Page_Views </span><p>Nível: Exibição de página </p></td> 
   <td colname="col3"> A porcentagem de sessões que saíram do site de cada página. A métrica Taxa de saída só pode ser avaliada na dimensão da página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Saídas </td> 
   <td colname="col2">Fórmula:<span class="filepath"> Page_Views[sem shift(None,Page_View, Session,1)] </span><p>Nível: Exibição de página </p></td> 
   <td colname="col3"> O número de sessões que saíram do site de cada página. Essa métrica é avaliada somente na dimensão Página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI90 </td> 
   <td colname="col2">Fórmula: <span class="filepath"> (bruto(Visitantes) - ((Visitantes) + .69)^0.5 * 1.281551 - 1.2269))*(Visitantes/bruto(Visitantes))</span><p>Nível: Visitante </p></td> 
   <td colname="col3"> Uma medida do menor número possível de visitantes, conforme relatado pelo Insight. Matematicamente, especifica o número mais baixo de visitantes com uma probabilidade de 90%. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Duração da exibição de página </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> soma (exata_page_duration, page_view)*0.1/Page_Views[any Exact_Page_Duration]</span></p> <p>Nível: Exibição de página </p> </td> 
   <td colname="col3"> A duração média (MM:SS) gasta em uma página ou grupo de páginas específico. Essa métrica é avaliada somente na dimensão Página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Exibições de página por sessão </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Page_Views/ (Sessões por Page_View) </span></p> <p>Nível: Sessão </p> </td> 
   <td colname="col3"> O número médio de exibições de página em cada sessão que tem exibições de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Exibições de página </td> 
   <td colname="col2">Fórmula: <span class="filepath"> sum(One, Page_View)</span><p>Nível: Exibição de página </p></td> 
   <td colname="col3"> O número de exibições de página. Uma exibição de página é uma solicitação para uma página definida (o acesso a imagens e outros tipos de conteúdo filtrado não são contados). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct de exibições de página </td> 
   <td colname="col2">Fórmula: <span class="filepath"> Page_Views/total(Page_Views) </span><p>Nível: Exibição de página </p></td> 
   <td colname="col3"> A porcentagem de exibições de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct de sessões </td> 
   <td colname="col2">Fórmula: <span class="filepath"> Sessões/total (Sessões)</span><p>Nível: Sessão </p></td> 
   <td colname="col3"> A porcentagem de sessões. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct de visitantes </td> 
   <td colname="col2">Fórmula: <span class="filepath"> Visitantes/total (Visitantes) </span><p>Nível: Visitante </p></td> 
   <td colname="col3"> A porcentagem de visitantes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes De Referência De Pct </td> 
   <td colname="col2"> <p>Fórmula: Referred_Visitors/Visitors </p> <p>Nível: Visitante </p> </td> 
   <td colname="col3"> A porcentagem de visitantes que foram encaminhados para este site a partir de outro site. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessões referenciadas </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Sessões[Referenciador&lt;&gt; 'Nenhum' e Referenciador&lt;&gt;'marcadores']</span></p> <p>Nível: Sessão </p> </td> 
   <td colname="col3"> O número de sessões que foram referenciadas para este site a partir de outro site. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes referenciados </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Visitantes[Visitor_Referrer&lt;&gt;'Nenhum' e Visitor_Referrer&lt;&gt;'marcas de livro']</span></p> <p>Nível: Visitante </p> </td> 
   <td colname="col3"> O número de visitantes que foram encaminhados para este site a partir de outro site. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Retenção </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Sessões[shift(None,Ses sion,Visitor,1) = ""] / Sessões</span></p> <p>Nível: Sessão </p> </td> 
   <td colname="col3"> A porcentagem de sessões que não são as últimas sessões dos visitantes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Duração da sessão </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> (soma (Exact_Page_Duration, Session)*.1/Sessions)[Session_ Duration &lt;= '01:00:00']</span></p> <p>Nível: Sessão </p> </td> 
   <td colname="col3">A duração média (MM:SS) que um visitante gasta em uma sessão. <p><p>Observação: É possível usar essa métrica com o recurso <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external"> Exportação</a> de segmentos. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessões por exibição de página </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Sessões por Page_View</span></p> <p> Nível: Sessão </p> </td> 
   <td colname="col3"> O número de sessões que tiveram uma exibição de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessões </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> sum(One, Session)</span></p> <p>Nível: Sessão </p> </td> 
   <td colname="col3"> Uma contagem de sessões do visitante. Uma sessão é um período de atividade para um visitante de um site. As sessões individuais de cada visitante são identificadas usando cookies, tempos limite e outras heurísticas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> confidence(Sessions) * 1.281551 / Sessões</span></p> <p>Nível: Visitante </p> </td> 
   <td colname="col3"> Uma medida de confiança da métrica Sessões, conforme relatado pela análise de big data. Matematicamente, é uma porcentagem +/- que especifica o intervalo dentro do qual a resposta real será 80% do tempo. Em princípio, a duplicação da percentagem do SIC80 permitirá obter uma resposta efetiva de 99% do tempo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI90 </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> ((raw(Visitors) + 0,68)^0.5 * 1.281551 + 1.2269) + raw(Visitors))*( Visitantes/raw(Visitantes))</span></p> <p>Nível: Visitante </p> </td> 
   <td colname="col3"> Uma medida do maior número possível de visitantes, conforme relatado pelo Insight. Matematicamente, especifica o maior número de visitantes com uma probabilidade de 90%. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI80 </td> 
   <td colname="col2">Fórmula: <span class="filepath"> (bruto(Visitantes) + 0,68)^0.5 * 1.281551 + 1.2269) / bruto(Visitantes)</span><p>Nível: Visitante </p></td> 
   <td colname="col3"> Uma medida de confiança da métrica Visitantes, conforme relatado pelo Insight. Matematicamente, é uma porcentagem +/- que especifica o intervalo dentro do qual a resposta real será 80% do tempo. Como regra geral, dobrar a porcentagem do VCI80 dará um intervalo dentro do qual a resposta real será 99% do tempo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes por exibição de página </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Visitantes por Page_View</span></p> <p>Nível: Exibição de página </p> </td> 
   <td colname="col3"> O número de visitantes que tiveram uma exibição de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes por sessão </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Visitantes por sessão </span></p> <p>Nível: Sessão </p> </td> 
   <td colname="col3"> O número de visitantes que tiveram uma sessão. </td> 
  </tr> 
 </tbody> 
</table>

