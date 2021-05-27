---
description: Ao configurar seu conjunto de dados, você pode definir variáveis, referidas como parâmetros, para representar valores significativos.
title: Definir parâmetros nos arquivos de inclusão do conjunto de dados
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
exl-id: 80bb77e1-a157-4e16-9519-6d0e2ce17fe1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 3%

---

# Definir parâmetros nos arquivos de inclusão do conjunto de dados{#defining-parameters-in-dataset-include-files}

Ao configurar seu conjunto de dados, você pode definir variáveis, referidas como parâmetros, para representar valores significativos.

Para atribuir um valor a um parâmetro (ou seja, para definir o parâmetro), adicione o nome e o valor do parâmetro ao vetor Parameters em um processamento de log ou em um arquivo [!DNL Transformation Dataset Include]. Após definir os parâmetros, é possível referenciá-los nos arquivos de configuração do perfil do conjunto de dados. A definição e referência a esses parâmetros é chamada de substituição de parâmetro. Usar a substituição de parâmetros ao configurar seu conjunto de dados permite criar um local centralizado para suas definições de parâmetros. Quando for necessário atualizar um parâmetro referenciado várias vezes ou em vários arquivos, é necessário fazer a alteração apenas uma vez.

>[!NOTE]
>
>Neste guia, o parâmetro de termo foi usado para se referir ao nome de qualquer configuração em um arquivo de configuração (como Condição de entrada de log, Reprocessamento ou Transformações). No entanto, conforme usado nesta seção, o parâmetro se refere especificamente a um membro do vetor Parâmetros em um arquivo de inclusão de conjunto de dados e não ao nome de uma configuração em um arquivo de configuração.

Considere os seguintes pontos ao definir um parâmetro:

* Um parâmetro deve ser definido exatamente uma vez. Portanto, não é possível definir a mesma variável em vários arquivos de inclusão do conjunto de dados.
* Qualquer parâmetro definido é local para as fases de processamento do log ou de transformação, mas é global em vários arquivos de configuração de conjunto de dados para essa fase. Por exemplo, se você definir um parâmetro em um arquivo [!DNL Transformation Dataset Include], o parâmetro será definido para toda a fase de transformação e você poderá referenciá-lo no arquivo [!DNL Transformation.cfg] e em todos os outros arquivos [!DNL Transformation Dataset Include] para os perfis herdados. O parâmetro não seria definido para processamento de log; portanto, qualquer referência ao parâmetro no arquivo [!DNL Log Processing.cfg] ou em um arquivo [!DNL Log Processing Dataset Include] geraria um erro de processamento.

**Definição de um parâmetro**

Você pode definir parâmetros de string, numéricos e de vetor em arquivos [!DNL Log Processing] e [!DNL Transformation Include].

1. Na janela do Data Workbench para o arquivo [!DNL Log Processing] ou [!DNL Transformation Dataset Include], clique com o botão direito do mouse **[!UICONTROL Parameters]** e depois clique em **[!UICONTROL Add new]** > **[!UICONTROL Parameter]**.

1. Selecione **[!UICONTROL String Parameter]**, **[!UICONTROL Numeric Parameter]** ou **[!UICONTROL Vector Parameter]** e preencha os parâmetros Nome e Valor conforme descrito nas seções a seguir.

1. Para salvar o arquivo de inclusão do conjunto de dados no qual você definiu o parâmetro, clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

1. Para que as alterações feitas localmente tenham efeito, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, onde o nome do perfil é o nome do perfil do conjunto de dados ou do perfil herdado ao qual pertence o arquivo de inclusão do conjunto de dados.

>[!NOTE]
>
>Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pelo Adobe, pois as alterações são substituídas ao instalar atualizações nesses perfis.

**Para fazer referência a um parâmetro**

* Ao referenciar um parâmetro definido em outro arquivo de configuração de conjunto de dados, você deve digitar seu nome como [!DNL $(parameter name)].

As seções a seguir descrevem os tipos de parâmetros que você pode definir.

* [Parâmetros de string e numéricos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [Parâmetros de vetor](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)
