---
description: Etapas para criar um novo conjunto de dados inclui o arquivo.
solution: Analytics
title: Criando Novo Conjunto de Dados Incluir Arquivos
topic: Data workbench
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Criando Novo Conjunto de Dados Incluir Arquivos{#creating-new-dataset-include-files}

Etapas para criar um novo conjunto de dados inclui o arquivo.

Você deve criar um novo arquivo de inclusão de conjunto de dados para executar qualquer uma das seguintes tarefas de configuração de conjunto de dados:

* Especificação de novos campos de dados a serem passados do processamento de log para a transformação.
* Definindo transformações que executam um dos seguintes procedimentos:

   * Atualizar campos de log existentes.
   * Produza novos campos que devem ser passados do processamento de log para a transformação ou que são usados para definir dimensões estendidas.

      Para obter informações sobre os tipos de transformação disponíveis, consulte Transformações [de dados](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

      >[!NOTE]
      >
      >Se você estiver definindo transformações em um novo conjunto de dados incluindo um arquivo, lembre-se de manter em mente a ordem das entradas e saídas. Para obter informações sobre a ordem de transformações, consulte [Convenções para a construção de transformações](../../../../home/c-dataset-const-proc/c-data-trans/c-con-transf.md#concept-01998eebb7e347c58255fb442f2613b6).

* Criação de dimensões estendidas. Para obter informações sobre os tipos de dimensão disponíveis, consulte Dimensões [](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)estendidas.

1. Ao trabalhar em seu perfil de conjunto de dados, abra o [!DNL Profile Manager] e clique para exibir **[!UICONTROL Dataset]** o conjunto de dados existente que inclui arquivos.

   * Para exibir os [!DNL Log Processing Dataset Include] arquivos, clique em **[!UICONTROL Log Processing]**.

   * Para exibir os [!DNL Transformation Dataset Include] arquivos, clique em **[!UICONTROL Transformation]**.

1. Crie um novo [!DNL Log Processing] ou [!DNL Transformation Dataset Include] arquivos executando uma das seguintes etapas:

   * Na [!DNL User] coluna do diretório Log Processing, clique em **[!UICONTROL Create]** > **[!UICONTROL New Log Processing]**. Um arquivo nomeado [!DNL New Log Processing.cfg] é exibido no diretório.

   * Na [!DNL User] coluna do diretório Transformation (Transformação), clique em **[!UICONTROL Create]** > **[!UICONTROL New Transformation]**. Um arquivo nomeado [!DNL New Transformation.cfg] é exibido no diretório.

1. Renomeie o novo arquivo clicando com o botão direito do mouse em sua marca de seleção na [!DNL User] coluna e digitando o novo nome no parâmetro Arquivo.

   ![Informações da etapa](assets/vis_ProfileManager_RenameFile.png)

1. Clique com o botão direito do mouse na marca de seleção do arquivo renomeado e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. A janela de configuração é exibida.
1. Edite os parâmetros no arquivo de configuração, conforme apropriado. Consulte Conjunto de dados de processamento de [log Incluir arquivos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) ou Conjunto de dados de [transformação Incluir arquivos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) para obter descrições dos parâmetros disponíveis.
1. Para salvar as alterações, clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
1. Para que as alterações feitas localmente entrem em vigor, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] coluna, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, onde nome do perfil é o nome do perfil do conjunto de dados ou o perfil herdado ao qual o conjunto de dados inclui o arquivo. O reprocessamento ou a retransformação dos dados começam após a sincronização do perfil do conjunto de dados.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pela Adobe, pois suas alterações são substituídas quando você instala atualizações nesses perfis.

Para editar um conjunto de dados, inclua o arquivo que você criou, consulte [Edição de conjuntos de dados existentes Incluir arquivos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).
