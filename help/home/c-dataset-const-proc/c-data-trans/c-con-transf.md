---
description: Tabela que mostra quais convenções se aplicam ao construir transformações.
title: Convenções para a construção de transformações
uuid: 91dddca6-4c17-4107-b78b-0f8b8870ef8d
exl-id: c2552c52-c6d3-4c9f-8359-b5a58bf1a59f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 2%

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
   <td colname="col2"> <p>As transformações em um arquivo de configuração de conjunto de dados são aplicadas às entradas de log sequencialmente (ou seja, na ordem em que são listadas no arquivo de configuração). Por conseguinte, as transformações devem ser enumeradas na ordem em que os seus resultados são utilizados como fatores de produção para outras transformações. Mais especificamente, se a saída de uma transformação for usada como entrada para outra transformação, é importante que essa transformação anterior seja listada antes da última transformação nos arquivos de configuração do conjunto de dados. Caso contrário, o servidor do Data Workbench gera um erro. </p> <p> As etapas de processamento fornecem uma maneira de ordenar as transformações definidas em vários arquivos de inclusão do conjunto de dados. Para todos os arquivos de inclusão do conjunto de dados associados a um estágio de processamento específico, as transformações são ordenadas com base em suas entradas e saídas. Além disso, se vários conjuntos de dados incluírem arquivos dentro de um estágio de dados de saída para o mesmo campo como resultado de uma transformação, o servidor do Data Workbench gerará um erro. </p> <p> Para obter mais informações sobre estágios, consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Arquivo de configuração de processamento de log</a>, <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md"> Arquivo de configuração de transformação</a> e <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Arquivos de inclusão do conjunto de dados</a>. </p> <p>Um <span class="wintitle"> Mapa de dependência de transformação</span> pode exibir como um campo é modificado por uma série de transformações. Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md"> Ferramentas de configuração do conjunto de dados</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nomes de saída </td> 
   <td colname="col2"> A maioria das transformações especifica um campo de saída. Se a saída for um campo estendido definido pelo usuário, o nome desse campo deverá começar com "x-". Os nomes de campo de saída não podem conter espaços ou caracteres especiais. Os nomes dos campos estendidos podem ser escritos com letras maiúsculas e minúsculas misturadas, como "x-NewCampaignName" ou "x-New-Campaign-Name" para facilitar a leitura, mas são tratados pelo software como não diferenciando maiúsculas de minúsculas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campos de entrada </td> 
   <td colname="col2"> <p>Os campos de entrada se referem a um dos campos de linha de base ou a um campo criado pelo usuário resultante da saída de uma transformação anterior. Se uma string constante for necessária, uma string entre aspas poderá ser usada em vez de uma linha de base ou de um campo criado pelo usuário. </p> <p> Para obter uma lista de alguns dos campos de dados definidos com frequência que o servidor do Data Workbench pode processar, consulte <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md"> Campos de registro de dados do evento</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sequências de caracteres simples e vetores de cadeias de caracteres </td> 
   <td colname="col2"> Todas as transformações operam em strings e/ou vetores de strings. Sequências simples são sequências literais de caracteres. Os vetores de string contêm zero ou strings mais simples em uma ordem específica. </td> 
  </tr> 
 </tbody> 
</table>
