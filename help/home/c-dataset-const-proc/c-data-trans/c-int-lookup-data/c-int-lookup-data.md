---
description: O Data Workbench fornece um conjunto de transformações que permite ao servidor do Data Workbench incorporar dados de pesquisa no conjunto de dados.
title: Integração de dados de pesquisa
uuid: 35fd48f7-c0c4-4a83-919d-c15902f27495
exl-id: 150d3aae-4431-488f-8f19-b522637ee935
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 2%

---

# Integração de dados de pesquisa{#integrating-lookup-data}

{{eol}}

O Data Workbench fornece um conjunto de transformações que permite ao servidor do Data Workbench incorporar dados de pesquisa no conjunto de dados.

Os dados de pesquisa são dados externos de bancos de dados corporativos ou arquivos de pesquisa que podem ser combinados com dados de evento para criar o conjunto de dados. Em geral, você usa dados de pesquisa para aumentar os dados do evento de suas fontes de log. Conceitualmente, você pode pensar em usar dados de pesquisa para preencher registros de dados de evento com colunas adicionais de informações.

Ao usar dados de pesquisa, você carrega os dados em uma tabela de pesquisa residente na memória. Uma coluna na tabela deve conter uma chave comum que também existe nos registros de dados do evento. Os dados na própria tabela de pesquisa podem ser carregados de um arquivo simples ou de uma fonte de dados ODBC. Os dados de pesquisa podem ser incorporados ao conjunto de dados durante a fase de processamento ou transformação do log do processo de construção do conjunto de dados.

Para incorporar dados de pesquisa, primeiro você deve gerar um arquivo de pesquisa ou ter as informações necessárias para acessar um banco de dados SQL, e em seguida definir uma ou mais das seguintes transformações nos arquivos de configuração do conjunto de dados para processamento e transformação de log.

**Para integrar dados de pesquisa ao conjunto de dados**

1. Gere o arquivo de pesquisa. Consulte [Preencher a tabela de pesquisa](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-pop-lookup-table.md#concept-dd761338731a40e0997c33dfdabdcdf8).
1. Defina um dos seguintes tipos de transformações no parâmetro Transformations no arquivo de configuração de conjunto de dados apropriado:

   * [!DNL Categorize]
   * [!DNL FlatFileLookup]
   * [!DNL ODBCLookup]

>[!NOTE]
>
>Observe que a variável [!DNL ODBCLookup] a transformação funciona somente quando definido no [!DNL Transformation.cfg] ou em um [!DNL Transformation Dataset Include] arquivo.
