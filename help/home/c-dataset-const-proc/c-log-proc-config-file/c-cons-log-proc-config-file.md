---
description: Informações conceituais a serem consideradas ao editar o arquivo Log Processing.cfg .
title: Considerações para o arquivo de configuração de processamento de log
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
exl-id: 278a4a10-d382-4d9f-b3f4-bcc4783eb50c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 4%

---

# Considerações para o arquivo de configuração de processamento de log{#considerations-for-the-log-processing-configuration-file}

{{eol}}

Informações conceituais a serem consideradas ao editar o arquivo Log Processing.cfg .

* Os arquivos de dados não devem ser movidos entre diretórios depois que as fontes de um conjunto de dados tiverem sido definidas. Os únicos arquivos adicionais que um diretório deve receber são os recém-criados que resultam do servidor do Data Workbench receber dados do(s) Sensor(es).
* Alterar qualquer um dos parâmetros neste arquivo requer o reprocessamento de todos os dados. O parâmetro Pause na [!DNL Log Processing Mode.cfg] O arquivo deve ser definido como false para que o reprocessamento ocorra. (Observe que o valor padrão deste parâmetro é falso, portanto, alterar o parâmetro pode não ser necessário.) Para obter informações sobre o [!DNL Log Processing Mode.cfg] arquivo, consulte [Arquivos de configuração adicionais](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* Se você reprocessar os dados, poderá verificar o parâmetro Andamento do processamento de log no Data Workbench [!DNL Processing Legend].

   Para obter informações sobre como reprocessar seus dados, consulte [Reprocessamento e retransformação](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md). Consulte [Legenda de processamento](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828).

* O [!DNL Log Processing.cfg] O arquivo pode ser compartilhado por vários perfis do conjunto de dados. As transformações definidas no [!DNL Log Processing.cfg] são aplicados a todos os perfis do conjunto de dados que compartilham esse arquivo de configuração.

   >[!NOTE]
   >
   >O Adobe recomenda definir transformações para o processamento de log em um ou mais processos de log [!DNL dataset include] arquivos. Para obter mais informações, consulte [Arquivos de dados do conjunto de dados de processamento de log](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

* Você pode adicionar qualquer um dos parâmetros descritos acima à [!DNL Log Processing.cfg] abrindo e editando o arquivo no Bloco de notas. Quaisquer alterações feitas e salvas serão exibidas quando você reabrir o arquivo no Data Workbench. Ao adicionar um novo parâmetro, use a tecla Space (não a tecla Tab) para recuar dois (2) espaços à direita do nível de cabeçalho anterior.

   Todos os erros que ocorrem durante a fase de processamento de log do processo de construção do conjunto de dados para um perfil de conjunto de dados são mostrados na [!DNL Profiles] nó do [!DNL Detailed Status] na análise de big data. Para obter informações sobre o [!DNL Detailed Status] consulte a *Guia do usuário do Data Workbench*.
