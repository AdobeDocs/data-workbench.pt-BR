---
description: As expressões Dimension nunca são usadas sozinhas, mas podem ser usadas em qualquer lugar onde uma dimensão é chamada em uma métrica ou expressão de filtro.
title: Sintaxe para expressões de dimensão
uuid: c437cc52-4eb3-4202-a0b4-e23889f9c8a2
exl-id: 58609e31-8ad8-418b-9a9f-40462d6443f7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1855'
ht-degree: 0%

---

# Sintaxe para expressões de dimensão{#syntax-for-dimension-expressions}

As expressões Dimension nunca são usadas sozinhas, mas podem ser usadas em qualquer lugar onde uma dimensão é chamada em uma métrica ou expressão de filtro.

1. Palavras sublinhadas devem ser inseridas no texto da expressão literalmente.
1. O formulário `{TEXT}?` representa o texto opcional.
1. O formulário `{TEXT}*` representa um texto que pode ocorrer zero ou mais vezes.
1. O formulário `{A | B | C |...}` representa o texto que consiste exatamente em uma das opções fornecidas, como A ou B ou C....
1. O formulário `[A,B)` representa um intervalo de números, de A até, mas não incluindo, B.

<table id="table_2D9AE1E2397843C284E838330370A1EE"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identificador </p> </td> 
   <td colname="col2"> <p>Um identificador faz referência a uma dimensão nomeada. Para obter as regras que regem os identificadores legais, consulte <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> Sintaxe para identificadores </a>. </p> <p>Exemplo: Sessões[ Session_Number = "1" ] é o número de Sessões que tiveram um Número de Sessões de "1". Número de sessão é uma dimensão nomeada referenciada pelo identificador . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(Dimensão) </p> </td> 
   <td colname="col2"> <p>O resultado de (Dimension) é o mesmo resultado de Dimension. Os parênteses especificam a ordem das operações em uma expressão. </p> <p>Exemplo: Sessões[ (Página) = "/home" ] é o número de Sessões que visitam a Página "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esmaecer por nível </p> </td> 
   <td colname="col2"> <p>Define uma dimensão com os mesmos elementos da dimensão Dim, mas relacionada a outras dimensões por meio do nível da dimensão. </p> <p>Especificamente, um elemento da nova dimensão está relacionado aos mesmos elementos de nível que o mesmo elemento de Dim e está relacionado aos elementos de qualquer outra dimensão que estejam relacionados a qualquer um desses elementos de nível. </p> <p>Exemplo: Sessões[ (Página por Visitante)="/home" ] é o número de Sessões de Visitantes que visitaram a Página "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>shift(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>Define uma dimensão com os mesmos elementos da dimensão Dim. O elemento eth do nível de dimensão está relacionado ao mesmo elemento da nova dimensão que o elemento Dim relacionado ao elemento e+Nth do Nível, desde que os elementos eth e+Nth do nível estejam relacionados ao mesmo elemento do grupo de dimensão. </p> <p>Exemplo: Page_Views[ shift(Page, Page_View, Session, 1)="/home" ] é o número de Exibições de página para as quais a próxima Página visualizada na mesma Sessão é "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>next(Dim,Nível,Grupo,N) </p> </td> 
   <td colname="col2"> <p>Semelhante a shift(Dim,Level,Group,N), exceto que se houver valores vazios na dimensão, eles serão ignorados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>segment(Level {,String-&gt;Filter}*) </p> </td> 
   <td colname="col2"> <p> Define uma dimensão que classifica elementos de Nível com base em uma lista de filtros. Os elementos da nova dimensão são as cadeias de caracteres fornecidas como argumentos. Cada elemento de Nível está relacionado ao primeiro elemento da dimensão de segmento cujo filtro admite o elemento de Nível. Isso é semelhante à visualização do segmento. </p> <p>Exemplo: segment(Visitor, "One-Time Visitors" -&gt; Visitor_Sessions = 1, "Muito Loyal Visitors" -&gt; Visitor_Sessions &gt; 10, "All Else" -&gt; True) cria uma dimensão que classifica Visitantes em três grupos - Visitantes únicos são aqueles com somente uma Sessão, Visitantes muito fiéis são aqueles com mais de dez Sessões e todos os outros Visitantes têm um valor de "Todos os outros". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>bucket(Level, Metric, Count, Format {, Start {, Size}? }?) </p> </td> 
   <td colname="col2"> <p>Define uma dimensão cujos elementos são intervalos de números (de tamanho fixo, por exemplo, [0-9], [10-19],...). Os elementos de Nível estão relacionados ao elemento do fluxo de bucket cujo intervalo contém o valor de Métrica para esse elemento de nível. Formato é a string de formato printf usada para formatar os elementos de Métrica. </p> <p>Exemplo: Se Page_Duration_Minutes for uma dimensão em nível de Exibição de página que representa o número de minutos gastos em cada página, então bucket(Session, sum(Page_Duration_Minutes, Page_View), 100, "%0.0f minutes", 0, 5) é uma dimensão em nível de sessão que representa o número de minutos gastos em cada Sessão; seus elementos são intervalos de 5 minutos <code>{[0-5), [5-10),...,[495-500)}</code>. </p> <p>Start é o valor inicial do primeiro intervalo (padrão: 0) e Size é o tamanho do intervalo (padrão: 1). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prefixo(Nível {,ElementoName-&gt;(Prefixo{,Prefixo}* )}* ) </p> </td> 
   <td colname="col2"> <p>Define uma dimensão cujos elementos são as cadeias de caracteres ElementName fornecidas e estão associados aos conjuntos correspondentes de cadeias de caracteres Prefix. Os elementos de Nível estão relacionados ao elemento do prefixo dim, que está associado ao prefixo mais longo que corresponde ao nome do elemento de nível especificado. Os prefixos que terminam com o caractere especial '$' devem ser correspondidos exatamente. </p> <p>Por exemplo, o prefixo (URI, "Produtos" -&gt; ("/produtos/"), "Serviços" -&gt; ("/serviços/", "/products/service/"), "Garantias" -&gt; ("/products/warranty.html$", "/services/warranty.html$", "Tudo o resto" -&gt; ("/")) cria uma dimensão que classifica URIs nas quatro categorias listadas. O efeito em várias páginas é o seguinte: </p> <p>/products/warranty.html Entra na garantia, já que corresponde exatamente ao prefixo /products/warranty.html$. </p> <p>/products/cars/specialcar.html entra em Produtos, pois corresponde ao prefixo /products/ e não possui mais o prefixo </p> <p>/products/service/something.html Entre em Serviços, pois corresponde ao prefixo /products/service/ que é maior que o prefixo /products/. </p> <p>/companyinfo/aboutus.html entre na categoria "Tudo o resto", já que o único prefixo correspondente é "/". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>latência(Nível, Clipe, Dim, Filtro, MaxBefore, MaxAfter, FormatString) </p> </td> 
   <td colname="col2"> <p>Consulte <a href="../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/t-create-ltncy-dims.md#task-6d46ea8c89a047318d9c71bf105ef64a"> Criando Dimension de Latência </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>produto_cartesiano(Separador {,Dim}*) </p> </td> 
   <td colname="col2"> <p>Define uma dimensão cujos elementos são todas as combinações ("produto cartesiano") dos elementos das dimensões fornecidas. O nome de cada elemento é feito da concatenação dos elementos correspondentes nas dimensões de entrada, separados pela string de Separador fornecida. </p> <p>Por exemplo, se a dimensão D1 tem elementos {"a", "b"} e a dimensão D2 tem os elementos {"x", "y"}, em seguida, produto cartesiano("-", D1, D2) tem os elementos {"a-x", "a-y", "b-x", "b-y"}. </p> <p>Observe que internamente, cada uma das dimensões de entrada é tratada como se o número de seus elementos fosse a próxima potência mais alta de duas. Isso resulta no fato de o produto da carésia ter alguns elementos fictícios. Ao usar a API do Data Workbench, dependendo do formato de saída, esses elementos podem ser omitidos ou podem ser mostrados como "#nn", onde nn é o ordinal do elemento (e deve ser ignorado pelo cliente). </p> <p>Por exemplo, no exemplo acima, se D2 tivesse os três elementos {"x", "y", "z"}, ele seria tratado como se tivesse quatro elementos, e o produto cartesiano teria os elementos {"a-x", "a-y", "a-z", "#3", "b-x", "b-y", "b-z", "#7"}. </p> <p>Se nenhuma dimensão for fornecida, o resultado será uma dimensão com um elemento, "#0", que é equivalente à dimensão Nenhum. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>next_countable(Dim) </p> </td> 
   <td colname="col2"> <p>Refere-se a uma dimensão já existente: o ancestral contável mais próximo de Dim no schema. Por exemplo, o URI mais próximo é idêntico ao Page_View. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>normalized(Dim,Count) </p> </td> 
   <td colname="col2"> <p>Define uma dimensão normalizada da dimensão denormal Dim, com até elementos Count. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>last_n(Dim, TimeMetric, FormatString, Count, Offset, TrimToData {, WeekStart}?) </p> </td> 
   <td colname="col2"> <p>Define uma dimensão que tem um subconjunto dos elementos da dimensão Dim, cujos elementos representam fatias de tempo — por exemplo, dias, semanas ou anos. </p> <p>O subconjunto é um intervalo ao redor de um tempo especificado, o valor da métrica constante TimeMetric, que é interpretado como um valor de tempo em segundos desde a meia-noite UTC de 1º de janeiro de 1970. O intervalo tem elementos Count, o último dos quais são elementos Offset após o elemento Dim fornecido, cujo nome é o resultado da formatação do valor da métrica com a string FormatString fornecida. FormatString usa o mesmo % escape que a função da biblioteca C padrão strftime. </p> <p>Se trimToData for verdadeiro, todos os elementos no início da dimensão resultante, que seria antes do início de Dim, serão removidos. Quando for falso, sempre haverá o número exato de elementos especificados por Count. Observe que sempre pode haver elementos no final da dimensão resultante que não estejam realmente no Dim. </p> <p>O WeekStart opcional, se especificado, deve ser um dos {"Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" }. Ela modifica TimeMetric ao movê-la para trás até a ocorrência mais recente desse dia da semana. </p> <p>Exemplo: Se Week tiver os elementos { "10/03/10", "10/10/10", ..., "12/12/10" } e a métrica As de incorporada tiver o valor 1292348109 (representando um tempo em meados de 14 de dezembro de 20 10), depois último n(Semana, As_Of, "%m/%d/%y", 4, 0, falso, "Sun") define a dimensão com elementos { "12/12/10", "12/19/10", "12/23/10", "12/30/10" } . </p> <p>Exemplo 2: Se a dimensão Semana tiver apenas elementos {"12/19/10", "12/26/10", ..., "01/30/11"} e a métrica As de estiver acima, então última n (Semana, As_Of, "%m/%d/%y", 4, 0, true, "Sun") fornecerá uma dimensão com elementos {"12/19/10", "12/23/10", "12/30/10"}. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_previous_months(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Define uma dimensão que tem um subconjunto dos elementos de Dim, cujos elementos representam dias. O subconjunto é um intervalo ao redor de um tempo especificado, o valor da métrica constante TimeMetric, que é interpretado como um valor de tempo em segundos desde a meia-noite UTC de 1º de janeiro de 1970. O intervalo incluirá os elementos correspondentes a cada dia nos meses n anteriores ao horário especificado. Se includeThisMonth for verdadeiro, o intervalo também inclui cada dia do mês que contém a hora especificada. </p> <p>FormatString especifica a formatação dos elementos de Dim, usando escape "%" como no strftime da função de biblioteca C padrão. </p> <p>Se trimToData for verdadeiro, todos os elementos no início da dimensão resultante, que seria antes do início de Dim, serão removidos. Quando for falso, sempre haverá o número exato de elementos especificados por Count. Observe que sempre pode haver elementos no final da dimensão resultante que não estejam realmente no Dim. </p> <p>Exemplo: Se Day tiver os elementos { "01/01/10", "01/02/10", ..., "12/31/10" } e a métrica As de incorporada tiver o valor 1292348109 (representando um horário em meados de 14 de dezembro de 20 10), em seguida, dias dos meses anteriores (Dia, As_De, "%m/%d/%y", 2, falso, falso) terão elementos { "10/01/10", "10/02/10", ..., "11/30/10" }. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_current_month(Dim, TimeMetric, FormatString, allMonth, trimToData) </p> </td> 
   <td colname="col2"> <p>Semelhante aos dias dos meses anteriores, exceto que os elementos correspondem apenas a dias do mesmo mês que o tempo especificado pela Métrica de tempo. Se allMonth for verdadeiro, haverá um elemento para cada dia do mês apropriado; caso contrário, somente os dias desde o primeiro do mês apropriado até o dia que contém a hora especificada farão parte da dimensão. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_Future_months(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Semelhante aos dias dos meses anteriores, exceto que os elementos correspondem aos dias dos meses seguintes, em vez de antes, ao mês que contém o tempo especificado por TimeMetric. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hours_of_day(Dim, Metric, TimeFormatString, nDaysForward, TrimData) </p> </td> 
   <td colname="col2"> <p>Define uma dimensão que tem um subconjunto dos elementos de Dim, cujos elementos representam horas. O subconjunto é um intervalo ao redor de um tempo especificado, o valor da métrica constante TimeMetric, que é interpretado como um valor de tempo em segundos desde a meia-noite UTC de 1º de janeiro de 1970. O intervalo inclui os elementos correspondentes a cada hora do dia em DaysForward após o dia que contém a hora especificada por TimeMetric. </p> <p>FormatString especifica a formatação dos elementos de Dim, usando escape "%" como no strftime da função de biblioteca C padrão. A string de formato sempre deve exibir uma string representando meia-noite no início do dia do tempo passado. </p> <p>Se trimToData for verdadeiro, todos os elementos no início da dimensão resultante, que seria antes do início de Dim, serão removidos. Quando for falso, sempre haverá o número exato de elementos especificados por Count. Observe que sempre pode haver elementos no final da dimensão resultante que não estejam realmente no Dim. </p> <p>Exemplo: Se a Hora tiver os elementos { "01/01/10 00:00", "01/01/10 01:00", ..., "12/31/10 23:00" } e a métrica A partir integrada tiver o valor 1292348 109 (representando uma hora em meados de 14 de dezembro de 2010), em seguida horas do dia (Hora, As_Of, "%x 00:00", 0, false) tem elementos { "12/12/10 00:00", "12/12/10 0 01:00" , ..., "12/12/10 23:00" }. </p> </td> 
  </tr> 
 </tbody> 
</table>
