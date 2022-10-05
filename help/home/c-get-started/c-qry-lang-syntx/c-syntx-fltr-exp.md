---
description: Um filtro é uma expressão que define um subconjunto de dados em um conjunto de dados.
title: Sintaxe para expressões de filtro
uuid: faeb6847-3295-48ab-9d1c-db00f57647ba
exl-id: 515c1645-69c8-4990-a913-d2d505c6fe51
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 1%

---

# Sintaxe para expressões de filtro{#syntax-for-filter-expressions}

{{eol}}

Um filtro é uma expressão que define um subconjunto de dados em um conjunto de dados.

Um filtro admite ou rejeita cada elemento de cada dimensão de acordo com as relações entre dimensões.

Os filtros podem ser editados usando o [!DNL Filter Editor]. Consulte [Editores de filtro](../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).

Na tabela a seguir, cada descrição de sintaxe inclui um exemplo de expressão de métrica usando esse filtro. Por exemplo, Sessões[Verdadeiro] é uma métrica definida usando o filtro &quot;Verdadeiro&quot;. As sessões[Verdadeiro] é igual à métrica Sessões , pois o filtro Verdadeiro admite cada elemento da dimensão Sessão .

<table id="table_5D66E6C11B384460BAAA7A6130214594"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Verdadeiro </p> </td> 
   <td colname="col2"> <p>Filtro constante. Admite cada elemento de cada dimensão </p> <p>Exemplo: Sessões[ True ] é o mesmo que Sessões. </p> </td> 
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
   <td colname="col1"> <p>FilterA e FilterB </p> </td> 
   <td colname="col2"> <p>Admite elementos que o FilterA e o FilterB admitem. </p> <p>Exemplo: Sessões[ Page="A" e Page="B" ] é o número de Sessões que visitaram as páginas A e B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA ou FilterB </p> </td> 
   <td colname="col2"> <p>Admite elementos que o FilterA ou o FilterB admitem. </p> <p>Exemplo: Sessões[ Page="A" ou Page="B" ] é o número de Sessões que visitaram as páginas A, B ou ambas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filtrar por atenuação </p> </td> 
   <td colname="col2"> <p>Admite o conjunto de elementos da dimensão Dim que são admitidos por Filtro. </p> <p>Exemplo: Sessões[ Page="/home" de Visitante ] é o número de Sessões pertencentes a um Visitante que viu a Página "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identificador </p> </td> 
   <td colname="col2"> <p>Faça referência aos filtros definidos do contrário no perfil. </p> <p>Exemplo: Sessões[ Broken_Session_Filter ] é o número de Sessões admitidas pelo Filtro de Sessões Quebradas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim = "Valor" </p> </td> 
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
   <td colname="col2"> <p>Admite todos os outros elementos da dimensão Dim. </p> <p>Exemplo: Sessões[ Session_Value &lt;&gt; #0 ] é o número de Sessões que têm um Valor de Sessão diferente de zero. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim corresponde a "Expr" </p> </td> 
   <td colname="col2"> <p>Admite os elementos da dimensão Dim que correspondem à expressão regular fornecida. Dim não deve ser uma dimensão denormal ou contável. </p> <p>Exemplo: Sessões[ URI corresponde a ".*/produto/.*" ] é o número de Sessões que visitaram qualquer página em um diretório de produto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim não corresponde a "Expr" </p> </td> 
   <td colname="col2"> <p>Admite os elementos da dimensão Dim que não correspondem à expressão regular fornecida. Dim não deve ser uma dimensão denormal ou contável. </p> <p>Exemplo: Sessões[ URI não corresponde a ".*\.jsp" ] é o número de Sessões que visitaram qualquer página que não era uma página JSP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt; "Value" </p> </td> 
   <td colname="col2"> <p>Admite os elementos da dimensão Dim com valores ordinais inferiores ao valor ordinal do elemento "Valor". Se "Valor" não for um elemento de dimensão, será considerado maior do que qualquer elemento atual da dimensão. </p> <p>Exemplo: Sessões[ Mês &lt; "julho de 2004" ] é o número de Sessões realizadas antes de julho de 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Escuro &gt; "Valor" </p> </td> 
   <td colname="col2"> <p>Admite os elementos da dimensão Dim com valores ordinais maiores que o valor ordinal do elemento "Valor". Se "Valor" não for um elemento de dimensão, será considerado maior do que qualquer elemento atual da dimensão. </p> <p>Exemplo: Sessões[ Mês &gt; "julho de 2004" ] é o número de Sessões realizadas após julho de 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;= "Value" </p> </td> 
   <td colname="col2"> <p>Admite os elementos da dimensão Dim com valores ordinais menores ou iguais ao valor ordinal do elemento "Valor". Se "Valor" não for um elemento de dimensão, será considerado maior do que qualquer elemento atual da dimensão. </p> <p>Exemplo: Sessões[ Session_Number &lt;= "2" ] é o número de Sessões que foram a primeira ou a segunda sessão de um visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim &gt;= "Valor" </td> 
   <td colname="col2"> <p>Admite os elementos da dimensão Dim com valores ordinais maiores ou iguais ao valor ordinal do elemento "Valor". Se "Valor" não for um elemento de dimensão, será considerado maior do que qualquer elemento atual da dimensão. </p> <p>Exemplo: Sessões[ Session_Number &gt;= "5" ] é o número de sessões que foram a quinta ou maior sessão de um visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>qualquer Dim </p> </td> 
   <td colname="col2"> <p>Admite todos os elementos da dimensão Dim. </p> <p>Exemplo: Sessões[ any Page_View ] é o número de sessões com pelo menos uma exibição de página. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sem Dim </p> </td> 
   <td colname="col2"> <p>Admite elementos que qualquer Dim rejeitar. </p> <p>Exemplo: Sessões[ no Page_View ] é o número de sessões sem uma exibição de página. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(FILTRO) </p> </td> 
   <td colname="col2"> <p>O mesmo que FILTER; usado para agrupar uma parte de uma expressão de filtro. </p> </td> 
  </tr> 
 </tbody> 
</table>
