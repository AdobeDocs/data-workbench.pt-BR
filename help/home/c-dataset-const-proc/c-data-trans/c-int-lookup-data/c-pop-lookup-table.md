---
description: Se você usar as transformações Categorize ou FlatFileLookup, a tabela de pesquisa será carregada na memória e preenchida a partir de um arquivo simples cujo local você especificar ao definir a transformação.
solution: Analytics
title: Preenchendo a tabela de pesquisa
topic: Data workbench
uuid: a11f3902-8853-4d22-bbfd-b2a3d143cb7b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Preenchendo a tabela de pesquisa{#populating-the-lookup-table}

Se você usar as transformações Categorize ou FlatFileLookup, a tabela de pesquisa será carregada na memória e preenchida a partir de um arquivo simples cujo local você especificar ao definir a transformação.

O arquivo simples especificado deve atender aos seguintes requisitos:

* Cada linha no arquivo deve representar uma linha na tabela de pesquisa.
* As colunas no arquivo devem ser separadas por um delimitador ASCII. Você pode usar qualquer caractere que não seja um caractere final de linha e não apareça em qualquer lugar dentro dos próprios dados do evento. Ao definir a transformação, especifique qual caractere foi usado para delimitar as colunas no arquivo simples.

Se você usar uma [!DNL ODBCLookup] transformação, a tabela de pesquisa será carregada na memória e preenchida a partir de uma tabela ou exibição em um [!DNL ODBC] banco de dados especificado. Ao definir a transformação, você também deve especificar a fonte de dados, o nome de usuário e a senha que o servidor da análise de big data deve usar para estabelecer uma conexão com o banco de dados.

>[!NOTE]
>
>As tabelas de pesquisa são carregadas quando o servidor da análise de big data começa a construir o conjunto de dados. Uma vez estabelecidos, os arquivos de pesquisa não devem ser alterados. Se você alterar o arquivo simples ou a tabela [!DNL ODBC] usada para a fase de transformação, será necessário retransformar o conjunto de dados inteiro. Se você alterar um arquivo simples usado durante a fase de processamento do log, os novos dados de pesquisa serão aplicados a todos os novos registros que inserirem o conjunto de dados, mas as alterações não serão aplicadas retroativamente.

