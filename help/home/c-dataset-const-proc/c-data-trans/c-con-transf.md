---
description: Tabela que mostra quais convenções se aplicam ao construir transformações.
solution: Analytics
title: Convenções para a construção de transformações
topic: Data workbench
uuid: 91dddca6-4c17-4107-b78b-0f8b8870ef8d
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Convenções para a construção de transformações{#conventions-for-constructing-transformations}

Tabela que mostra quais convenções se aplicam ao construir transformações.

<table id="table_BEB0F6C416D144B5A2DD3D1A21613B21"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Convenção </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Execução sequencial </td> 
   <td colname="col2"> <p>As transformações dentro de um arquivo de configuração de conjunto de dados são aplicadas às entradas de log sequencialmente (isto é, na ordem em que estão listadas no arquivo de configuração). Por conseguinte, as transformações devem ser enumeradas na ordem em que os seus resultados são utilizados como entradas para outras transformações. Mais especificamente, se a saída de uma transformação for usada como entrada para outra transformação, é importante que essa transformação anterior seja listada antes da última transformação nos arquivos de configuração do conjunto de dados. Caso contrário, o servidor da análise de big data gera um erro. </p> <p> Os estágios de processamento fornecem uma maneira de ordenar as transformações definidas em vários conjuntos de dados que incluem arquivos. Para todo o conjunto de dados incluir arquivos associados a um estágio de processamento específico, as transformações são ordenadas com base em suas entradas e saídas. Além disso, se vários conjuntos de dados incluírem arquivos em um estágio e os dados de saída forem exibidos no mesmo campo como resultado de uma transformação, o servidor da análise de big data gerará um erro. </p> <p> Para obter mais informações sobre estágios, consulte Arquivo <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> de configuração de processamento de</a>log, Arquivo <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md"> de configuração de</a>transformação e <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Arquivo</a>de inclusão de conjunto de dados. </p> <p>Um Mapa <span class="wintitle"> de dependência de</span> transformação pode exibir como um campo é modificado por uma série de transformações. Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md"> Ferramentas</a>de configuração do conjunto de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nomes de saída </td> 
   <td colname="col2"> A maioria das transformações especifica um campo de saída. Se a saída for um campo estendido definido pelo usuário, o nome desse campo deve começar com "x-". Os nomes dos campos de saída não podem conter espaços ou caracteres especiais. Os nomes dos campos estendidos podem ser escritos com letras maiúsculas e minúsculas, como "x-NewCampaignName" ou "x-New-Campaign-Name", mas são tratados pelo software como não diferenciando maiúsculas de minúsculas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campos de entrada </td> 
   <td colname="col2"> <p>Os campos de entrada referem-se a um dos campos de linha de base ou a um campo criado pelo usuário resultante da saída de uma transformação anterior. Se uma string constante for necessária, uma string entre aspas poderá ser usada em vez de uma linha de base ou de um campo criado pelo usuário. </p> <p> Para obter uma lista de alguns dos campos de dados definidos com frequência que o servidor da análise de big data pode processar, consulte Campos <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md"> de registro de dados de</a>evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Strings simples e vetores de strings </td> 
   <td colname="col2"> Todas as transformações operam em sequências de caracteres e/ou vetores de sequências de caracteres. Sequências simples são sequências literais de caracteres. Os vetores de string contêm zero ou sequências de caracteres mais simples em uma ordem específica. </td> 
  </tr> 
 </tbody> 
</table>

