---
description: Durante o reprocessamento, o servidor do Data Workbench reconstrói seu conjunto de dados como você especificou nos arquivos de Processamento de log e Configuração de conjunto de dados de transformação.
title: Compreender como reprocessar e retransformar
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
exl-id: 12c69935-a981-492c-9124-71f6f06ff77b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 2%

---

# Compreender como reprocessar e retransformar{#understanding-reprocessing-and-retransformation}

{{eol}}

Durante o reprocessamento, o servidor do Data Workbench reconstrói seu conjunto de dados como você especificou nos arquivos de Processamento de log e Configuração de conjunto de dados de transformação.

Para isso, o servidor do Data Workbench (InsightServer64.exe) deve concluir a fase de processamento de log e a fase de transformação da construção do conjunto de dados. Quando o processamento de log é concluído, ele aciona a transformação para ocorrer automaticamente, mas a transformação também pode ocorrer independentemente do processamento de log.

Durante a fase de processamento de log, os usuários do Data Workbench não têm acesso aos dados no conjunto de dados. Durante a fase de transformação, os usuários do Data Workbench têm acesso a dados atualizados, mas os dados são coletados em vez de concluídos. A análise de dados pode continuar durante a transformação, mas as consultas serão concluídas somente assim que a transformação estiver ocorrendo.

## Reprocessando {#section-92f1e46bf1534b3dba39e9493190b8ab}

Cada vez que você conclui uma das seguintes tarefas, o processamento de log e, portanto, a transformação, ocorre automaticamente para reconstruir seu conjunto de dados conforme você especificou nos arquivos de configuração do conjunto de dados:

* Adicione uma nova fonte de dados.
* Adicionar um novo servidor do Data Workbench ao cluster na [!DNL Profile.cfg] arquivo.
* Altere o [!DNL Cluster.cfg] arquivo.
* Altere o [!DNL Log Processing.cfg] ou um [!DNL Log Processing Dataset Include] , incluindo, mas não limitado a:

   * Adicionar um novo parâmetro
   * Alterar uma transformação
   * Alterar os parâmetros Hora de Início ou Hora de Término

* Atualize seu [!DNL Insight Server.exe] arquivo.

Você também pode iniciar o reprocessamento a qualquer momento inserindo qualquer caractere ou combinação de caracteres no parâmetro Reprocessar da variável [!DNL Log Processing.cfg] e salvando o arquivo.

>[!NOTE]
>
>Para que o reprocessamento ocorra, o parâmetro Pause na função [!DNL Log Processing Mode.cfg] O arquivo deve ser definido como false. O valor padrão deste parâmetro é falso, portanto, alterar o parâmetro pode não ser necessário. Para obter mais informações sobre [!DNL Log Processing Mode.cfg], consulte [Arquivos de configuração adicionais](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md).

## Retransformação {#section-02446744549940ada8eba0573ec5575f}

Sempre que você alterar qualquer informação na [!DNL Transformation.cfg] ou em um [!DNL Transformation Dataset Include] , como alterar uma transformação ou definir uma nova dimensão, a transformação ocorre automaticamente.

Cada vez que você altera os arquivos de pesquisa referenciados no [!DNL Transformation.cfg] ou em um [!DNL Transformation Dataset Include] (incluindo arquivos de pesquisa para [!DNL Categorize], [!DNL FlatFileLookup]e [!DNL ODBCLookup] transformações), você deve iniciar a transformação inserindo qualquer caractere ou combinação de caracteres no parâmetro Reprocess da variável [!DNL Transformation.cfg] e salvando o arquivo.
