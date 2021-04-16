---
description: Informações sobre as transformações que podem ser usadas para incorporar dados de pesquisa ao conjunto de dados.
title: Definir transformações de pesquisa
uuid: 4f7358b1-9e6a-4d03-b0c6-411e454fc11e
exl-id: 7b1504be-8669-4340-8400-e33f9663b602
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '2288'
ht-degree: 3%

---

# Definir transformações de pesquisa{#defining-lookup-transformations}

Informações sobre as transformações que podem ser usadas para incorporar dados de pesquisa ao conjunto de dados.

Observe que nem todos os tipos podem ser usados durante ambas as fases do processo de construção do conjunto de dados.

* [Categorizar](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-8474376c14e54d14ae73749696ada468)
* [FlatFileLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-e09b2eeb96444a859b14f03cdaab31f2)
* [ODBCLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-4dcc3747e42e45c0a057e85f308a83cc)

## Categorize {#section-8474376c14e54d14ae73749696ada468}

A transformação [!DNL Categorize] usa uma tabela de pesquisa de duas colunas composta de pares de string/valor de padrão. Durante essa transformação, o servidor do Data Workbench lê cada registro de dados do evento e compara o conteúdo de um campo designado no registro a cada uma das strings de padrão listadas na primeira coluna da tabela de pesquisa. Se o campo designado corresponder a uma das strings de padrão, o servidor do Data Workbench gravará o valor (encontrado na segunda coluna) associado a essa string de padrão em um campo de saída designado no registro.

As cadeias de caracteres na primeira coluna da tabela de pesquisa podem, opcionalmente, começar com o caractere ^ e/ou terminar no caractere $ para forçar a correspondência no início e/ou no fim. Essa transformação não aceita expressões regulares para definir condições de correspondência na primeira coluna. Se o valor de entrada for um vetor de cadeias de caracteres, cada cadeia de caracteres será executada pela transformação e os resultados serão anexados a um vetor de cadeia de caracteres de saída.

Uma transformação [!DNL Categorize] geralmente é mais fácil e rápida do que usar uma transformação [!DNL Regular Expression] para fazer a mesma coisa.

>[!NOTE]
>
>O teste de substring usado em [!DNL Categorize] diferencia maiúsculas de minúsculas, a menos que especificado de outra forma usando o parâmetro [!DNL Case Sensitive].

<table id="table_1773344FAAE34BD4919CC4414249FDEE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Nome descritivo da transformação. Você pode inserir qualquer nome aqui. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Diferenciação de maiúsculas e minúsculas </td> 
   <td colname="col2"> Verdadeiro ou falso. Especifica se o teste de substring faz distinção entre maiúsculas e minúsculas. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Observações sobre a transformação. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição </td> 
   <td colname="col2"> Condições de aplicação desta transformação. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Padrão </td> 
   <td colname="col2"> O valor padrão a ser usado se o teste de condição for aprovado e nenhuma entrada no arquivo de categorização corresponder à entrada, ou o campo de entrada não for definido na entrada de log fornecida. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Delimitador </td> 
   <td colname="col2"> <p>Sequência de caracteres usada para separar as colunas no arquivo de pesquisa. Deve ter um único caractere de comprimento. </p> <p> Se você pressionar a tecla Ctrl e clicar com o botão direito do mouse no parâmetro Delimitador, um menu <span class="wintitle"> Inserir</span> é exibido. Esse menu contém uma lista de caracteres especiais que geralmente são usados como delimitadores. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Múltiplos valores </td> 
   <td colname="col2"> Verdadeiro ou falso. Se verdadeiro, quando várias linhas no arquivo correspondem à entrada, cada correspondência resulta em um valor anexado ao vetor de saída das cadeias de caracteres. Se false, somente a primeira linha correspondente no arquivo será usada na saída. Neste último caso, se a entrada for um vetor, a saída também será um vetor de comprimento equivalente. Se a entrada for uma string simples, a saída também será uma string simples. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Arquivo </td> 
   <td colname="col2"> Caminho e nome do arquivo de categorização. Caminhos relativos referem-se ao diretório de instalação do servidor do Data Workbench. Normalmente, esse arquivo está localizado no diretório Lookups no diretório de instalação do servidor do Data Workbench. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> O arquivo de categorização corresponde suas subsequências em relação ao valor desse campo para identificar a linha correspondente no arquivo. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Saída </td> 
   <td colname="col2"> O nome do campo associado ao resultado. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**Considerações para categorizar**

