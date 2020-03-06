---
description: Durante o reprocessamento, o servidor da análise de big data reconstrói seu conjunto de dados como você especificou nos arquivos de Configuração de Processamento de Log e Transformação de Conjunto de Dados.
solution: Analytics
title: Noções básicas sobre reprocessamento e retransformação
topic: Data workbench
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Noções básicas sobre reprocessamento e retransformação{#understanding-reprocessing-and-retransformation}

Durante o reprocessamento, o servidor da análise de big data reconstrói seu conjunto de dados como você especificou nos arquivos de Configuração de Processamento de Log e Transformação de Conjunto de Dados.

Para isso, o servidor da análise de big data (InsightServer64.exe) deve concluir a fase de processamento de log e a fase de transformação da construção do conjunto de dados. Quando o processamento de log é concluído, ele aciona a transformação para ocorrer automaticamente, mas a transformação também pode ocorrer independentemente do processamento de log.

Durante a fase de processamento de log, os usuários da análise de big data não têm acesso aos dados no conjunto de dados. Durante a fase de transformação, os usuários da análise de big data têm acesso a dados atualizados, mas os dados são coletados em vez de concluídos. A análise de dados pode continuar durante a transformação, mas as consultas serão concluídas apenas tão rapidamente quanto a transformação ocorrer.

## Reprocessamento {#section-92f1e46bf1534b3dba39e9493190b8ab}

Cada vez que você conclui uma das seguintes tarefas, o processamento de log e, portanto, a transformação, ocorre automaticamente para reconstruir seu conjunto de dados conforme especificado nos arquivos de configuração do conjunto de dados:

* Adicione uma nova fonte de dados.
* Adicione um novo servidor de análise de big data ao cluster no [!DNL Profile.cfg] arquivo.
* Altere o [!DNL Cluster.cfg] arquivo.
* Altere o [!DNL Log Processing.cfg] arquivo ou um [!DNL Log Processing Dataset Include] arquivo, incluindo, mas não limitado, o seguinte:

   * Adicionar um novo parâmetro
   * Alterar uma transformação
   * Alterar os parâmetros Hora de início ou Hora de término

* Atualize seu [!DNL Insight Server.exe] arquivo.

Você também pode iniciar o reprocessamento a qualquer momento inserindo qualquer caractere ou combinação de caracteres no parâmetro Reprocessar do arquivo e salvando o arquivo. [!DNL Log Processing.cfg]

>[!NOTE]
>
>Para que o reprocessamento ocorra, o parâmetro Pausar no [!DNL Log Processing Mode.cfg] arquivo deve ser definido como falso. O valor padrão desse parâmetro é falso, portanto, alterar o parâmetro pode não ser necessário. Para obter mais informações sobre [!DNL Log Processing Mode.cfg], consulte Arquivos [de configuração](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md)adicionais.

## Retransformação {#section-02446744549940ada8eba0573ec5575f}

Cada vez que você altera qualquer informação no [!DNL Transformation.cfg] arquivo ou em um [!DNL Transformation Dataset Include] arquivo, como alterar uma transformação ou definir uma nova dimensão, a transformação ocorre automaticamente.

Sempre que você alterar arquivos de pesquisa referenciados no [!DNL Transformation.cfg] arquivo ou em um [!DNL Transformation Dataset Include] arquivo (incluindo arquivos de pesquisa para [!DNL Categorize], [!DNL FlatFileLookup]e [!DNL ODBCLookup] transformações), deve iniciar a transformação inserindo qualquer caractere ou combinação de caracteres no parâmetro Reprocessar do [!DNL Transformation.cfg] arquivo e salvando o arquivo.
