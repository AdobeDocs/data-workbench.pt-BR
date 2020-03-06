---
description: Informações importantes a serem consideradas ao editar o arquivo Transformation.cfg.
solution: Analytics
title: Considerações para o arquivo de configuração de transformação
topic: Data workbench
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Considerações para o arquivo de configuração de transformação{#considerations-for-the-transformation-configuration-file}

Informações importantes a serem consideradas ao editar o arquivo Transformation.cfg.

* A alteração de qualquer um dos parâmetros neste arquivo requer a retransformação dos dados.
* Se os dados forem reprocessados, você poderá verificar o [!DNL Transformation Progress] parâmetro em análise de big data [!DNL Processing Legend].

   Para obter informações sobre como reprocessar seus dados ou o [!DNL Processing Legend,] consulte [Reprocessamento e Retransformação](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]e [!DNL AppendURI] transformações funcionam somente quando definidas em um [!DNL Transformation Dataset Configuration] arquivo. Para obter informações sobre essas transformações, consulte Transformações [de dados](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >A Adobe recomenda definir transformações para a fase de transformação da construção do conjunto de dados em um ou mais [!DNL Transformation Dataset Include] arquivos. Para obter informações, consulte [Transformation Dataset Include Files (Incluir arquivos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace)de conjuntos de dados de transformação).

* Você pode adicionar qualquer um dos parâmetros descritos acima ao [!DNL Transformation.cfg] arquivo abrindo e editando o arquivo no Bloco de notas. Quaisquer alterações feitas e salvas serão exibidas quando o arquivo for reaberto na análise de big data. Ao adicionar um novo parâmetro, use a tecla Space (não a tecla Tab) para recuar dois (2) espaços à direita do nível de cabeçalho anterior.

   Todos os erros que ocorrem durante a fase de transformação do processo de construção do conjunto de dados para um perfil de conjunto de dados são mostrados no [!DNL Profiles] [!DNL Detailed Status] nó da interface na análise de big data. Para obter informações sobre a [!DNL Detailed Status] interface, consulte o Guia *do Usuário do* Análise de big data.

