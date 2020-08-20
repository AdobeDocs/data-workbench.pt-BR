---
description: As expressões de Dimension nunca são usadas sozinhas, mas podem ser usadas em qualquer lugar em que uma dimensão é solicitada em uma métrica ou expressão de filtro.
solution: Analytics
title: Sintaxe para expressões de dimensão
topic: Data workbench
uuid: c437cc52-4eb3-4202-a0b4-e23889f9c8a2
translation-type: tm+mt
source-git-commit: a276b16565634fea9b693206c8a55b528fada977
workflow-type: tm+mt
source-wordcount: '1855'
ht-degree: 0%

---


# Sintaxe para expressões de dimensão{#syntax-for-dimension-expressions}

As expressões de Dimension nunca são usadas sozinhas, mas podem ser usadas em qualquer lugar em que uma dimensão é solicitada em uma métrica ou expressão de filtro.

1. As palavras sublinhadas devem ser digitadas literalmente no texto da expressão.
1. O formulário `{TEXT}?` representa o texto opcional.
1. O formulário `{TEXT}*` representa um texto que pode ocorrer zero ou mais vezes.
1. O formulário `{A | B | C |...}` representa o texto que consiste exatamente em uma das opções fornecidas, como A ou B ou C....
1. O formulário `[A,B)` representa um intervalo de números, de A até, mas não incluindo, B.

