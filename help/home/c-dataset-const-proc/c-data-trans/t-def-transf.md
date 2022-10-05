---
description: Você pode definir transformações de dados a serem aplicadas durante o processamento de log ou a fase de transformação da construção do conjunto de dados.
title: Definir uma transformação
uuid: 69dd667b-e465-4c1a-a20e-4384e8988cd0
exl-id: 61ce8093-9e64-419a-bddc-dc2225c0eaab
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 5%

---

# Definir uma transformação{#defining-a-transformation}

{{eol}}

Você pode definir transformações de dados a serem aplicadas durante o processamento de log ou a fase de transformação da construção do conjunto de dados.

>[!NOTE]
>
>O Adobe recomenda definir transformações em [!DNL Log Processing] ou [!DNL Transformation Dataset Include] arquivos em vez de em [!DNL Log Processing.cfg] ou [!DNL Transformation.cfg].

As seguintes transformações funcionam somente quando definidas no [!DNL Transformation.cfg] ou em um [!DNL Transformation Dataset Include] arquivo:

* [AppendURI](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-appenduri.md#concept-a0df05dd958645bf8219fc7b0b675ee4)I
* [CrossRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2)
* [LookupRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-lookuprows.md#concept-4bd9a1f13ee243e592a6a0008053134f)
* [Fontes de dados ODBC](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)
* [Sessionize](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-sessionize.md#concept-b1af95c8cba34b248f86de883d914bc0)

**Para definir uma transformação**

1. Use o [!DNL Profile Manager] para abrir o arquivo de configuração do conjunto de dados no qual deseja definir a transformação.

   * (Recomendado) Para abrir um arquivo de inclusão do conjunto de dados, consulte [Arquivos de inclusão do conjunto de dados](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).
   * Para abrir o [!DNL Log Processing.cfg] arquivo, consulte [Editar o arquivo de configuração de processamento de log](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

   * Para abrir o [!DNL Transformation.cfg] arquivo, consulte [Editar o arquivo de configuração de transformação](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

1. Clique com o botão direito do mouse **[!UICONTROL Transformations]**, depois clique em **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Transformation type]**>*.
1. Insira as informações apropriadas para sua transformação. Para obter descrições dos tipos de transformação e informações sobre seus parâmetros, consulte as seguintes seções:

   * [Transformações padrão](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-standard-transf.md#concept-25f4bdbf8fe74c4aaeb2fcd226243886)
   * [Transformações de URI](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-uri-transf.md#concept-2dfa0ffcd83d4fb69c1f42ad50dea125)
   * [Integração de dados de pesquisa](../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-int-lookup-data.md#concept-08ff70769a464f50ab14299a344f05c7)

1. Depois de definir as transformações no arquivo de configuração, salve o arquivo localmente e salve-o no perfil do conjunto de dados no servidor do Data Workbench.

       Dicas para definir e editar transformações:
   
   * Ao editar a configuração de uma transformação em uma janela do Data Workbench, você pode usar teclas de atalho para recursos básicos de edição, incluindo recortar (Ctrl+x ), copiar (Ctrl+c) , colar (Ctrl+v ), desfazer (Ctrl+z ), refazer (Ctrl+Shift+z ), selecionar seção (clicar+arrastar) e selecionar tudo (Ctrl+a ). Além disso, é possível usar os atalhos para copiar e colar o texto ou as definições de transformação inteiras de um arquivo de configuração ( [!DNL .cfg]) para outro.
   * Para qualquer transformação definida, é possível adicionar uma ou mais linhas de comentário ao parâmetro Comentários para descrever ainda mais a transformação ou adicionar observações sobre o uso. Para adicionar um comentário usando o Data Workbench, clique com o botão direito do mouse no **[!UICONTROL Comments]** rótulo e clique em **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

   * Você pode abrir a configuração de qualquer transformação a partir de um [!DNL Transformation Dependency Map]. Após abrir a configuração, você pode editá-la e salvar as alterações. Para obter informações sobre [!DNL Transformation Dependency Maps], consulte [Ferramentas de configuração do conjunto de dados](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

   * Uma saída de string vazia de uma transformação pode substituir uma string que não esteja vazia no campo de saída.
