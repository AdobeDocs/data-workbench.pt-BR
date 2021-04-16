---
description: Se você usar as transformações Categorize ou FlatFileLookup , a tabela de pesquisa será carregada na memória e preenchida em um arquivo simples cujo local você especifica ao definir a transformação.
title: Preencher a tabela de pesquisa
uuid: a11f3902-8853-4d22-bbfd-b2a3d143cb7b
exl-id: e83d9feb-44fe-4fa1-b559-e1f5606637b5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 2%

---

# Preencher a tabela de pesquisa{#populating-the-lookup-table}

Se você usar as transformações Categorize ou FlatFileLookup , a tabela de pesquisa será carregada na memória e preenchida em um arquivo simples cujo local você especifica ao definir a transformação.

O arquivo simples especificado deve atender aos seguintes requisitos:

* Cada linha no arquivo deve representar uma linha na tabela de pesquisa.
* As colunas no arquivo devem ser separadas por um delimitador ASCII. Você pode usar qualquer caractere que não seja um caractere final de linha e não apareça em nenhum lugar dentro dos próprios dados do evento. Ao definir a transformação, você especifica qual caractere foi usado para delimitar as colunas no arquivo simples.

Se você usar uma transformação [!DNL ODBCLookup], a tabela de pesquisa será carregada na memória e preenchida a partir de uma tabela ou exibição em um banco de dados [!DNL ODBC] especificado. Ao definir a transformação, você também deve especificar a fonte de dados, o nome de usuário e a senha que o servidor do Data Workbench deve usar para estabelecer uma conexão com o banco de dados.

>[!NOTE]
>
>As tabelas de pesquisa são carregadas quando o servidor do Data Workbench começa inicialmente a construir o conjunto de dados. Depois de estabelecido, os arquivos de pesquisa não devem ser alterados. Se você alterar o arquivo simples ou a tabela [!DNL ODBC] usada para a fase de transformação, será necessário retransformar todo o conjunto de dados. Se você alterar um arquivo simples usado durante a fase de processamento de log, os novos dados de pesquisa serão aplicados a todos os novos registros que inserirem o conjunto de dados, mas as alterações não serão aplicadas retroativamente.
