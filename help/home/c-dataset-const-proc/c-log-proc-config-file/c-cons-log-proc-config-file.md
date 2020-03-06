---
description: Informações conceituais a serem consideradas ao editar o arquivo Log Processing.cfg.
solution: Analytics
title: Considerações para o arquivo de configuração de processamento de log
topic: Data workbench
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Considerações para o arquivo de configuração de processamento de log{#considerations-for-the-log-processing-configuration-file}

Informações conceituais a serem consideradas ao editar o arquivo Log Processing.cfg.

* Os arquivos de dados não devem ser movidos entre diretórios depois que as fontes de um conjunto de dados forem definidas. Os únicos arquivos adicionais que um diretório deve receber são os recém-criados que resultam do servidor de análise de big data receber dados do(s) sensor(es).
* A alteração de qualquer um dos parâmetros neste arquivo requer o reprocessamento de todos os dados. O parâmetro Pause no [!DNL Log Processing Mode.cfg] arquivo deve ser definido como false para que o reprocessamento ocorra. (Observe que o valor padrão desse parâmetro é falso, portanto, alterar o parâmetro pode não ser necessário.) Para obter informações sobre o [!DNL Log Processing Mode.cfg] arquivo, consulte Arquivos [de configuração](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)adicionais.

* Se você reprocessar os dados, poderá verificar o parâmetro Andamento do Processamento de Log em análise de big data [!DNL Processing Legend].

   Para obter informações sobre como reprocessar seus dados, consulte [Reprocessamento e Retransformação](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md). Consulte [Processando legenda](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828).

* O [!DNL Log Processing.cfg] arquivo pode ser compartilhado por vários perfis de conjunto de dados. As transformações definidas no [!DNL Log Processing.cfg] arquivo são aplicadas a todos os perfis de conjunto de dados que compartilham esse arquivo de configuração.

   >[!NOTE]
   >
   >A Adobe recomenda definir transformações para o processamento de log em um ou mais [!DNL dataset include] arquivos de processamento de log. Para obter informações, consulte [Log Processing Dataset Include Files (Incluir arquivos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)).

* Você pode adicionar qualquer um dos parâmetros descritos acima ao [!DNL Log Processing.cfg] arquivo abrindo e editando o arquivo no Bloco de notas. Quaisquer alterações feitas e salvas serão exibidas quando o arquivo for reaberto na análise de big data. Ao adicionar um novo parâmetro, use a tecla Space (não a tecla Tab) para recuar dois (2) espaços à direita do nível de cabeçalho anterior.

   Todos os erros que ocorrem durante a fase de processamento de log do processo de construção do conjunto de dados para um perfil de conjunto de dados são mostrados no [!DNL Profiles] [!DNL Detailed Status] nó da interface no análise de big data. Para obter informações sobre a [!DNL Detailed Status] interface, consulte o Guia *do Usuário do* Análise de big data.