* As alterações nos arquivos de pesquisa em [!DNL Categorize] transformações definidas no arquivo [!DNL Transformation.cfg] ou em um arquivo [!DNL Transformation Dataset Include] exigem a retransformação do conjunto de dados. Os arquivos de pesquisa para [!DNL Categorize] transformações definidas no arquivo [!DNL Log Processing.cfg] ou [!DNL Log Processing Dataset Include] não estão sujeitos a essa limitação. Para obter informações sobre como reprocessar seus dados, consulte [Reprocessando e Retransformação](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL Categorize] transformações definidas no  [!DNL Log Processing.cfg] arquivo ou um  [!DNL Log Processing Dataset Include] arquivo recarrega seus arquivos de pesquisa sempre que os arquivos de pesquisa são alterados. As alterações não são aplicadas retroativamente, mas se aplicam a todos os dados de log lidos após a alteração.

Este exemplo ilustra o uso da transformação [!DNL Categorize] para integrar dados de pesquisa com dados de evento coletados do tráfego do site. Suponha que um site específico tenha seções de negócios e que haja um requisito para poder observar e fazer comparações com base no fluxo de tráfego e no valor gerado pelas diferentes seções. Você pode criar um arquivo de pesquisa que lista as subsequências de caracteres usadas para identificar essas diferentes seções.

O arquivo de pesquisa [!DNL Lookups\custommap.txt] contém a seguinte tabela:

| /produtos/ | Produtos |
|---|---|
| ^/esportes/ | Esportes |
| ^/notícias/ | Notícias |
| ... | ... |

Esse arquivo de categorização mapeia qualquer coisa que contenha a string &quot;/products/&quot; para o valor &quot;Produtos&quot;, qualquer coisa que comece com &quot;/esportivos/&quot; para o valor &quot;Esportes&quot; e qualquer coisa que comece com &quot;/news/&quot; para o valor &quot;Notícias&quot;. A transformação de categorização a seguir usa o valor no campo cs-uri-stem como a string na qual estamos procurando uma substring correspondente. O resultado da transformação é colocado no campo x-custommap.

![](assets/cfg_TransformationType_Categorize.png)

Supondo que o parâmetro de Vários Valores esteja definido como false, o exemplo produziria os seguintes valores para x-custommap, dados os valores listados para cs-uri-stem.

| [!DNL cs-uri-stem] | [!DNL x-custommap] |
|---|---|
| [!DNL /sports/news/today.php] | Esportes |
| [!DNL /sports/products/buy.php] | Produtos |
| [!DNL /news/headlines.php] | Notícias |
| [!DNL /news/products/subscribe.php] | Produtos |

A saída é baseada na ordem das subsequências no arquivo de pesquisa. Por exemplo, o cs-uri-stem [!DNL /sports/products/buy.php] retorna &quot;Produtos&quot;. Embora o fluxo do URI comece com &quot;/esportista/&quot;, a sequência &quot;/products/&quot; é listada antes de &quot;/esportista/&quot; no arquivo de pesquisa. Se o parâmetro Valores múltiplos fosse definido como true, haveria um valor adicional para x-custommap, já que o último exemplo corresponderia a duas linhas na tabela de pesquisa: Produtos e notícias.

## FlatFileLookup {#section-e09b2eeb96444a859b14f03cdaab31f2}

