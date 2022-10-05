---
description: Etapas para criar um novo arquivo de inclusão do conjunto de dados.
title: Criar novos arquivos de inclusão do conjunto de dados
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
exl-id: 8a7b343d-b695-41aa-b465-8c5cd68d6ef7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 3%

---

# Criar novos arquivos de inclusão do conjunto de dados{#creating-new-dataset-include-files}

{{eol}}

Etapas para criar um novo arquivo de inclusão do conjunto de dados.

Você deve criar um novo arquivo de inclusão do conjunto de dados para executar qualquer uma das seguintes tarefas de configuração do conjunto de dados:

* Especificação de novos campos de dados a serem passados do processamento de log para a transformação.
* Definindo transformações que façam o seguinte:

   * Atualize os campos de log existentes.
   * Produza novos campos que devem ser passados do processamento de log para a transformação ou que são usados para definir dimensões estendidas.

      Para obter informações sobre os tipos de transformação disponíveis, consulte [Transformações de dados](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

      >[!NOTE]
      >
      >Se você estiver definindo transformações em um novo conjunto de dados, certifique-se de manter a ordem das entradas e saídas em mente. Para obter informações sobre a ordem de transformações, consulte [Convenções para a construção de transformações](../../../../home/c-dataset-const-proc/c-data-trans/c-con-transf.md#concept-01998eebb7e347c58255fb442f2613b6).

* Criação de dimensões estendidas. Para obter informações sobre os tipos de dimensão disponíveis, consulte [Dimension estendidas](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

1. Ao trabalhar no perfil do conjunto de dados, abra o [!DNL Profile Manager] e clique em **[!UICONTROL Dataset]** para exibir os arquivos de inclusão do conjunto de dados existente.

   * Para exibir o [!DNL Log Processing Dataset Include] arquivos, clique em **[!UICONTROL Log Processing]**.

   * Para exibir o [!DNL Transformation Dataset Include] arquivos, clique em **[!UICONTROL Transformation]**.

1. Crie um novo [!DNL Log Processing] ou [!DNL Transformation Dataset Include] arquivos executando uma das seguintes etapas:

   * No [!DNL User] para o diretório Log Processing, clique em **[!UICONTROL Create]** > **[!UICONTROL New Log Processing]**. Um arquivo chamado [!DNL New Log Processing.cfg] é exibido no diretório .

   * No [!DNL User] para o diretório Transformation , clique em **[!UICONTROL Create]** > **[!UICONTROL New Transformation]**. Um arquivo chamado [!DNL New Transformation.cfg] é exibido no diretório .

1. Renomeie o novo arquivo clicando com o botão direito do mouse em sua marca de seleção no [!DNL User] e digitar o novo nome no parâmetro Arquivo .

   ![Informações da etapa](assets/vis_ProfileManager_RenameFile.png)

1. Clique com o botão direito do mouse na marca de seleção do arquivo renomeado e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. A janela de configuração é exibida.
1. Edite os parâmetros no arquivo de configuração, conforme apropriado. Consulte [Arquivos de dados do conjunto de dados de processamento de log](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) ou [Arquivos de inclusão do conjunto de dados de transformação](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) para obter descrições dos parâmetros disponíveis.
1. Para salvar as alterações, clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
1. Para que as alterações feitas localmente entrem em vigor, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo no [!DNL User] e, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, em que o nome do perfil é o nome do perfil do conjunto de dados ou o perfil herdado ao qual o arquivo de inclusão do conjunto de dados pertence. O reprocessamento ou a retransformação dos dados começam após a sincronização do perfil do conjunto de dados.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pelo Adobe, pois as alterações são substituídas ao instalar atualizações nesses perfis.

Para editar um arquivo de inclusão do conjunto de dados criado, consulte [Editar arquivos de inclusão existentes do conjunto de dados](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).
