---
description: Ao configurar seu conjunto de dados, você pode definir variáveis, conhecidas como parâmetros, para representar valores significativos.
solution: Analytics
title: Definindo Parâmetros no Conjunto de Dados Incluir Arquivos
topic: Data workbench
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definindo Parâmetros no Conjunto de Dados Incluir Arquivos{#defining-parameters-in-dataset-include-files}

Ao configurar seu conjunto de dados, você pode definir variáveis, conhecidas como parâmetros, para representar valores significativos.

Para atribuir um valor a um parâmetro (isto é, para definir o parâmetro), adicione o nome e o valor do parâmetro ao vetor Parâmetros em um processamento de log ou [!DNL Transformation Dataset Include] arquivo. Depois de definir os parâmetros, é possível referenciá-los nos arquivos de configuração do perfil do conjunto de dados. A definição e referência desses parâmetros é chamada de substituição de parâmetros. Usar a substituição de parâmetros ao configurar seu conjunto de dados permite criar um local centralizado para suas definições de parâmetros. Quando for necessário atualizar um parâmetro referenciado várias vezes ou em vários arquivos, é necessário fazer a alteração apenas uma vez.

>[!NOTE]
>
>Neste guia, o parâmetro de termo foi usado para fazer referência ao nome de qualquer configuração em um arquivo de configuração (como Condição de entrada do registro, Reprocessamento ou Transformações). No entanto, conforme usado nesta seção, o parâmetro refere-se especificamente a um membro do vetor Parâmetros em um conjunto de dados que inclui o arquivo e não ao nome de uma configuração em um arquivo de configuração.

Você deve considerar os seguintes pontos ao definir um parâmetro:

* Um parâmetro deve ser definido exatamente uma vez. Portanto, não é possível definir a mesma variável em vários conjuntos de dados que incluem arquivos.
* Qualquer parâmetro definido é local para as fases de processamento ou transformação do log, mas é global em vários arquivos de configuração do conjunto de dados para essa fase. Por exemplo, se você definir um parâmetro em um [!DNL Transformation Dataset Include] arquivo, ele será definido para toda a fase de transformação e poderá referenciá-lo no [!DNL Transformation.cfg] arquivo e em todos os outros [!DNL Transformation Dataset Include] arquivos para os perfis herdados. O parâmetro não seria definido para processamento de log; portanto, qualquer referência ao parâmetro no [!DNL Log Processing.cfg] arquivo ou em um [!DNL Log Processing Dataset Include] arquivo geraria um erro de processamento.

**Definição de um parâmetro**

É possível definir parâmetros de sequência, numéricos e vetoriais em [!DNL Log Processing] e [!DNL Transformation Include] arquivos.

1. Na janela da análise de big data do arquivo [!DNL Log Processing] ou [!DNL Transformation Dataset Include] , clique com o botão direito do mouse **[!UICONTROL Parameters]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Parameter]**.

1. Selecione **[!UICONTROL String Parameter]**, **[!UICONTROL Numeric Parameter]** ou **[!UICONTROL Vector Parameter]** e preencha os parâmetros Nome e Valor conforme descrito nas seções a seguir.

1. Para salvar o conjunto de dados, inclua um arquivo no qual você definiu o parâmetro, clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

1. Para que as alterações feitas localmente entrem em vigor, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] coluna, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, onde nome do perfil é o nome do perfil do conjunto de dados ou o perfil herdado ao qual o conjunto de dados inclui o arquivo.

>[!NOTE]
>
>Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pela Adobe, pois suas alterações são substituídas quando você instala atualizações nesses perfis.

**Para fazer referência a um parâmetro**

* Ao referenciar um parâmetro definido em outro arquivo de configuração de conjunto de dados, você deve digitar o nome como [!DNL $(parameter name)].

As seções a seguir descrevem os tipos de parâmetros que você pode definir.

* [Parâmetros de string e numéricos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [Parâmetros de vetor](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)