<table id="table_2D9AE1E2397843C284E838330370A1EE"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identificador </p> </td> 
   <td colname="col2"> <p>Um identificador faz referência a uma dimensão nomeada. Para obter as regras que regem identificadores legais, consulte <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> Sintaxe para identificadores </a>. </p> <p>Exemplo: Sessões[ Session_Number = "1" ] é o número de Sessões que tiveram um Número de Sessão de "1". Número da sessão é uma dimensão nomeada referenciada pelo identificador. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(Dimensão) </p> </td> 
   <td colname="col2"> <p>O resultado de (Dimension) é o mesmo resultado de Dimension. Os parênteses especificam a ordem das operações em uma expressão. </p> <p>Exemplo: Sessões[ (Página) = "/home" ] é o número de Sessões que visitam a Página "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esmaecer por nível </p> </td> 
   <td colname="col2"> <p>Define uma dimensão com os mesmos elementos que a dimensão Dim, mas relacionada a outras dimensões pelo nível da dimensão. </p> <p>Especificamente, um elemento da nova dimensão está relacionado aos mesmos elementos de nível que o mesmo elemento de Dim e está relacionado aos elementos de qualquer outra dimensão que estejam relacionados a qualquer um desses elementos de nível. </p> <p>Exemplo: Sessões[ (Página por Visitante)="/home" ] é o número de Sessões de Visitantes que visitaram a Página "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>shift(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>Define uma dimensão com os mesmos elementos que a dimensão Dim. O elemento eth do nível de dimensão está relacionado ao mesmo elemento da nova dimensão que o elemento Dim relacionado pelo elemento e+Nth de Nível, desde que os elementos eth e+Nth de nível estejam relacionados ao mesmo elemento do grupo de dimensões. </p> <p>Exemplo: Page_Visualização[ shift(Page, Page_Visualização, Session, 1)="/home" ] é o número de Visualizações de página para as quais a próxima página visualizada na mesma sessão é "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>next(Dim,Nível,Grupo,N) </p> </td> 
   <td colname="col2"> <p>Semelhante a shift(Dim,Level,Group,N), exceto que se houver valores vazios na dimensão, eles serão ignorados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>segment(Level {,String-&gt;Filter}*) </p> </td> 
   <td colname="col2"> <p> Define uma dimensão que classifica elementos de Nível com base em uma lista de filtros. Os elementos da nova dimensão são as strings fornecidas como argumentos. Cada elemento de Nível está relacionado ao primeiro elemento da dimensão de segmento cujo filtro admite o elemento de Nível. Isso é semelhante à visualização do segmento. </p> <p>Exemplo: segment(Visitante, "Visitantes únicos" -&gt; Visitante_Sessões = 1, "Visitantes muito leais" -&gt; Visitante_Sessões &gt; 10, "Todos os outros" -&gt; Verdadeiro) cria uma dimensão que classifica Visitantes em três grupos - Visitantes únicos são aqueles com apenas uma Sessão, Visitantes muito leais são aqueles com mais de dez Sessões e todos os outros Visitante têm um valor de "Todos os outros se." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>bucket(Level, Metric, Count, Format {, Start {, Size}? }?) </p> </td> 
   <td colname="col2"> <p>Define uma dimensão cujos elementos são intervalos de números (por exemplo, [0-9], [10-19],...). Os elementos de Nível estão relacionados ao elemento do bucket dim cujo intervalo contém o valor de Métrica para esse elemento de nível. Format é a string de formato printf usada para formatar os elementos de Métrica. </p> <p>Exemplo: Se Page_Duration_Minutos for uma dimensão no nível de Visualização da página que representa o número de minutos gastos em cada página, então bucket(Session, sum(Page_Duration_Minutos, Page_Visualização), 100, "%0.0f minutos", 0, 5) é uma dimensão no nível da sessão que representa o número de minutos gastos em cada Sessão; seus elementos têm intervalos de 5 minutos <code>{[0-5), [5-10),...,[495-500)}</code>. </p> <p>Start é o valor inicial do primeiro intervalo (padrão: 0) e Size é o tamanho do intervalo (padrão: 1). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prefix(Level {,ElementName-&gt;(Prefix{,Prefix}* )}* ) </p> </td> 
   <td colname="col2"> <p>Define uma dimensão cujos elementos são as sequências de caracteres de ElementName fornecidas e estão associados aos conjuntos correspondentes de strings de Prefixo. Os elementos de Nível se relacionam ao elemento do prefixo dim, que está associado ao prefixo mais longo correspondido pelo nome do elemento de nível especificado. Os prefixos que terminam com o caractere especial '$' devem corresponder exatamente. </p> <p>Por exemplo, prefix(URI, "Products" -&gt; ("/products/"), "Services" -&gt; ("/services/", "/products/service/"), "Warranties" -&gt; ("/products/warranty.html$", "/services/warranty.html$", "Tudo o resto" -&gt; ("/"))) cria uma dimensão que classifica URIs nas quatro categorias listadas. O efeito em várias páginas é o seguinte: </p> <p>/products/warranty.html na garantia, já que corresponde exatamente ao prefixo /products/warranty.html$. </p> <p>/products/cars/specialcar.html entra em Produtos, pois corresponde ao prefixo /products/ e não ao prefixo </p> <p>/products/service/something.html entra em Serviços, pois corresponde ao prefixo /products/service/ que é maior que o prefixo /products/. </p> <p>/companyinfo/aboutus.html entra na categoria "Tudo o resto", já que o único prefixo correspondente é "/". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>latency(Level, Clip, Dim, Filter, MaxBefore, MaxAfter, FormatString) </p> </td> 
   <td colname="col2"> <p>Consulte <a href="../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/t-create-ltncy-dims.md#task-6d46ea8c89a047318d9c71bf105ef64a"> Criação de Dimension de latência </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cartesiano_product(Separador {,Dim}*) </p> </td> 
   <td colname="col2"> <p>Define uma dimensão cujos elementos são todas as combinações ("produto cartesiano") dos elementos das dimensões fornecidas. O nome de cada elemento é feito da concatenação dos elementos correspondentes nas dimensões de entrada, separadas pela string Separator fornecida. </p> <p>Por exemplo, se a dimensão D1 tem elementos {"a", "b"} e a dimensão D2 tem os elementos {"x", "y"}, em seguida, produto cartesiano("-", D1, D2) tem os elementos {"a-x", "a-y", "b-x", "b-y"}. </p> <p>Observe que internamente, cada uma das dimensões de entrada é tratada como se o número de seus elementos fosse a próxima potência mais alta de duas. Isto resulta no fato de o produto cartesiano ter alguns elementos fictícios. Ao usar a API de Data Workbench, dependendo do formato de saída, esses elementos podem ser omitidos ou podem ser exibidos como "#nnn", onde nnn é o ordinal do elemento (e devem ser ignorados pelo cliente). </p> <p>Por exemplo, no exemplo acima, se D2 tivesse os três elementos {"x", "y", "z"}, ele seria tratado como se tivesse quatro elementos, e o produto cartesiano teria os elementos {"a-x", "a-y", "a-z", "#3", "b-x", "b-y", "b-z", "#7"}. </p> <p>Se nenhuma dimensão for fornecida, o resultado será uma dimensão com um elemento, "#0", que é equivalente à dimensão Nenhum. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>next_countable(Dim) </p> </td> 
   <td colname="col2"> <p>Refere-se a uma dimensão já existente: o antepassado mais próximo de Dim no schema. Por exemplo, o URI mais próximo é idêntico a Page_Visualização. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>normalized(Dim,Count) </p> </td> 
   <td colname="col2"> <p>Define uma dimensão normalizada a partir da dimensão desnormalizada Dim, com até elementos Count. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>last_n(Dim, TimeMetric, FormatString, Count, Offset, TrimToData {, WeekStart}?) </p> </td> 
   <td colname="col2"> <p>Define uma dimensão que tem um subconjunto dos elementos da dimensão Dim, cujos elementos representam fatias de tempo — por exemplo, dias, semanas ou anos. </p> <p>O subconjunto é um intervalo ao redor de um horário especificado, o valor da métrica constante TimeMetric, que é interpretada como um valor de tempo em segundos desde a meia-noite UTC de 1° de janeiro de 1970. O intervalo tem elementos Count, o último dos quais são elementos Offset depois do elemento Dim fornecido cujo nome é o resultado da formatação do valor da métrica com a string FormatString fornecida. FormatString usa o mesmo % escape que o strftime padrão da função da biblioteca C. </p> <p>Se trimToData for verdadeiro, todos os elementos no início da dimensão resultante, que seriam antes do início de Dim, serão removidos. Quando for falso, sempre haverá o número exato de elementos especificados por Count. Observe que pode haver sempre elementos no final da dimensão resultante que não estejam realmente em Dim. </p> <p>O WeekStart opcional, se especificado, deve ser um dos seguintes: { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" }. Ele modifica TimeMetric movendo-o para trás para a ocorrência mais recente do dia da semana. </p> <p>Exemplo: Se Week tiver os elementos { "10/03/10", "10/10/10", ..., "12/12/10" } e a métrica incorporada como de valor 1292348109 (representando um horário em meados de 14 de dezembro, 20 10), depois o último n(Semana, As_De, "%m/%d/%y", 4, 0, falso, "Sol") define a dimensão com os elementos { "12/12/10", "12/19/10", "12/23/10", "12/30/10 }" ... </p> <p>Exemplo 2: Se a dimensão Semana tiver apenas elementos {"12/19/10", "12/26/10", ..., "01/30/11"}, e a métrica De estiver acima, a última n (Semana, As_De, "%m/%d/%y", 4, 0, true, "Sol") fornecerá uma dimensão com elementos {"12/19/10", "23/12/10", "30/12/10"}. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_previous_months(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Define uma dimensão que tem um subconjunto dos elementos de Dim, cujos elementos representam dias. O subconjunto é um intervalo ao redor de um horário especificado, o valor da métrica constante TimeMetric, que é interpretada como um valor de tempo em segundos desde a meia-noite UTC de 1° de janeiro de 1970. O intervalo incluirá os elementos correspondentes a cada dia nos n meses anteriores ao horário especificado. Se includeThisMonth for verdadeiro, o intervalo também incluirá cada dia do mês que contém a hora especificada. </p> <p>FormatString especifica a formatação dos elementos de Dim, usando escape "%" como no tempo limite padrão da função da biblioteca C. </p> <p>Se trimToData for verdadeiro, todos os elementos no início da dimensão resultante, que seriam antes do início de Dim, serão removidos. Quando for falso, sempre haverá o número exato de elementos especificados por Count. Observe que pode haver sempre elementos no final da dimensão resultante que não estejam realmente em Dim. </p> <p>Exemplo: Se Day tiver os elementos { "01/01/10", "01/02/10", ..., "12/31/10" } e a métrica As de incorporada tiver o valor 1292348109 (representando um horário em meados de 14 de dezembro de 2000 10), em seguida, os dias dos meses anteriores (Dia, As_De, "%m/%d/%y", 2, falso, falso) terão elementos { "10/01/10", "10/02/10", ..., "11/30/10" }. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_current_month(Dim, TimeMetric, FormatString, allMonth, trimToData) </p> </td> 
   <td colname="col2"> <p>Semelhante aos dias dos meses anteriores, exceto que os elementos correspondem somente a dias do mesmo mês que o tempo especificado pela TimeMetric. Se allMonth for true, haverá um elemento para cada dia do mês apropriado; caso contrário, somente os dias a partir do primeiro dia do mês apropriado até o dia que contém a hora especificada farão parte da dimensão. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_future_months(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Semelhante aos dias dos meses anteriores, exceto que os elementos correspondem aos dias dos meses seguintes, em vez de antes, ao mês que contém o tempo especificado pela TimeMetric. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>horas_do_dia(Dim, Métrica, TimeFormatString, nDaysForward, TrimData) </p> </td> 
   <td colname="col2"> <p>Define uma dimensão que tem um subconjunto dos elementos de Dim, cujos elementos representam horas. O subconjunto é um intervalo ao redor de um horário especificado, o valor da métrica constante TimeMetric, que é interpretada como um valor de tempo em segundos desde a meia-noite UTC de 1° de janeiro de 1970. O intervalo inclui os elementos correspondentes a cada hora do dia nDaysForward após o dia que contém a hora especificada pela TimeMetric. </p> <p>FormatString especifica a formatação dos elementos de Dim, usando escape "%" como no tempo limite padrão da função da biblioteca C. A string de formato sempre deve exibir uma string representando meia-noite no início do dia do tempo passado. </p> <p>Se trimToData for verdadeiro, todos os elementos no início da dimensão resultante, que seriam antes do início de Dim, serão removidos. Quando for falso, sempre haverá o número exato de elementos especificados por Count. Observe que pode haver sempre elementos no final da dimensão resultante que não estejam realmente em Dim. </p> <p>Exemplo: Se a Hora tiver os elementos { "01/01/10 00:00", "01/01/10 01:00", ..., "12/31/10 23:00" }, e a métrica A partir integrada tiver o valor 1292348 109 (representando um horário em meados de 14 de dezembro de 2010), depois horas do dia (Hora, As_Of, "%x 00:00", 0, false) tem elementos { "12/12/10 00:00", "12/12/10 01:00" , ..., "12/12/10 23:00" }. </p> </td> 
  </tr> 
 </tbody> 
</table>

