---
description: A análise de big data fornece um conjunto de transformações que permite ao servidor da análise de big data incorporar dados de pesquisa ao conjunto de dados.
solution: Analytics
title: Integração de dados de pesquisa
topic: Data workbench
uuid: 35fd48f7-c0c4-4a83-919d-c15902f27495
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Integração de dados de pesquisa{#integrating-lookup-data}

A análise de big data fornece um conjunto de transformações que permite ao servidor da análise de big data incorporar dados de pesquisa ao conjunto de dados.

Os dados de pesquisa são dados externos de bancos de dados corporativos ou arquivos de pesquisa que podem ser combinados com dados de eventos para criar o conjunto de dados. Em geral, você usa dados de pesquisa para aumentar os dados de eventos das fontes de log. Conceitualmente, você pode pensar em usar dados de pesquisa para preencher registros de dados de eventos com colunas adicionais de informações.

Quando você usa dados de pesquisa, carrega os dados em uma tabela de pesquisa residente na memória. Uma coluna na tabela deve conter uma chave comum que também existe nos registros de dados do evento. Os dados na própria tabela de pesquisa podem ser carregados de um arquivo simples ou de uma fonte de dados ODBC. Os dados de pesquisa podem ser incorporados ao conjunto de dados durante a fase de processamento ou transformação do log do processo de construção do conjunto de dados.

Para incorporar dados de pesquisa, você deve primeiro gerar um arquivo de pesquisa ou ter as informações necessárias para acessar um banco de dados SQL, em seguida, definir uma ou mais das seguintes transformações nos arquivos de configuração do conjunto de dados para processamento e transformação de log.

**Para integrar dados de pesquisa ao conjunto de dados**

1. Gere o arquivo de pesquisa. Consulte [Preenchendo a tabela](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-pop-lookup-table.md#concept-dd761338731a40e0997c33dfdabdcdf8)de pesquisa.
1. Defina um dos seguintes tipos de transformações no parâmetro Transformações no arquivo de configuração de conjunto de dados apropriado:

   * [!DNL Categorize]
   * [!DNL FlatFileLookup]
   * [!DNL ODBCLookup]

>[!NOTE]
>
>Observe que a [!DNL ODBCLookup] transformação funciona somente quando definida no [!DNL Transformation.cfg] arquivo ou em um [!DNL Transformation Dataset Include] arquivo.