A transformação [!DNL FlatFileLookup] usa uma tabela de pesquisa composta por qualquer número de colunas e linhas (embora, lembre-se de que ela reside na memória). Durante esse tipo de transformação, o servidor do Data Workbench lê cada registro de dados do evento e compara o conteúdo de um campo designado no registro a cada um dos valores em uma coluna designada da tabela de pesquisa. Se houver uma correspondência, o servidor do Data Workbench grava um ou mais valores da linha correspondente na tabela de pesquisa em um ou mais campos de saída designados no registro de dados do evento.

A tabela de pesquisa usada durante essa transformação é preenchida a partir de um arquivo simples cujo local é especificado ao definir a transformação.

<table id="table_772B8ABF3B44493F99069010DDB5F77A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Nome descritivo da transformação. Você pode inserir qualquer nome aqui. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Observações sobre a transformação. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição </td> 
   <td colname="col2"> Condições de aplicação desta transformação. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Padrão </td> 
   <td colname="col2"> O valor padrão a ser usado se a condição for atendida e se nenhuma entrada no arquivo de pesquisa corresponder à entrada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Delimitador </td> 
   <td colname="col2"> <p>Sequência de caracteres usada para separar as colunas no arquivo de pesquisa. Deve ter um único caractere de comprimento. </p> <p> Se você pressionar a tecla Ctrl e clicar com o botão direito do mouse no parâmetro Delimitador, um menu <span class="wintitle"> Inserir</span> é exibido. Esse menu contém uma lista de caracteres especiais que geralmente são usados como delimitadores. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Arquivo </td> 
   <td colname="col2"> Caminho e nome do arquivo de pesquisa. Caminhos relativos referem-se ao diretório de instalação do servidor do Data Workbench. Normalmente, esse arquivo está localizado no diretório Lookups no diretório de instalação do servidor do Data Workbench. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Linha de cabeçalho </td> 
   <td colname="col2"> Verdadeiro ou falso. Indica que a primeira linha da tabela é uma linha de cabeçalho a ser ignorada no processamento. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> <span class="wintitle"> Nome </span> da coluna é o nome da coluna usada para corresponder a entrada à(s) linha(s) no arquivo. Se Linha de cabeçalho for verdadeira, esse pode ser o nome de uma coluna no arquivo de pesquisa. Caso contrário, esse deve ser o número da coluna com base em zero para correspondência. <span class="wintitle"> Nome do </span> campo é o nome do campo usado para localizar a linha no arquivo de pesquisa. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Múltiplos valores </td> 
   <td colname="col2"> <p>Verdadeiro ou falso. Determina se um único valor (uma linha correspondente) ou vários valores devem ser retornados (um para cada linha correspondente). </p> <p> <p>Observação:  Se <span class="wintitle"> Valores múltiplos</span> for definido como falso, você deve garantir que não haja várias correspondências. Quando ocorrem várias correspondências, não há garantia de qual correspondência será retornada. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Saídas </td> 
   <td colname="col2"> <p>Um vetor de objetos de coluna (resultados) no qual cada objeto é definido por nomes de coluna e campo. </p> <p> <span class="wintitle"> Nome </span> da coluna é a coluna da qual o valor de saída é obtido. Se <span class="wintitle"> Linha do cabeçalho</span> for verdadeiro, esse poderá ser o nome de uma coluna no arquivo de pesquisa. Caso contrário, esse deve ser o número da coluna com base em zero para correspondência. </p> <p> <span class="wintitle"> Nome do </span> campo é o nome do campo usado para capturar a saída. Observe que isso pode ser um vetor de resultados, um para cada linha identificada no caso em que o parâmetro Valores Múltiplos é verdadeiro. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**Considerações para[!DNL FlatFileLookup]**

