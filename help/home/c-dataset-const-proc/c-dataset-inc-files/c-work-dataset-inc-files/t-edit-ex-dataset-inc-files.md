---
description: Etapas para editar arquivos de inclusão do conjunto de dados existente.
title: Editar arquivos de inclusão existentes do conjunto de dados
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
exl-id: f4095871-d004-4e10-af18-bf6c1e47493d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 3%

---

# Editar arquivos de inclusão existentes do conjunto de dados{#editing-existing-dataset-include-files}

{{eol}}

Etapas para editar arquivos de inclusão do conjunto de dados existente.

Você abre um arquivo de inclusão de conjunto de dados existente usando o [!DNL Profile Manager] no Data Workbench.

Para obter informações sobre como abrir e trabalhar com a [!DNL Profile Manager], consulte o *Guia do usuário do Data Workbench*.

1. Ao trabalhar no perfil do conjunto de dados, abra o [!DNL Profile Manager] e clique em **[!UICONTROL Dataset]** para mostrar o conteúdo do diretório.

   * Para abrir um [!DNL Log Processing Dataset Include] , clique em **[!UICONTROL Log Processing]** para mostrar o conteúdo do diretório.

   * Para abrir um [!DNL Transformation Dataset Include] , clique em **[!UICONTROL Transformation]** para mostrar o conteúdo do diretório.

1. Clique com o botão direito do mouse na marca de seleção ao lado do arquivo de inclusão do conjunto de dados desejado e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece no [!DNL User] coluna.
1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. A janela de configuração é exibida.

   Também é possível abrir um arquivo de inclusão de conjunto de dados a partir de um [!DNL Transformation Dependency Maps]. Para obter informações sobre [!DNL Transformation Dependency Maps], consulte [Reprocessamento e retransformação](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

1. Edite os parâmetros no arquivo de configuração, conforme apropriado. Consulte [Arquivos de dados do conjunto de dados de processamento de log](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) ou [Arquivos de inclusão do conjunto de dados de transformação](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) para obter descrições dos parâmetros.

   Ao editar um arquivo de inclusão de conjunto de dados em uma janela do Data Workbench, você pode usar teclas de atalho para recursos básicos de edição, incluindo recortar (Ctrl+x ), copiar (Ctrl+c) , colar (Ctrl+v ), desfazer (Ctrl+z ), refazer (Ctrl+Shift+z ), selecionar seção (clicar+arrastar) e selecionar tudo (Ctrl+a ). Além disso, é possível usar os atalhos para copiar e colar o texto de um arquivo de configuração ( [!DNL .cfg]) para outro.

1. Para salvar as alterações, clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
1. Para que as alterações feitas localmente entrem em vigor, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo no [!DNL User] e, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, em que o nome do perfil é o nome do perfil do conjunto de dados ou o perfil herdado ao qual o arquivo de inclusão do conjunto de dados pertence. O reprocessamento ou a retransformação dos dados começam após a sincronização do perfil do conjunto de dados.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pelo Adobe, pois as alterações são substituídas ao instalar atualizações nesses perfis.
