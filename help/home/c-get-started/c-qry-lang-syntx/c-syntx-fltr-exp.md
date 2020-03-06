---
description: Um filtro é uma expressão que define um subconjunto dos dados em um conjunto de dados.
solution: Analytics
title: Sintaxe para expressões de filtro
topic: Data workbench
uuid: faeb6847-3295-48ab-9d1c-db00f57647ba
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sintaxe para expressões de filtro{#syntax-for-filter-expressions}

Um filtro é uma expressão que define um subconjunto dos dados em um conjunto de dados.

Um filtro admite ou rejeita cada elemento de cada dimensão de acordo com as relações entre dimensões.

Os filtros podem ser editados usando o [!DNL Filter Editor]. Consulte Editores [de filtro](../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).

Na tabela a seguir, cada descrição de sintaxe inclui um exemplo de uma expressão de métrica usando esse filtro. Por exemplo,[SessionsTrue] é uma métrica definida usando o filtro &quot;True&quot;. A métrica[SessionsTrue] é a mesma da métrica Sessões porque o filtro True admite todos os elementos da dimensão Sessão.

<table id="table_5D66E6C11B384460BAAA7A6130214594"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Verdadeiro </p> </td> 
   <td colname="col2"> <p>Filtro constante. Admite todos os elementos de cada dimensão </p> <p>Exemplo: Sessões[ Verdadeiro ] é o mesmo que Sessões. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Falso </p> </td> 
   <td colname="col2"> <p>Filtro constante. Rejeita cada elemento de cada dimensão. </p> <p>Exemplo: Sessões[ False ] é sempre zero. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>não filtrar </p> </td> 
   <td colname="col2"> <p>Admite elementos que o Filtro rejeita. </p> <p>Exemplo: Sessões[ not Page="A" ] é o número de Sessões que não visitaram a página A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FiltroA e FiltroB </p> </td> 
   <td colname="col2"> <p>Admite elementos que os filtrosA e FilterB admitem. </p> <p>Exemplo: Sessões[ Page="A" e Page="B" ] é o número de Sessões que visitaram as páginas A e B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FiltroA ou FiltroB </p> </td> 
   <td colname="col2"> <p>Admite elementos que o FilterA ou o FilterB admitem. </p> <p>Exemplo: Sessões[ Page="A" ou Page="B" ] é o número de Sessões que visitaram as páginas A, B ou ambas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filtrar por Esmaecimento </p> </td> 
   <td colname="col2"> <p>Admite o conjunto de elementos da dimensão Dim que são admitidos pelo Filtro. </p> <p>Exemplo: Sessões[ Page="/home" do Visitante ] é o número de Sessões pertencentes a um Visitante que visualizou a Página "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identificador </p> </td> 
   <td colname="col2"> <p>Filtros de referência definidos de outra forma no perfil. </p> <p>Exemplo: Sessões[ Broken_Session_Filter ] é o número de Sessões admitidas pelo Filtro de Sessão Quebrado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim = "Value" </p> </td> 
   <td colname="col2"> <p>Admite o elemento especificado da dimensão Dim. </p> <p>Exemplo: Sessões[ Page="A" ] é o número de Sessões que visitaram a Página A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; "Value" </p> <p>Dim!= “Valor” </p> </td> 
   <td colname="col2"> <p>Admite todos os outros elementos da dimensão Dim. </p> <p>Exemplo: Sessões[ Página&lt;&gt;"A" ] é o número de Sessões que visitaram qualquer página diferente de A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim = #Ordinal </td> 
   <td colname="col2"> <p>Admite o elemento da dimensão Dim com o valor ordinal especificado. </p> <p>Exemplo: Sessões[ Mês=#0 ] é o número de Sessões no primeiro mês do conjunto de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; #Ordinal </p> <p>Dim!= #Ordinal </p> </td> 
   <td colname="col2"> <p>Admite todos os outros elementos da dimensão Dim. </p> <p>Exemplo: Sessões[ Session_Value &lt;&gt; #0 ] é o número de Sessões com um Valor de Sessão diferente de zero. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim corresponde a "Expr" </p> </td> 
   <td colname="col2"> <p>Admite os elementos da dimensão Dim que correspondem à expressão regular fornecida. Dim não deve ser uma dimensão desnormalizada ou contável. </p> <p>Exemplo: Sessions[ URI corresponde a ".*/produto/.*" ] é o número de Sessões que visitaram qualquer página em um diretório de produto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim não corresponde a "Expr" </p> </td> 
   <td colname="col2"> <p>Admite os elementos da dimensão Dim que não correspondem à expressão regular fornecida. Dim não deve ser uma dimensão desnormalizada ou contável. </p> <p>Exemplo: Sessões[ URI não corresponde a ".*\.jsp" ] é o número de Sessões que visitaram qualquer página que não era uma página JSP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt; "Value" </p> </td> 
   <td colname="col2"> <p>Admite os elementos da dimensão Dim com valores ordinais menores que o valor ordinal do elemento "Valor". Se "Valor" não for um elemento de dimensão, presume-se que seja maior que qualquer elemento atual da dimensão. </p> <p>Exemplo: Sessões[ Mês &lt; "jul ‘04" ] é o número de Sessões realizadas antes de julho de 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esmaecer &gt; "Valor" </p> </td> 
   <td colname="col2"> <p>Admite os elementos da dimensão Dim com valores ordinais maiores que o valor ordinal do elemento "Valor". Se "Valor" não for um elemento de dimensão, presume-se que seja maior que qualquer elemento atual da dimensão. </p> <p>Exemplo: Sessões[ Mês &gt; "Julho de 2004" ] é o número de Sessões realizadas após julho de 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;= "Value" </p> </td> 
   <td colname="col2"> <p>Admite os elementos da dimensão Dim com valores ordinais menores ou iguais ao valor ordinal do elemento "Valor". Se "Valor" não for um elemento de dimensão, presume-se que seja maior que qualquer elemento atual da dimensão. </p> <p>Exemplo: Sessões[ Session_Number &lt;= "2" ] é o número de Sessões que foram a primeira ou a segunda sessão de um visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim &gt;= "Valor" </td> 
   <td colname="col2"> <p>Admite os elementos da dimensão Dim com valores ordinais maiores ou iguais ao valor ordinal do elemento "Valor". Se "Valor" não for um elemento de dimensão, presume-se que seja maior que qualquer elemento atual da dimensão. </p> <p>Exemplo: Sessões[ Session_Number &gt;= "5" ] é o número de sessões que foram a quinta ou maior sessão de um visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>qualquer extremidade </p> </td> 
   <td colname="col2"> <p>Admite todos os elementos da dimensão Dim. </p> <p>Exemplo: Sessões[ any Page_View ] é o número de sessões com pelo menos uma exibição de página. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sem interrupção </p> </td> 
   <td colname="col2"> <p>Admite elementos que qualquer Dim rejeita. </p> <p>Exemplo: Sessões[ sem Page_View ] é o número de sessões sem uma exibição de página. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(FILTRO) </p> </td> 
   <td colname="col2"> <p>O mesmo que FILTER; usado para agrupar uma parte de uma expressão de filtro. </p> </td> 
  </tr> 
 </tbody> 
</table>

