---
description: Etapas para definir dimensões estendidas.
solution: Analytics
title: Definindo Dimensões Estendidas
topic: Data workbench
uuid: 25946998-54ca-4595-a2f9-9c593917643a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Definindo Dimensões Estendidas{#defining-extended-dimensions}

Etapas para definir dimensões estendidas.

1. Ao trabalhar em seu perfil de conjunto de dados, abra o [!DNL Profile Manager] e clique **[!UICONTROL Dataset]** para mostrar seu conteúdo.
1. Abra o [!DNL Transformation.cfg] arquivo ou o [!DNL Transformation Dataset Include] arquivo no qual você deseja definir a dimensão estendida.

   * (Recomendado) Para abrir um arquivo de inclusão de conjunto de dados, consulte [Arquivo de inclusão de conjunto de dados](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

      >[!NOTE]
      >
      >A Adobe recomenda definir dimensões estendidas em um ou mais [!DNL Transformation Dataset Include] arquivos novos. Para obter mais informações, consulte [Criação de novos arquivos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e)de inclusão de conjuntos de dados.

   * Para abrir o [!DNL Transformation.cfg] arquivo, consulte [Editando o arquivo](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)de configuração de transformação.

1. Clique com o botão direito do mouse **[!UICONTROL Transformations]** e clique em **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Extended dimension type]**>*.
1. Insira as informações apropriadas para sua dimensão estendida. Para obter descrições dos tipos de transformação e informações sobre seus parâmetros, consulte as seguintes seções:

   * [Dimensões contáveis](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)
   * [Dimensões simples](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-simple-dim.md#concept-c1d804dac4094489afe61560d2908181)
   * [Dimensões de muitos para muitos](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-many-dim.md#concept-5ed3cca8b2194d4f96134f6238040998)
   * [Dimensões numéricas](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed)
   * [Dimensões desnormalizadas](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-denormal-dim.md#concept-54a2600b8ee748b7acff405daccf3489)
   * [Dimensões de tempo](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-time-dim.md#concept-1e4eeb8d33964bb2a8d5768d6439df67)

      Para qualquer dimensão estendida que você definir, é possível adicionar uma ou mais linhas de comentário ao parâmetro Comentários para descrever a dimensão ou adicionar observações sobre seu uso. Para adicionar um comentário, clique com o botão direito do mouse no **[!UICONTROL Comments]** rótulo e clique em **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

1. Depois de definir suas dimensões estendidas no arquivo de configuração, salve o arquivo localmente e salve-o no perfil do conjunto de dados no servidor da análise de big data.
