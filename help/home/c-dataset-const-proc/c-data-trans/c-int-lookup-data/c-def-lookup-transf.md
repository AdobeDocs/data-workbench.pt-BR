---
description: Informações sobre as transformações que podem ser usadas para incorporar dados de pesquisa ao conjunto de dados.
solution: Analytics
title: Definindo Transformações de Pesquisa
topic: Data workbench
uuid: 4f7358b1-9e6a-4d03-b0c6-411e454fc11e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Definindo Transformações de Pesquisa{#defining-lookup-transformations}

Informações sobre as transformações que podem ser usadas para incorporar dados de pesquisa ao conjunto de dados.

Observe que nem todos os tipos podem ser usados durante ambas as fases do processo de construção do conjunto de dados.

* [Categorizar](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-8474376c14e54d14ae73749696ada468)
* [FlatFileLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-e09b2eeb96444a859b14f03cdaab31f2)
* [ODBCLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-4dcc3747e42e45c0a057e85f308a83cc)

## Categorizar {#section-8474376c14e54d14ae73749696ada468}

A [!DNL Categorize] transformação usa uma tabela de pesquisa de duas colunas composta de pares de string/valor de padrão. Durante essa transformação, o servidor da análise de big data lê cada registro de dados de evento e compara o conteúdo de um campo designado no registro a cada uma das strings de padrão listadas na primeira coluna da tabela de pesquisa. Se o campo designado corresponder a uma das strings de padrões, o servidor da análise de big data gravará o valor (encontrado na segunda coluna) associado à string de padrão em um campo de saída designado no registro.

As strings na primeira coluna da tabela de pesquisa podem, opcionalmente, começar com o caractere ^ e/ou terminar no caractere $ para forçar a correspondência no início e/ou no fim. Essa transformação não aceita expressões regulares para definir condições de correspondência na primeira coluna. Se o valor de entrada for um vetor de strings, cada string será executada pela transformação e os resultados serão anexados a um vetor de string de saída.

Uma [!DNL Categorize] transformação é geralmente mais fácil e rápida do que usar uma [!DNL Regular Expression] transformação para conseguir a mesma coisa.

>[!NOTE]
>
>O teste de subsequência de caracteres usado em [!DNL Categorize] diferencia maiúsculas e minúsculas, a menos que especificado de outra forma usando o [!DNL Case Sensitive] parâmetro.

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
   <td colname="col2"> Nome descritivo da transformação. Você pode digitar qualquer nome aqui. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Diferenciação de maiúsculas e minúsculas </td> 
   <td colname="col2"> Verdadeiro ou falso. Especifica se o teste de subsequência de caracteres faz distinção entre maiúsculas e minúsculas. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Notas sobre a transformação. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição </td> 
   <td colname="col2"> As condições em que essa transformação é aplicada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Padrão </td> 
   <td colname="col2"> O valor padrão a ser usado se o teste de condição for aprovado e nenhuma entrada no arquivo de categorização corresponder à entrada, ou o campo de entrada não for definido na entrada de log fornecida. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Delimitador </td> 
   <td colname="col2"> <p>String usada para separar as colunas no arquivo de pesquisa. Deve ter um único caractere de comprimento. </p> <p> Se você pressionar a tecla Ctrl e clicar com o botão direito do mouse no parâmetro Delimitador, um menu <span class="wintitle"> Inserir</span> será exibido. Esse menu contém uma lista de caracteres especiais que são usados com frequência como delimitadores. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Múltiplos valores </td> 
   <td colname="col2"> Verdadeiro ou falso. Se verdadeiro, quando várias linhas no arquivo correspondem à entrada, cada correspondência resulta em um valor anexado ao vetor de saída de sequências. Se false, somente a primeira linha correspondente no arquivo será usada na saída. No último caso, se a entrada for um vetor, a saída também será um vetor de comprimento equivalente. Se a entrada for uma string simples, a saída também será uma string simples. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Arquivo </td> 
   <td colname="col2"> Caminho e nome de arquivo do arquivo de categorização. Os caminhos relativos referem-se ao diretório de instalação do servidor de análise de big data. Normalmente, esse arquivo está localizado no diretório Pesquisas no diretório de instalação do servidor da análise de big data. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> O arquivo de categorização corresponde suas subsequências de caracteres em relação ao valor neste campo para identificar a linha correspondente no arquivo. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Saída </td> 
   <td colname="col2"> O nome do campo associado ao resultado. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**Considerações para categorização**

* As alterações nos arquivos de pesquisa em [!DNL Categorize] transformações definidas no [!DNL Transformation.cfg] arquivo ou em um [!DNL Transformation Dataset Include] arquivo exigem a retransformação do conjunto de dados. Os arquivos de pesquisa para [!DNL Categorize] transformações definidas no [!DNL Log Processing.cfg] arquivo ou em um [!DNL Log Processing Dataset Include] arquivo não estão sujeitos a essa limitação. Para obter informações sobre como reprocessar seus dados, consulte [Reprocessamento e Retransformação](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL Categorize] as transformações definidas no [!DNL Log Processing.cfg] arquivo ou em um [!DNL Log Processing Dataset Include] arquivo recarregam seus arquivos de pesquisa sempre que os arquivos de pesquisa forem alterados. As alterações não são aplicadas retroativamente, mas se aplicam a todos os dados de log lidos após a alteração.

Este exemplo ilustra o uso da [!DNL Categorize] transformação para integrar dados de pesquisa com dados de evento coletados do tráfego do site. Suponha que um site em particular tenha seções de negócios e que haja um requisito para ser capaz de analisar e fazer comparações com base no fluxo de tráfego e no valor gerado pelas diferentes seções. Você pode criar um arquivo de pesquisa que lista as subsequências usadas para identificar essas diferentes seções.

O arquivo de pesquisa [!DNL Lookups\custommap.txt] contém a seguinte tabela:

| /products/ | Produtos |
|---|---|
| ^/esportes/ | Esportes |
| ^/notícias/ | Notícias |
| ... | ... |

Este arquivo de categorização mapeia qualquer coisa que contenha a string &quot;/products/&quot; para o valor &quot;Products&quot;, qualquer coisa que comece com &quot;/Sports/&quot; para o valor &quot;Sports&quot; e qualquer coisa que comece com &quot;/news/&quot; para o valor &quot;News&quot;. A transformação de categorização a seguir usa o valor no campo cs-uri-stem como a string dentro da qual estamos procurando uma substring correspondente. O resultado da transformação é colocado no campo x-custommap.

![](assets/cfg_TransformationType_Categorize.png)

Supondo que o parâmetro Vários valores esteja definido como falso, o exemplo produziria os seguintes valores para x-custommap, dados os valores listados para cs-uri-stem.

| [!DNL cs-uri-stem] | [!DNL x-custommap] |
|---|---|
| [!DNL /sports/news/today.php] | Esportes |
| [!DNL /sports/products/buy.php] | Produtos |
| [!DNL /news/headlines.php] | Notícias |
| [!DNL /news/products/subscribe.php] | Produtos |

A saída se baseia na ordem das subsequências no arquivo de pesquisa. Por exemplo, o sistema cs-uri- [!DNL /sports/products/buy.php] retorna &quot;Produtos&quot;. Embora o sistema URI comece com &quot;/Sports/&quot;, a sequência &quot;/products/&quot; é listada antes de &quot;/Sports/&quot; no arquivo de pesquisa. Se o parâmetro Vários valores estivesse definido como true, haveria um valor adicional para x-custommap, já que o último exemplo corresponderia a duas linhas na tabela de pesquisa: Produtos e notícias.

## FlatFileLookup {#section-e09b2eeb96444a859b14f03cdaab31f2}

A [!DNL FlatFileLookup] transformação usa uma tabela de pesquisa composta de qualquer número de colunas e linhas (embora, lembre-se de que ela reside na memória). Durante esse tipo de transformação, o servidor da análise de big data lê cada registro de dados de evento e compara o conteúdo de um campo designado no registro a cada um dos valores em uma coluna designada da tabela de pesquisa. Se houver uma correspondência, o servidor da análise de big data grava um ou mais valores da linha correspondente na tabela de pesquisa para um ou mais campos de saída designados no registro de dados do evento.

A tabela de pesquisa usada durante essa transformação é preenchida a partir de um arquivo simples cujo local você especifica ao definir a transformação.

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
   <td colname="col2"> Nome descritivo da transformação. Você pode digitar qualquer nome aqui. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Notas sobre a transformação. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição </td> 
   <td colname="col2"> As condições em que essa transformação é aplicada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Padrão </td> 
   <td colname="col2"> O valor padrão a ser usado se a condição for atendida e se nenhuma entrada no arquivo de pesquisa corresponder à entrada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Delimitador </td> 
   <td colname="col2"> <p>String usada para separar as colunas no arquivo de pesquisa. Deve ter um único caractere de comprimento. </p> <p> Se você pressionar a tecla Ctrl e clicar com o botão direito do mouse no parâmetro Delimitador, um menu <span class="wintitle"> Inserir</span> será exibido. Esse menu contém uma lista de caracteres especiais que são usados com frequência como delimitadores. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Arquivo </td> 
   <td colname="col2"> Caminho e nome do arquivo de pesquisa. Os caminhos relativos referem-se ao diretório de instalação do servidor de análise de big data. Normalmente, esse arquivo está localizado no diretório Pesquisas dentro do diretório de instalação do servidor da análise de big data. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Linha do cabeçalho </td> 
   <td colname="col2"> Verdadeiro ou falso. Indica que a primeira linha da tabela é uma linha de cabeçalho a ser ignorada no processamento. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> <span class="wintitle"> Nome</span> da coluna é o nome da coluna usada para corresponder a entrada às linhas no arquivo. Se a Linha do cabeçalho for verdadeira, poderá ser o nome de uma coluna no arquivo de pesquisa. Caso contrário, esse deve ser o número da coluna com base em zero para corresponder. <span class="wintitle"> Nome</span> do campo é o nome do campo usado para localizar a linha no arquivo de pesquisa. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Múltiplos valores </td> 
   <td colname="col2"> <p>Verdadeiro ou falso. Determina se um único valor (uma linha correspondente) ou vários valores devem ser retornados (um para cada linha correspondente). </p> <p> <p>Observação:  Se <span class="wintitle"> Vários valores</span> estiver definido como falso, verifique se não há várias correspondências. Quando ocorrem várias correspondências, não há garantia de qual correspondência será retornada. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Saídas </td> 
   <td colname="col2"> <p>Um vetor de objetos de coluna (resultados) no qual cada objeto é definido por nomes de colunas e campos. </p> <p> <span class="wintitle"> Nome</span> da coluna é a coluna a partir da qual o valor de saída é obtido. Se a Linha <span class="wintitle"> do</span> cabeçalho for verdadeira, poderá ser o nome de uma coluna no arquivo de pesquisa. Caso contrário, esse deve ser o número da coluna com base em zero para corresponder. </p> <p> <span class="wintitle"> Nome</span> do campo é o nome do campo usado para capturar a saída. Observe que isso pode ser um vetor de resultados, um para cada linha identificada no caso em que o parâmetro Vários valores é verdadeiro. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**Considerações para[!DNL FlatFileLookup]**

* A correspondência do campo de entrada com o arquivo de pesquisa sempre faz distinção entre maiúsculas e minúsculas.
* As alterações nos arquivos de pesquisa em [!DNL FlatFileLookup] transformações definidas no [!DNL Transformation.cfg] arquivo ou nos [!DNL Transformation Dataset Include] arquivos exigem a retransformação do conjunto de dados. Os arquivos de pesquisa para [!DNL FlatFileLookup] transformações definidas no [!DNL Log Processing.cfg] arquivo ou nos [!DNL Log Processing Dataset Include] arquivos não estão sujeitos a essa limitação. Para obter informações sobre como reprocessar seus dados, consulte [Reprocessamento e Retransformação](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL FlatFileLookup] transformações no [!DNL Log Processing.cfg] arquivo ou nos [!DNL Log Processing Dataset Include] arquivos recarregam seus arquivos de pesquisa sempre que os arquivos de pesquisa são alterados. As alterações não são aplicadas retroativamente, mas se aplicam a todos os dados de log lidos após a alteração.

Este exemplo ilustra o uso da [!DNL FlatFileLookup] transformação para integrar dados de pesquisa com dados de evento coletados do tráfego do site. Suponha que você queira isolar os parceiros do site que estão encaminhando tráfego para o site e transformar suas IDs de parceiro em nomes mais amigáveis. Em seguida, você pode usar os nomes amigáveis para criar dimensões e visualizações estendidas que mapeiam mais claramente para o relacionamento comercial do que o relacionamento site a site usado para rotear o tráfego.

A transformação de exemplo pesquisa o campo cs(referrer-query) pelo par nome-valor da PartnerID e, se estiver localizado, o arquivo de pesquisa [!DNL Lookups\partners.txt] é usado para comparar o valor da PartnerID com os valores na [!DNL Partner] coluna da tabela. Se uma linha estiver localizada, o campo de saída x-partner-name recebe o nome da [!DNL PrintName] coluna da linha identificada.

![](assets/cfg_TransformationType_FlatFileLookup.png)

Se a tabela de pesquisa contiver as seguintes informações:

| ID | Parceiro | Iniciado | PrintName |
|---|---|---|---|
| 1 | P154 | 21 de ago de 1999 | Yahoo |
| 2 | P232 | 10 de julho de 2000 | Microsoft |
| 3 | P945 | 12 de jan de 2001 | Amazônia |

Os exemplos a seguir se transformariam da seguinte forma:

* Se cs(referrer)(PartnerID) retornasse P232, o campo x-partner-name receberia o valor &quot;Microsoft&quot;.
* Se cs(referrer)(PartnerID) retornasse P100, o campo x-partner-name receberia o valor &quot;No Partner&quot;.
* Se cs(referrer)(PartnerID) não retornasse nada, o campo x-partner-name receberia o valor &quot;No Partner&quot;, conforme especificado pelo parâmetro Default.

## ODBCLookup {#section-4dcc3747e42e45c0a057e85f308a83cc}

A [!DNL ODBCLookup] transformação opera como uma [!DNL FlatFileLookup] transformação. A única diferença é que a tabela de pesquisa usada durante essa transformação é preenchida a partir de um banco de dados ODBC e não de um arquivo simples.

>[!NOTE]
>
>[!DNL ODBCLookup] as transformações só podem ser executadas durante a fase de transformação do processo de construção do conjunto de dados. Quando possível, a Adobe recomenda que você use a [!DNL FlatFileLookup] transformação em vez da [!DNL ODBCLookup] transformação. [!DNL FlatFileLookup] as transformações são inerentemente mais confiáveis porque não dependem da disponibilidade de um sistema externo. Além disso, há menos risco de que a tabela de pesquisa seja modificada se estiver em um arquivo simples que você controla localmente.

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
   <td colname="col2"> Nome descritivo da transformação. Você pode digitar qualquer nome aqui. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Notas sobre a transformação. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição </td> 
   <td colname="col2"> As condições em que essa transformação é aplicada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome da fonte de dados </td> 
   <td colname="col2"> Um DSN, conforme fornecido por um administrador da máquina do servidor da análise de big data na qual o conjunto de dados é processado, que se refere ao banco de dados a partir do qual os dados devem ser carregados. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Senha do banco de dados </td> 
   <td colname="col2">A senha a ser usada na conexão com o banco de dados. Se uma senha tiver sido configurada para o DSN no Administrador <span class="wintitle"> da fonte de</span>dados, ela poderá ficar em branco. Qualquer senha fornecida aqui substitui a senha configurada para o DSN no Administrador <span class="wintitle"> da fonte de</span>dados. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de usuário do banco de dados </td> 
   <td colname="col2">A ID de usuário a ser usada ao conectar-se ao banco de dados. Se uma ID de usuário tiver sido configurada para o DSN no Administrador <span class="wintitle"> da fonte de</span>dados, isso pode ficar em branco. Qualquer ID de usuário fornecida aqui substitui a ID de usuário configurada para o DSN no Administrador <span class="wintitle"> da fonte de</span>dados. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Padrão </td> 
   <td colname="col2"> O valor padrão a ser usado se a condição for atendida e nenhuma entrada no arquivo de pesquisa corresponder à entrada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Coluna de entrada </td> 
   <td colname="col2"> <span class="wintitle"> Nome</span> da coluna é o nome da coluna ou a expressão SQL para os dados correspondentes à entrada. <span class="wintitle"> Nome</span> do campo é o nome do campo que contém os dados a serem pesquisados. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Múltiplos valores </td> 
   <td colname="col2"> <p>Verdadeiro ou falso. Determina se um único valor (uma linha correspondente) ou vários valores devem ser retornados (um para cada linha correspondente). </p> <p> <p>Observação:  Se <span class="wintitle"> Vários valores</span> estiver definido como falso, verifique se não há várias correspondências. Quando ocorrem várias correspondências, não há garantia de qual correspondência será retornada. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colunas de saída </td> 
   <td colname="col2"> <p>Um vetor de objetos de coluna (resultados) em que cada objeto é definido por nomes de colunas e campos. </p> <p> <span class="wintitle"> Nome</span> da coluna é o nome ou a expressão SQL da coluna na qual o valor de saída é obtido. <span class="wintitle"> Nome</span> do campo é o nome do campo usado para capturar a saída. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Identificador de tabela</span> </td> 
   <td colname="col2"> Uma expressão SQL que nomeia a tabela ou exibição a partir da qual os dados devem ser carregados. Um identificador de tabela típico tem o formato SCHEMA.TABLE. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

* Os parâmetros Nome da fonte de dados, [!DNL Database User ID], [!DNL Database Password]e Identificador de tabela são os mesmos parâmetros dos mesmos nomes descritos para fontes de dados ODBC. See [ODBC Data Sources](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

* Diferentemente das fontes de dados ODBC, [!DNL ODBCLookup] as transformações não exigem uma coluna de ID crescente. See [ODBC Data Sources](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3). Isso ocorre porque o conteúdo da tabela de pesquisa não deve ser alterado de forma alguma enquanto o conjunto de dados estiver ativo. As alterações em uma tabela de pesquisa ou exibição não podem ser detectadas até que ocorra a retransformação. Para obter informações sobre como reprocessar seus dados, consulte [Reprocessamento e Retransformação](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

Suponha que você deseja converter registros DNS desatualizados para os registros atualizados. Ambos os conjuntos de registros são armazenados em um banco de dados SQL. Para executar essa tarefa, você faria referência a uma tabela de pesquisa gerada a partir do banco de dados e substituiria os registros DNS desatualizados.

Nosso exemplo de transformação pesquisa as entradas de log do campo s-dns e, se estiver localizado, a tabela de pesquisa VISUAL.LOOKUP é usada para comparar a entrada s-dns com as entradas na [!DNL OLDDNS] coluna da tabela. Se uma linha estiver localizada na tabela, o campo de saída s-dns receberá a entrada de registro DNS atualizada da [!DNL NEWDNS] coluna da linha identificada.

![](assets/cfg_TransformationType_ODBCLookup.png)