* A correspondência do campo de entrada ao arquivo de pesquisa sempre diferencia maiúsculas de minúsculas.
* As alterações nos arquivos de pesquisa em [!DNL FlatFileLookup] transformações definidas no arquivo [!DNL Transformation.cfg] ou nos arquivos [!DNL Transformation Dataset Include] exigem a retransformação do conjunto de dados. Os arquivos de pesquisa para [!DNL FlatFileLookup] transformações definidas no arquivo [!DNL Log Processing.cfg] ou nos arquivos [!DNL Log Processing Dataset Include] não estão sujeitos a essa limitação. Para obter informações sobre como reprocessar seus dados, consulte [Reprocessando e Retransformação](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL FlatFileLookup] transformações no  [!DNL Log Processing.cfg] arquivo ou  [!DNL Log Processing Dataset Include] arquivos recarregam seus arquivos de pesquisa sempre que os arquivos de pesquisa são alterados. As alterações não são aplicadas retroativamente, mas se aplicam a todos os dados de log lidos após a alteração.

Este exemplo ilustra o uso da transformação [!DNL FlatFileLookup] para integrar dados de pesquisa com dados de evento coletados do tráfego do site. Suponha que você queira isolar os parceiros do site que estão roteando o tráfego para o site e transformar suas IDs de parceiro em nomes mais amigáveis. Em seguida, é possível usar os nomes amigáveis para criar dimensões e visualizações estendidas que mapeiam mais claramente para o relacionamento comercial do que o relacionamento site a site usado para rotear o tráfego.

A transformação de exemplo pesquisa o campo cs(referrer-query) pelo par de nome-valor PartnerID e, se estiver localizado, o arquivo de pesquisa [!DNL Lookups\partners.txt] é usado para comparar o valor de PartnerID com os valores na coluna [!DNL Partner] da tabela. Se uma linha estiver localizada, o campo de saída x-partner-name receberá o nome da coluna [!DNL PrintName] da linha identificada.

![](assets/cfg_TransformationType_FlatFileLookup.png)

Se a tabela de pesquisa continha as seguintes informações:

| ID | Parceiro | Iniciado | PrintName |
|---|---|---|---|
| 1 | P154 | 21 de agosto de 1999 | Yahoo |
| 2 | P232 | 10 de julho de 2000 | Microsoft |
| 3 | P945 | 12 de janeiro de 2001 | Amazon |

Os exemplos a seguir se transformariam da seguinte maneira:

* Se cs(referrer)(PartnerID) retornasse P232, o campo x-partner-name receberia o valor &quot;Microsoft&quot;.
* Se cs(referrer)(PartnerID) retornasse P100, o campo x-partner-name receberia o valor &quot;No Partner&quot;.
* Se cs(referrer)(PartnerID) não retornasse nada, o campo x-partner-name receberia o valor &quot;No Partner&quot;, conforme especificado pelo parâmetro Default .

## ODBCLookup {#section-4dcc3747e42e45c0a057e85f308a83cc}

A transformação [!DNL ODBCLookup] funciona como uma transformação [!DNL FlatFileLookup]. A única diferença é que a tabela de pesquisa usada durante essa transformação é preenchida em um banco de dados ODBC e não em um arquivo simples.

>[!NOTE]
>
>[!DNL ODBCLookup] as transformações só podem ser executadas durante a fase de transformação do processo de construção do conjunto de dados. Quando possível, o Adobe recomenda usar a transformação [!DNL FlatFileLookup] em vez da transformação [!DNL ODBCLookup]. [!DNL FlatFileLookup] as transformações são inerentemente mais confiáveis porque não dependem da disponibilidade de um sistema externo. Além disso, há menos risco de a tabela de pesquisa ser modificada se residir em um arquivo simples que você controla localmente.

