---
description: É possível definir transformações de dados a serem aplicadas durante o processamento de log ou a fase de transformação da construção do conjunto de dados.
solution: Analytics
title: Definição de uma transformação
topic: Data workbench
uuid: 69dd667b-e465-4c1a-a20e-4384e8988cd0
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Definição de uma transformação{#defining-a-transformation}

É possível definir transformações de dados a serem aplicadas durante o processamento de log ou a fase de transformação da construção do conjunto de dados.

>[!NOTE]
>
>A Adobe recomenda definir transformações em um dos arquivos [!DNL Log Processing] ou [!DNL Transformation Dataset Include] em vez de dentro [!DNL Log Processing.cfg] ou [!DNL Transformation.cfg].

As seguintes transformações funcionam somente quando definidas no [!DNL Transformation.cfg] arquivo ou em um [!DNL Transformation Dataset Include] arquivo:

* [](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-appenduri.md#concept-a0df05dd958645bf8219fc7b0b675ee4)AppendURII
* [CrossRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2)
* [LookupRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-lookuprows.md#concept-4bd9a1f13ee243e592a6a0008053134f)
* [Fontes de dados ODBC](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)
* [Sessionize](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-sessionize.md#concept-b1af95c8cba34b248f86de883d914bc0)

**Definição de uma transformação**

1. Use o [!DNL Profile Manager] para abrir o arquivo de configuração do conjunto de dados no qual você deseja definir a transformação.

   * (Recomendado) Para abrir um arquivo de inclusão de conjunto de dados, consulte [Arquivo de inclusão de conjunto de dados](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).
   * Para abrir o [!DNL Log Processing.cfg] arquivo, consulte [Edição do arquivo](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)de configuração de processamento de log.

   * Para abrir o [!DNL Transformation.cfg] arquivo, consulte [Editando o arquivo](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)de configuração de transformação.

1. Clique com o botão direito do mouse **[!UICONTROL Transformations]**, em seguida, clique em **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Transformation type]**>*.
1. Insira as informações apropriadas para sua transformação. Para obter descrições dos tipos de transformação e informações sobre seus parâmetros, consulte as seguintes seções:

   * [Transformações padrão](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-standard-transf.md#concept-25f4bdbf8fe74c4aaeb2fcd226243886)
   * [Transformações de URI](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-uri-transf.md#concept-2dfa0ffcd83d4fb69c1f42ad50dea125)
   * [Integração de dados de pesquisa](../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-int-lookup-data.md#concept-08ff70769a464f50ab14299a344f05c7)

1. Depois de definir suas transformações no arquivo de configuração, salve o arquivo localmente e salve-o no perfil do conjunto de dados no servidor da análise de big data.

       Dicas para definir e editar transformações:
   
   * Ao editar a configuração de uma transformação em uma janela do análise de big data, você pode usar teclas de atalho para recursos básicos de edição, incluindo recortar (Ctrl+x ), copiar (Ctrl+c), colar (Ctrl+v ), desfazer (Ctrl+z ), refazer (Ctrl+Shift+z ), selecionar seção (clique+arrastar) e selecionar tudo (Ctrl+a ). Além disso, você pode usar os atalhos para copiar e colar texto ou definições de transformação inteiras de um arquivo de configuração ( [!DNL .cfg]) para outro.
   * Para qualquer transformação definida, é possível adicionar uma ou mais linhas de comentário ao parâmetro Comentários para descrever a transformação ou adicionar observações sobre o uso. Para adicionar um comentário usando a análise de big data, clique com o botão direito do mouse no **[!UICONTROL Comments]** rótulo e clique em **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

   * É possível abrir a configuração de qualquer transformação a partir de um [!DNL Transformation Dependency Map]. Depois de abrir a configuração, é possível editá-la e salvar as alterações. Para obter informações sobre [!DNL Transformation Dependency Maps], consulte Ferramentas [de configuração de](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)conjuntos de dados.

   * Uma saída de string vazia de uma transformação pode substituir uma string não vazia no campo de saída.

