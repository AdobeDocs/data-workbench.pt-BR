---
description: O processamento de arquivos de log como fontes de log requer a definição de um decodificador no arquivo Incluir do Conjunto de Dados de Processamento de Log para extrair campos de dados das entradas de log.
solution: Analytics
title: Grupos do decodificador de arquivos de texto
topic: Data workbench
uuid: 3ff9700b-4f34-4098-8827-6856897bdb28
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Grupos do decodificador de arquivos de texto{#text-file-decoder-groups}

O processamento de arquivos de log como fontes de log requer a definição de um decodificador no arquivo Incluir do Conjunto de Dados de Processamento de Log para extrair campos de dados das entradas de log.

A definição de grupos do decodificador de arquivos de texto para fontes de log requer conhecimento da estrutura e do conteúdo do arquivo de log, dos dados a serem extraídos e dos campos nos quais esses dados são armazenados. Esta seção fornece descrições básicas dos parâmetros que você pode especificar para decodificadores, mas a maneira como você usa qualquer decodificador depende do arquivo de log que contém os dados de origem.

Para obter informações sobre os requisitos de formato para fontes de log de arquivos, consulte Arquivos [de Log](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e). Para obter ajuda com a definição de decodificadores de arquivos de texto, entre em contato com a Adobe.

Um grupo de decodificador de arquivos de texto pode incluir:

* [Decodificadores de expressão regular](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-67aca2c1f008404da7f845a64abec97c)
* [Decodificadores Delimitados](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-7e0a23decdbc4c75ae750a42446997a6)

## Decodificadores de expressão regular {#section-67aca2c1f008404da7f845a64abec97c}

Um decodificador de expressão regular identifica padrões complexos de sequência dentro das entradas de log em um arquivo de log e extrai esses padrões como campos de dados. Para cada decodificador, o número de campos deve ser igual ao número de subpadrões de captura na expressão regular. A parte da linha que corresponde ao subpadrão de captura n é atribuída ao enésimo campo dessa linha.

**Para adicionar um decodificador de expressão regular a um grupo decodificador de arquivos de texto**

1. Abra o [!DNL Log Processing Dataset Include] arquivo conforme descrito em [Edição de conjuntos de dados existentes Incluir arquivos](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) e adicione um grupo de decodificador de arquivos de texto. Consulte a entrada da tabela Grupos [](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)decodificadores.

1. Clique com o botão direito do mouse **[!UICONTROL Decoders]** no grupo de decodificadores recém-criado e clique em **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.

1. Especifique as seguintes informações:

   * **Campos:** Lista dos campos no arquivo de log. Se algum dos campos definidos aqui forem transmitidos para a fase de transformação da construção do conjunto de dados, esses campos deverão ser listados no parâmetro Campos de um dos [!DNL Log Processing Dataset Include] arquivos do conjunto de dados. Os nomes de campos personalizados devem começar com &quot;x-&quot;.

   * **Nome:** Identificador opcional para o decodificador.
   * **Expressão regular:** Usado para extrair os campos desejados de cada linha do arquivo.

1. Repita as etapas 4 e 5 para qualquer outro decodificador que você deseja adicionar ao grupo.
1. Para salvar o [!DNL Log Processing Dataset Include] arquivo, clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

1. Para que as alterações feitas localmente entrem em vigor, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] coluna. Clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, onde nome do perfil é o nome do perfil do conjunto de dados ou o perfil herdado ao qual o conjunto de dados inclui o arquivo.

Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pela Adobe, pois suas alterações são substituídas quando você instala atualizações nesses perfis.

>[!NOTE]
>
>Um determinado arquivo de log pode ter vários decodificadores de expressão regular. A ordem em que você define os decodificadores é importante: o primeiro decodificador a corresponder a uma linha no arquivo de log é o usado para decodificar essa linha.

Este exemplo ilustra o uso de um decodificador de expressão regular para extrair campos de dados de um arquivo de texto delimitado por tabulação. Você pode obter o mesmo resultado definindo um decodificador delimitado com um delimitador de tabulação.

![](assets/cfg_LogProcessingInclude_RegExpDecoder.png)

Para obter mais informações sobre decodificadores de expressões regulares, incluindo terminologia e sintaxe, consulte Expressões [regulares](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

## Decodificadores Delimitados {#section-7e0a23decdbc4c75ae750a42446997a6}

Um decodificador delimitado decodifica um arquivo de log cujos campos são delimitados por um único caractere. O número de campos deve corresponder ao número de colunas no arquivo delimitado; no entanto, nem todos os campos precisam ser nomeados. Se um campo ficar em branco, a coluna ainda será necessária no arquivo de log, mas o decodificador a ignorará.

**Para adicionar um decodificador delimitado a um grupo de decodificador de arquivos de texto**

1. Abra o [!DNL Log Processing Dataset Include] arquivo conforme descrito em [Edição de conjuntos de dados existentes Incluir arquivos](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) e adicione um grupo de decodificador de arquivos de texto. Consulte a entrada da tabela Grupos [](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)decodificadores.

1. Clique com o botão direito do mouse **[!UICONTROL Decoders]** no grupo de decodificadores recém-criado e clique em **[!UICONTROL Add new]** > **[!UICONTROL Delimited]**.

1. Especifique as seguintes informações:

   * **Campos:** Lista dos campos no arquivo de log. Se algum dos campos definidos aqui forem transmitidos para a fase de transformação da construção do conjunto de dados, esses campos deverão ser listados no parâmetro Campos de um dos [!DNL Log Processing Dataset Include] arquivos do conjunto de dados. Os nomes de campos personalizados devem começar com &quot;x-&quot;.

   * **Delimitador:** Caractere usado para separar campos no arquivo de saída.

1. Repita as etapas 4 e 5 para qualquer outro decodificador que você deseja adicionar ao grupo.
1. Para salvar o [!DNL Log Processing Dataset Include] arquivo, clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

1. Para que as alterações feitas localmente entrem em vigor, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] coluna, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, onde nome do perfil é o nome do perfil do conjunto de dados ou o perfil herdado ao qual o conjunto de dados inclui o arquivo.

>[!NOTE]
>
>Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pela Adobe, pois suas alterações são substituídas quando você instala atualizações nesses perfis.

Este exemplo ilustra o uso de um decodificador delimitado para extrair campos de dados de um arquivo de texto delimitado por vírgulas contendo dados sobre filmes.

![](assets/cfg_LogProcessingInclude_DelimitedDecoder.png)

