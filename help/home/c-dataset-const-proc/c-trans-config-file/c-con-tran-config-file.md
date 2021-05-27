---
description: Informações importantes a serem consideradas ao editar o arquivo Transformation.cfg .
title: Considerações para o arquivo de configuração de transformação
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
exl-id: 7164ccb5-269c-4968-a3b4-1ff046a57f92
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 5%

---

# Considerações para o arquivo de configuração de transformação{#considerations-for-the-transformation-configuration-file}

Informações importantes a serem consideradas ao editar o arquivo Transformation.cfg .

* Alterar qualquer um dos parâmetros neste arquivo requer a retransformação dos dados.
* Se você reprocessar os dados, poderá verificar o parâmetro [!DNL Transformation Progress] no [!DNL Processing Legend] do Data Workbench.

   Para obter informações sobre como reprocessar seus dados ou o [!DNL Processing Legend,] consulte [Reprocessando e Retransformação](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL CrossRows]As  [!DNL ODBCLookup]transformações,  [!DNL Sessionize],  [!DNL AppendURI]  e funcionam somente quando definidas em um  [!DNL Transformation Dataset Configuration] arquivo. Para obter informações sobre essas transformações, consulte [Transformações de dados](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >O Adobe recomenda definir transformações para a fase de transformação da construção do conjunto de dados em um ou mais arquivos [!DNL Transformation Dataset Include]. Para obter informações, consulte [Arquivos de inclusão do conjunto de dados de transformação](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace).

* Você pode adicionar qualquer um dos parâmetros descritos acima ao arquivo [!DNL Transformation.cfg] abrindo e editando o arquivo no Bloco de notas. Quaisquer alterações feitas e salvas serão exibidas quando você reabrir o arquivo no Data Workbench. Ao adicionar um novo parâmetro, use a tecla Space (não a tecla Tab) para recuar dois (2) espaços à direita do nível de cabeçalho anterior.

   Todos os erros que ocorrem durante a fase de transformação do processo de construção do conjunto de dados para um perfil de conjunto de dados são mostrados no nó [!DNL Profiles] da interface [!DNL Detailed Status] no Data Workbench. Para obter informações sobre a interface [!DNL Detailed Status], consulte o *Guia do Usuário do Data Workbench*.
