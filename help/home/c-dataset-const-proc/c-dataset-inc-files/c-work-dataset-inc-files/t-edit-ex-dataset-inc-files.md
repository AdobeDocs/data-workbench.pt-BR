---
description: As etapas para editar um conjunto de dados existente incluem arquivos.
solution: Analytics
title: Edição de conjuntos de dados existentes Incluir arquivos
topic: Data workbench
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Edição de conjuntos de dados existentes Incluir arquivos{#editing-existing-dataset-include-files}

As etapas para editar um conjunto de dados existente incluem arquivos.

Você abre um arquivo de inclusão de conjunto de dados existente usando o arquivo [!DNL Profile Manager] na análise de big data.

Para obter informações sobre como abrir e trabalhar com o [!DNL Profile Manager], consulte o Guia *do usuário da Análise de* big data.

1. Ao trabalhar no perfil do conjunto de dados, abra o [!DNL Profile Manager] e clique **[!UICONTROL Dataset]** para mostrar o conteúdo do diretório.

   * Para abrir um [!DNL Log Processing Dataset Include] arquivo, clique **[!UICONTROL Log Processing]** para mostrar o conteúdo do diretório.

   * Para abrir um [!DNL Transformation Dataset Include] arquivo, clique **[!UICONTROL Transformation]** para mostrar o conteúdo do diretório.

1. Clique com o botão direito do mouse na marca de seleção ao lado do arquivo de inclusão do conjunto de dados desejado e clique em **[!UICONTROL Make Local]**. Uma marca de seleção para este arquivo é exibida na [!DNL User] coluna.
1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. A janela de configuração é exibida.

   Você também pode abrir um arquivo de inclusão de conjunto de dados de um [!DNL Transformation Dependency Maps]. Para obter informações sobre [!DNL Transformation Dependency Maps], consulte [Reprocessamento e Retransformação](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

1. Edite os parâmetros no arquivo de configuração, conforme apropriado. Consulte Conjunto de dados de processamento de [log Incluir arquivos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) ou Conjunto de dados de [transformação Incluir arquivos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) para obter descrições dos parâmetros.

   Ao editar um conjunto de dados, inclua um arquivo em uma janela de análise de big data, você pode usar teclas de atalho para recursos básicos de edição, incluindo recortar (Ctrl+x ), copiar (Ctrl+c), colar (Ctrl+v ), desfazer (Ctrl+z ), refazer (Ctrl+Shift+z ), selecionar seção (clique+arrastar) e selecionar tudo (Ctrl+a ). Além disso, você pode usar os atalhos para copiar e colar o texto de um arquivo de configuração ( [!DNL .cfg]) para outro.

1. Para salvar as alterações, clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
1. Para que as alterações feitas localmente entrem em vigor, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] coluna, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, onde nome do perfil é o nome do perfil do conjunto de dados ou o perfil herdado ao qual o conjunto de dados inclui o arquivo. O reprocessamento ou a retransformação dos dados começam após a sincronização do perfil do conjunto de dados.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pela Adobe, pois suas alterações são substituídas quando você instala atualizações nesses perfis.

