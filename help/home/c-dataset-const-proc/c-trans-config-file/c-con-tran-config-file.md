---
description: Informações importantes a serem consideradas ao editar o arquivo Transformation.cfg .
title: Considerações para o arquivo de configuração de transformação
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
exl-id: 7164ccb5-269c-4968-a3b4-1ff046a57f92
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 5%

---

# Considerações para o arquivo de configuração de transformação{#considerations-for-the-transformation-configuration-file}

{{eol}}

Informações importantes a serem consideradas ao editar o arquivo Transformation.cfg .

* Alterar qualquer um dos parâmetros neste arquivo requer a retransformação dos dados.
* Se você reprocessar os dados, poderá verificar a variável [!DNL Transformation Progress] no parâmetro do Data Workbench [!DNL Processing Legend].

   Para obter informações sobre como reprocessar seus dados ou o [!DNL Processing Legend,] see [Reprocessamento e retransformação](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]e [!DNL AppendURI] as transformações funcionam somente quando definidas em um [!DNL Transformation Dataset Configuration] arquivo. Para obter informações sobre essas transformações, consulte [Transformações de dados](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >O Adobe recomenda definir transformações para a fase de transformação da construção do conjunto de dados em um ou mais [!DNL Transformation Dataset Include] arquivos. Para obter mais informações, consulte [Arquivos de inclusão do conjunto de dados de transformação](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace).

* Você pode adicionar qualquer um dos parâmetros descritos acima à [!DNL Transformation.cfg] abrindo e editando o arquivo no Bloco de notas. Quaisquer alterações feitas e salvas serão exibidas quando você reabrir o arquivo no Data Workbench. Ao adicionar um novo parâmetro, use a tecla Space (não a tecla Tab) para recuar dois (2) espaços à direita do nível de cabeçalho anterior.

   Todos os erros que ocorrem durante a fase de transformação do processo de construção do conjunto de dados para um perfil de conjunto de dados são mostrados na [!DNL Profiles] nó do [!DNL Detailed Status] na análise de big data. Para obter informações sobre o [!DNL Detailed Status] consulte a *Guia do usuário do Data Workbench*.
