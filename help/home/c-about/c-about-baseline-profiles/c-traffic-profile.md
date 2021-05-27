---
description: O perfil Tráfego contém as seguintes métricas para identificar o tráfego do visitante.
title: Métricas de perfil de tráfego
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
exl-id: 38f191e5-5b30-4fe0-a680-bcb33fe52eca
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 2%

---

# Métricas de perfil de tráfego{#traffic-profile-metrics}

O perfil Tráfego contém as seguintes métricas para identificar o tráfego do visitante.

<table id="table_D981FB9F8B734E3C845A9628548565F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Fórmula e nível de métrica </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Entradas </td> 
   <td colname="col2">Fórmula: <span class="filepath"> Page_Views[no shift(None,Page_View, Session,-1)]</span><p>Nível: Exibição da página </p></td> 
   <td colname="col3"> O número de sessões que entraram no site em cada página. Essa métrica é avaliada somente pela dimensão Página . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Taxa de saída </td> 
   <td colname="col2">Fórmula: <span class="filepath"> Saídas/Page_Views </span><p>Nível: Exibição da página </p></td> 
   <td colname="col3"> A porcentagem de sessões que saíram do site de cada página. A métrica Taxa de saída só pode ser avaliada pela dimensão da página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Saídas </td> 
   <td colname="col2">Fórmula:<span class="filepath"> Page_Views[sem shift(None,Page_View, Session,1)] </span><p>Nível: Exibição da página </p></td> 
   <td colname="col3"> O número de sessões que saíram do site de cada página. Essa métrica é avaliada somente pela dimensão Página . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI90 </td> 
   <td colname="col2">Fórmula: <span class="filepath"> (bruto(Visitantes) - ((bruto(Visitantes) + .69)^0.5 * 1.281551 - 1.2269))*(Visitantes/bruto(Visitantes))</span><p>Nível: Visitante </p></td> 
   <td colname="col3"> Uma medida do número mais baixo de visitantes possíveis, conforme relatado pelo Insight. Matematicamente, ela especifica o número mais baixo de visitantes com uma probabilidade de 90%. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Duração da exibição de página </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> soma (exato_page_duration, page_view)*0.1/Page_Views[any Exact_Page_Duration]</span></p> <p>Nível: Exibição da página </p> </td> 
   <td colname="col3"> O tempo médio (MM:SS) gasto em uma página ou grupo de páginas específico. Essa métrica é avaliada somente pela dimensão Página . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Exibições de página por sessão </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Page_Views/ (Sessões por Page_View) </span></p> <p>Nível: Sessão </p> </td> 
   <td colname="col3"> O número médio de exibições de página em cada sessão que tem exibições de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Exibições de página </td> 
   <td colname="col2">Fórmula: <span class="filepath"> soma(Um, Page_View)</span><p>Nível: Exibição da página </p></td> 
   <td colname="col3"> O número de exibições da página. Uma exibição de página é uma solicitação de uma página definida (o acesso a imagens e outros tipos de conteúdo filtrado não são contados). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porte das exibições de página </td> 
   <td colname="col2">Fórmula: <span class="filepath"> Page_Views/total(Page_Views) </span><p>Nível: Exibição da página </p></td> 
   <td colname="col3"> A porcentagem de exibições de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct das sessões </td> 
   <td colname="col2">Fórmula: <span class="filepath"> Sessões/total(Sessões)</span><p>Nível: Sessão </p></td> 
   <td colname="col3"> A porcentagem de sessões. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct de visitantes </td> 
   <td colname="col2">Fórmula: <span class="filepath"> Visitantes/total(Visitantes) </span><p>Nível: Visitante </p></td> 
   <td colname="col3"> A porcentagem de visitantes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes referenciados Pct </td> 
   <td colname="col2"> <p>Fórmula: Referred_Visitors/Visitors </p> <p>Nível: Visitante </p> </td> 
   <td colname="col3"> A porcentagem de visitantes que foram encaminhados para este site a partir de outro site. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessões referenciadas </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Sessões[Referenciador&lt;&gt; 'Nenhum' e Referenciador&lt;&gt;'marcadores']</span></p> <p>Nível: Sessão </p> </td> 
   <td colname="col3"> O número de sessões que foram encaminhadas para este site a partir de outro site. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes referenciados </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Visitantes[Visitor_ Referrer&lt;&gt;'None' e Visitor_Referrer&lt;&gt;'bookmarks']</span></p> <p>Nível: Visitante </p> </td> 
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
   <td colname="col3">A duração média (MM:SS) que um visitante gasta em uma sessão. <p><p>Observação: Você pode usar essa métrica com o recurso <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external"> Exportar segmento</a>. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessões por exibição de página </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Sessões por Page_View</span></p> <p> Nível: Sessão </p> </td> 
   <td colname="col3"> O número de sessões que tiveram uma exibição de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessões </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> soma(Uma, Sessão)</span></p> <p>Nível: Sessão </p> </td> 
   <td colname="col3"> Uma contagem de sessões de visitante. Uma sessão é um período de atividade para um visitante de um site. As sessões individuais para cada visitante são identificadas usando cookies, tempos limite e outras heurísticas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> confidence(Sessions) * 1.281551 / Sessions</span></p> <p>Nível: Visitante </p> </td> 
   <td colname="col3"> Uma medida de confiança da métrica Sessões conforme relatado pelo Data Workbench. Matematicamente, é uma porcentagem +/- especificando o intervalo no qual a resposta real será de 80% das vezes. Em princípio, a duplicação da percentagem SCI80 dará um intervalo dentro do qual a resposta efetiva será de 99% das vezes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI90 </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> ((raw(Visitors) + .68)^0.5 * 1.281551 + 1.2269) + raw(Visitors))*( Visitors/raw(Visitors))</span></p> <p>Nível: Visitante </p> </td> 
   <td colname="col3"> Uma medida do maior número de visitantes possíveis, conforme relatado pelo Insight. Matematicamente, ele especifica o número mais alto de visitantes com uma probabilidade de 90%. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI80 </td> 
   <td colname="col2">Fórmula: <span class="filepath"> ((raw(Visitors) + .68)^0.5 * 1.281551 + 1.2269) / raw(Visitors)</span><p>Nível: Visitante </p></td> 
   <td colname="col3"> Uma medida de confiança da métrica Visitantes conforme relatado pelo Insight. Matematicamente, é uma porcentagem +/- especificando o intervalo no qual a resposta real será de 80% das vezes. Em princípio, dobrar a porcentagem de VCI80 dará um intervalo dentro do qual a resposta real ficará em 99% das vezes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes por exibição de página </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Visitantes por Page_View</span></p> <p>Nível: Exibição da página </p> </td> 
   <td colname="col3"> O número de visitantes com uma exibição de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes por sessão </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Visitantes por Sessão </span></p> <p>Nível: Sessão </p> </td> 
   <td colname="col3"> O número de visitantes que tiveram uma sessão. </td> 
  </tr> 
 </tbody> 
</table>
