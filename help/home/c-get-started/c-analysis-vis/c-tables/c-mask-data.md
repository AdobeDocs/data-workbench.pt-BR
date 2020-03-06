---
description: Mascaramento refere-se à seleção de um subconjunto de seus dados ou de um subconjunto dos elementos em uma dimensão.
solution: Analytics
title: Mascarar dados
topic: Data workbench
uuid: 81b5f4e0-826c-4803-9169-66a424a4ea9f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mascarar dados{#mask-data}

Mascaramento refere-se à seleção de um subconjunto de seus dados ou de um subconjunto dos elementos em uma dimensão.

Você mascara ou oculta os elementos que não deseja incluir na análise.

A Análise de big data fornece dois métodos para mascarar elementos de dimensão. O primeiro método emprega as opções disponíveis no [!DNL Mask] menu. Usando as opções de [!DNL Mask] menu, você pode usar o mouse para selecionar esses elementos para mostrar ou mascarar, ou pode mostrar elementos classificados acima ao classificar os dados por métrica. O segundo método para mascarar elementos de dimensão emprega uma pesquisa.

**Para mascarar dados**

1. Clique com o botão direito do mouse em um elemento ou no rótulo da dimensão desejada e clique em **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_Mask.png)

1. Clique em uma das seguintes opções:

   * **[!UICONTROL Show all]**
   * **[!UICONTROL Show selected only]**
   * **[!UICONTROL Hide selected]**
   * **[!UICONTROL Show top > 5, 10, 25, 50, 100]** ou **[!UICONTROL 500]** dos elementos exibidos classificados por métrica
   * **[!UICONTROL Show top > All Positive]** para mostrar somente valores maiores que zero (0)
   * **[!UICONTROL Display “X more”]** para mostrar o número de elementos mascarados no momento
   * **[!UICONTROL At least one >]***&lt; **[!UICONTROL countable dimension name]**>*(disponível somente ao trabalhar com uma dimensão desnormalizada)

      Ao trabalhar com uma dimensão desnormalizada, essa opção permite mascarar uma dimensão por uma dimensão contável. Quando selecionada, a tabela mostra apenas os elementos que têm pelo menos um elemento da dimensão contável selecionada. A tabela exibe até 1.023 elementos.

>[!NOTE]
>
>Como a Adobe [!DNL Platform] processa dados em ordem aleatória, quando pelo menos uma máscara resulta em mais de 1.023 elementos, os elementos mais comuns e maiores têm maior chance de serem incluídos na tabela.

Quando você coloca uma máscara em Mostrar na parte superior ou Pelo menos uma, por padrão, a ordem na tabela corresponde aos valores afetados pela seleção no momento. Se posteriormente você alterar a seleção, a ordem não será alterada a partir da ordem original, a menos que a tabela seja reordenada ou que você ative a Seleção dinâmica. Quando você clica em **[!UICONTROL Mask]** > **[!UICONTROL Dynamic Selection]**, a tabela é reordenada sempre que você altera a seleção.

**Para mascarar dados usando uma pesquisa**

* É possível mascarar dados usando uma das seguintes opções de pesquisa:

   * Clique com o botão direito do mouse em um elemento ou no rótulo da dimensão desejada, clique em **[!UICONTROL Mask]**[!DNL Search] e, na caixa, digite a frase para a qual deseja pesquisar.

      ![](assets/mnu_Table_MaskSearch.png)

   * Clique com o botão direito do mouse em um elemento ou no rótulo da dimensão desejada, clique em **[!UICONTROL Mask]** > **[!UICONTROL Display search bar]** e, na caixa de pesquisa que é exibida na célula do rótulo da dimensão, digite a frase para a qual deseja pesquisar.

      ![](assets/vis_Table_Mask_searchBar.png)

      Conforme você digita uma frase de pesquisa, a Análise de big data atualiza a dimensão para refletir correspondências.

Para restringir ainda mais o mascaramento durante uma pesquisa, você pode usar qualquer um dos seguintes métodos:

* Você pode digitar &quot;re:&quot; na [!DNL search] caixa ou na barra para que a frase de pesquisa seja interpretada como uma expressão regular. Você pode usar qualquer sintaxe associada a expressões regulares na frase de pesquisa. Para obter mais informações sobre expressões regulares, consulte o apêndice Expressão regular no Guia *de configuração de* conjuntos de dados.
* Você pode digitar o símbolo $ como o primeiro caractere em sua string de pesquisa para localizar frases que começam com a string digitada ou como o último caractere para localizar frases que terminam com a string digitada.
* Você pode digitar um espaço como o primeiro caractere na sequência de caracteres de pesquisa para localizar quaisquer palavras em uma frase que comecem com a sequência inserida ou como o último caractere para localizar quaisquer palavras em uma frase que terminem com a sequência inserida.

Veja a seguir exemplos de maneiras diferentes de mascarar uma tabela usando a string &quot;on&quot; em uma pesquisa:

* Digitar &quot;on&quot; exibe cada frase que contém a string &quot;on&quot; em qualquer lugar na frase: &quot;banco **** online&quot;, &quot;**** contatos compradores&quot;, &quot;moedas de **bilhão** &quot;, &quot;banco **** online&quot;, &quot;**** opções de ouro&quot; e &quot;**bilhão** de prata&quot;.
* A digitação de &quot;$on&quot; exibe cada frase que começa com a string &quot;on&quot;:

   &quot;banco **** online&quot; e &quot;pagamento **online**&quot;.

* Digitar &quot;on$&quot; exibe cada frase que termina com a string &quot;on&quot;:

   &quot;**Bola** de prata&quot; e &quot;**opção** de ouro&quot;.

* Ao digitar &quot;on&quot;, é exibida cada frase que contém uma palavra que começa com a string &quot;on&quot;:

   &quot;banco **** online&quot; e &quot;banco **** online&quot;.

* Digitar &quot;on&quot; exibe cada frase que contém uma palavra que termina com a string &quot;on&quot;:

   &quot;moedas de **ouro** &quot; e &quot;**ouro** prateado&quot;.

* O uso de &quot;on&quot; exibe cada frase que contém a string &quot;on&quot; como uma palavra:

   &quot;**on** line banking&quot; e &quot;bank **on** line&quot;.