<table id="table_B903DB291BCC4F44B09D54300216D288"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Nome descritivo da transformação. Você pode inserir qualquer nome aqui. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Observações sobre a transformação. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição </td> 
   <td colname="col2"> Condições de aplicação desta transformação. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome da fonte de dados </td> 
   <td colname="col2"> Um DSN, conforme fornecido por um administrador da máquina do servidor do Data Workbench em que o conjunto de dados é processado, que se refere ao banco de dados do qual os dados devem ser carregados. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Senha do banco de dados </td> 
   <td colname="col2">A senha a ser usada na conexão com o banco de dados. Se uma senha tiver sido configurada para o DSN no <span class="wintitle"> Data Source Administrator</span>, isso pode ser deixado em branco. Qualquer senha fornecida aqui substitui a senha configurada para o DSN no <span class="wintitle"> Data Source Administrator</span>. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de usuário do banco de dados </td> 
   <td colname="col2">A ID de usuário a ser usada ao se conectar ao banco de dados. Se uma ID de usuário tiver sido configurada para o DSN no <span class="wintitle"> Administrador da Fonte de Dados</span>, isso pode ser deixado em branco. Qualquer ID de usuário fornecida aqui substitui a ID de usuário configurada para o DSN no <span class="wintitle"> Administrador da Fonte de Dados</span>. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Padrão </td> 
   <td colname="col2"> O valor padrão a ser usado se a condição for atendida e nenhuma entrada no arquivo de pesquisa corresponder à entrada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Coluna de entrada </td> 
   <td colname="col2"> <span class="wintitle"> Nome </span> da Coluna é o nome da coluna ou a expressão SQL para os dados que são correspondidos em relação à entrada. <span class="wintitle"> Nome do </span> campo é o nome do campo que contém os dados que serão pesquisados. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Múltiplos valores </td> 
   <td colname="col2"> <p>Verdadeiro ou falso. Determina se um único valor (uma linha correspondente) ou vários valores devem ser retornados (um para cada linha correspondente). </p> <p> <p>Observação:  Se <span class="wintitle"> Valores múltiplos</span> for definido como falso, você deve garantir que não haja várias correspondências. Quando ocorrem várias correspondências, não há garantia de qual correspondência será retornada. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colunas de Saída </td> 
   <td colname="col2"> <p>Um vetor de objetos de coluna (resultados) em que cada objeto é definido por nomes de coluna e campo. </p> <p> <span class="wintitle"> Nome </span> da coluna é o nome da expressão ou SQL da coluna da qual o valor de saída é obtido. <span class="wintitle"> Nome do </span> campo é o nome do campo usado para capturar a saída. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Identificador de tabela</span> </td> 
   <td colname="col2"> Uma expressão SQL que nomeia a tabela ou exibição da qual os dados devem ser carregados. Um identificador de tabela típico é do formulário SCHEMA.TABLE. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

* Os parâmetros Nome da Fonte de Dados, [!DNL Database User ID], [!DNL Database Password] e Identificador de Tabela são iguais aos parâmetros dos mesmos nomes descritos para fontes de dados ODBC. Consulte [Fontes de Dados ODBC](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

* Diferentemente das fontes de dados ODBC, as transformações [!DNL ODBCLookup] não exigem uma coluna ID crescente. Consulte [Fontes de Dados ODBC](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3). Isso ocorre porque o conteúdo da tabela de pesquisa não deve ser alterado de forma alguma enquanto o conjunto de dados está ativo. As alterações em uma tabela de pesquisa ou exibição não podem ser detectadas até que ocorra uma retransformação. Para obter informações sobre como reprocessar seus dados, consulte [Reprocessando e Retransformação](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

Suponha que você deseja converter registros DNS desatualizados para os registros atualizados. Ambos os conjuntos de registros são armazenados em um banco de dados SQL. Para executar essa tarefa, você referenciaria uma tabela de pesquisa gerada a partir do banco de dados e substituiria os registros DNS desatualizados.

Nossa transformação de exemplo pesquisa as entradas de log do campo s-dns e, se estiver localizada, a tabela de pesquisa VISUAL.LOOKUP é usada para comparar a entrada s-dns com as entradas na coluna [!DNL OLDDNS] da tabela. Se uma linha estiver localizada na tabela , o campo de saída s-dns receberá a entrada de registro DNS atualizada da coluna [!DNL NEWDNS] da linha identificada.

![](assets/cfg_TransformationType_ODBCLookup.png)
