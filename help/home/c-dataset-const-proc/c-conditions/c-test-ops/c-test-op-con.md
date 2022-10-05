---
description: Informações sobre as condições da operação de teste incluindo comparação, não vazia, intervalo, expressão regular e correspondência de sequência.
title: Condições de funcionamento do teste
uuid: 6a117569-1372-4095-972b-76289a45f19e
exl-id: 6c1f521b-a6b9-4bb7-bdfa-56c615b0c916
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 5%

---

# Condições de funcionamento do teste{#test-operation-conditions}

{{eol}}

Informações sobre as condições da operação de teste incluindo comparação, não vazia, intervalo, expressão regular e correspondência de sequência.

* [Comparar](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-fb2bdb3838504099b324b9838cdeeaac)
* [Não Vazio](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)
* [Intervalo](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1db31583bb09418b8f49481a897b08a6)
* [Expressão regular](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-ae9c016502cb44128760c58f2d2d5297)
* [Correspondência de sequência](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-f8d132085c6b4500bfbe4515b848142f)

## Comparar {#section-fb2bdb3838504099b324b9838cdeeaac}

O [!DNL Compare] compara valores de string ou numéricos. Para comparações de valores de string, é possível especificar se as letras maiúsculas e minúsculas devem ser consideradas.

Os parâmetros do [!DNL Compare] estão descritas na tabela a seguir:

<table id="table_05B1FBB2AED242D99081E62BE2FBEC60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Diferenciação de maiúsculas e minúsculas </td> 
   <td colname="col2">Verdadeiro ou falso. Usado somente se o Tipo for <span class="wintitle"> LEXICAL</span>. Se definido como falso, letras maiúsculas e minúsculas são consideradas iguais. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Notas sobre a condição. </td> 
   <td colname="col3"> Comentários </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada A </td> 
   <td colname="col2"> O primeiro dos dois valores a serem comparados. Esse valor representa o operando esquerdo na condição. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada B </td> 
   <td colname="col2"> O segundo dos dois valores a serem comparados. Esse valor representa o operando correto na condição. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operação </td> 
   <td colname="col2"> <p>A operação de comparação. As operações disponíveis (e seus significados) são as seguintes: 
     <ul id="ul_74F3C298E9CC4FE89897BA0052A9EB9F"> 
      <li id="li_1605FA73474E404A84056D40E7082623"> = ou == (Entrada A é igual à Entrada B) </li> 
      <li id="li_F694A262ED7A4787B2A68B877339620C"> &lt;&gt; ou != (A entrada A não é igual à entrada B) </li> 
      <li id="li_1A75437E23B64BEB92297E1C771092B0"> &lt; (A entrada A é inferior à entrada B) </li> 
      <li id="li_B80ED6BE9DEA41FE84BC6BA3B7759276"> &lt;= (A entrada A é menor ou igual à entrada B) </li> 
      <li id="li_93148F34065F489E8E198DFB9F9F0E70"> &gt; (A entrada A é maior que a entrada B) </li> 
      <li id="li_8A98EE9AED2445429805169040BB253D"> &gt;= (A entrada A é maior ou igual à entrada B) </li> 
     </ul> </p> </td> 
   <td colname="col3"> = </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tipo </td> 
   <td colname="col2">O tipo de comparação a ser feita. Os tipos disponíveis são <span class="wintitle"> LEXICAL</span>, <span class="wintitle"> NUMÉRICO</span>e <span class="wintitle"> DATETIME</span>. Para obter descrições dos tipos, consulte <a href="../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-types.md#concept-a9fca97a2f03464cb0cbab8b5f809d0a"> Tipos de teste para operações de teste</a>. </td> 
   <td colname="col3"> <span class="wintitle"> LEXICAL</span> </td> 
  </tr> 
 </tbody> 
</table>

Esse exemplo usa um [!DNL Compare] para definir a [!DNL Log Entry Condition]. Conforme o servidor do Data Workbench lê cada registro de dados do evento, ele compara os valores numéricos x-age e 55. Se para uma determinada entrada de log, x-age é menor ou igual a 55, a entrada de log é incluída no processo de construção do conjunto de dados.

![](assets/cfg_Condition_CompareCondition.png)

## Não Vazio {#section-1decb9d887894073a1b6b3d985729ac8}

O [!DNL Not Empty] verifica um campo para ver se ele contém um valor ou está vazio. A condição é atendida para qualquer entrada de log cujo valor para a variável [!DNL Input] campo não está vazio.

Os parâmetros do [!DNL Not Empty] estão descritas na tabela a seguir:

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Comentários | Opcional. Notas sobre a condição. | Comentários |
| Entrada | O nome do campo da entrada de log para verificar o conteúdo. |  |

Este exemplo assume como entrada um x-some-field e testa se o campo não está vazio. A condição será atendida se o campo for preenchido.

![](assets/cfg_Condition_NotEmpty.png)

## Intervalo {#section-1db31583bb09418b8f49481a897b08a6}

O [!DNL Range] pega um campo de entrada e determina se o valor desse campo se enquadra, inclusive, nos valores de parâmetro mínimo (Min) e máximo (Max) fornecidos.

Os parâmetros do [!DNL Range] estão descritas na tabela a seguir:

<table id="table_1587D8D333804FC28024C0DFC2F2D4D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Diferenciação de maiúsculas e minúsculas </td> 
   <td colname="col2">Verdadeiro ou falso. Usado somente se a variável <span class="wintitle"> Tipo</span> é <span class="wintitle"> LEXICAL</span>. Se definido como falso, letras maiúsculas e minúsculas são consideradas iguais. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Notas sobre a condição. </td> 
   <td colname="col3"> Comentários </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> O nome do campo da entrada de log a ser usada como entrada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Versão mín </td> 
   <td colname="col2"> <p>Limite inferior do intervalo. </p> <p> O valor desse parâmetro deve ser um valor literal ou uma string, não um nome de campo. Se você usar uma data para esse campo, deverá especificar um fuso horário. Para obter uma lista de abreviações de fuso horário suportadas, consulte <a href="../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de fuso horário</a>. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Máx </td> 
   <td colname="col2"> <p>Limite superior do intervalo. </p> <p> <p>Observação: O valor desse parâmetro deve ser um valor literal ou uma string, não um nome de campo. Se você usar uma data para esse campo, deverá especificar um fuso horário. Para obter uma lista de abreviações de fuso horário suportadas, consulte <a href="../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de fuso horário</a>. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tipo </td> 
   <td colname="col2">O tipo de comparação a ser feita. Os tipos disponíveis são <span class="wintitle"> LEXICAL</span>, <span class="wintitle"> NUMÉRICO</span>e <span class="wintitle"> DATETIME</span>. Para obter descrições dos tipos, consulte <a href="../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-types.md#concept-a9fca97a2f03464cb0cbab8b5f809d0a"> Tipos de teste para operações de teste</a>. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Esse exemplo usa um [!DNL Range] para definir a [!DNL Log Entry Condition]. Conforme o servidor do Data Workbench lê cada [!DNL event data] , compara os valores numéricos x-age e 55. Se para uma determinada entrada de log, x-age é pelo menos 55, a entrada de log é incluída no processo de construção do conjunto de dados. Esse exemplo executa a mesma função da função [!DNL Compare] exemplo de condição. Consulte [Comparar](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-fb2bdb3838504099b324b9838cdeeaac).

>[!NOTE]
>
>Se o parâmetro Min ou Max for deixado em branco, o servidor do Data Workbench substituirá os valores inteiros mínimo ou máximo disponíveis. O valor mínimo é zero (0) e o valor máximo é infinito.

![](assets/cfg_Condition_RangeCondition.png)

## Expressão regular {#section-ae9c016502cb44128760c58f2d2d5297}

O [!DNL Regular Expression] o teste de condição usa a correspondência de padrões de expressões regulares (consulte [Expressões regulares](../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c)) para determinar se o valor do campo de entrada especificado contém uma string que corresponde a um dos padrões especificados no parâmetro Matches .

Se a entrada for um vetor de cadeias de caracteres, somente o primeiro valor no vetor será usado para o teste. O [!DNL Regular Expression] A condição executa comparações completas de sequências de caracteres. Se quiser identificar subsequências de caracteres, anexe e anexe &quot;.&#42;&quot; para a string.

Os parâmetros do [!DNL Regular Expression] estão descritas na tabela a seguir:

<table id="table_0BF5F89F87C9493B8DABA97620074FAD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Diferenciação de maiúsculas e minúsculas </td> 
   <td colname="col2"> Verdadeiro ou falso. Se definido como falso, letras maiúsculas e minúsculas são consideradas iguais. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Notas sobre a condição. </td> 
   <td colname="col3"> Comentários </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> O nome do campo da entrada de log a ser usada como entrada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Corresponde </td> 
   <td colname="col2"> <p>Os padrões de expressão regular a serem comparados com o valor do campo de entrada. </p> <p> <b> Para adicionar um padrão de expressão regular</b> 
     <ol id="ol_6D6467FF74334DEA8E8625C3B155D11D"> 
      <li id="li_9E13A63558FF44749C2E49BD50B7F770">Clique com o botão direito do mouse <span class="uicontrol"> Corresponde</span>. </li> 
      <li id="li_195A2F3B6B9442F5B1DACDE0FC96CE5C">Clique em <span class="uicontrol"> Adicionar novo</span> &gt; <span class="uicontrol"> Expressão regular</span>. </li> 
      <li id="li_225E98F8EF39426A9483B86EA2CFE6DF">Digite a expressão regular desejada na caixa de texto. </li> 
     </ol> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Este exemplo ilustra o uso da variável [!DNL Regular Expression] para corresponder a um campo de dados coletados do tráfego do site. A condição retornará true somente se o campo cs(referrer-query) contiver uma string que corresponda à expressão regular `campaign=C[1-9][0-9]{4}`. Essa expressão regular corresponde a qualquer string que contenha `campaign=C12345`. No entanto, o padrão não corresponderia à string `campaign=C0123&` porque o primeiro caractere após a variável `C` não está no intervalo `1-9`.

![](assets/cfg_Condition_RegularExpression.png)

## Correspondência de sequência {#section-f8d132085c6b4500bfbe4515b848142f}

O [!DNL String Match] teste de condição para igualdade de string. Ele pega um campo especificado como entrada e testa o valor desse campo em cada entrada de log em relação às strings especificadas no parâmetro Correspondências da operação. Se qualquer uma dessas strings de correspondência que diferenciam maiúsculas e minúsculas for igual ao valor no campo de entrada fornecido, a operação retornará true. Caso a variável [!DNL StringCondition] não contém strings de correspondência, a condição retorna false. Se a entrada for um vetor de cadeias de caracteres, somente o primeiro valor (cadeia de caracteres) no vetor será usado para o teste.

<table id="table_BD599BAA5DD54B278813B6C38AC8DE6B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Diferenciação de maiúsculas e minúsculas </td> 
   <td colname="col2"> Verdadeiro ou falso. Se definido como falso, letras maiúsculas e minúsculas são consideradas iguais. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Notas sobre a condição. </td> 
   <td colname="col3"> Comentários </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> O nome do campo da entrada de log a ser usada como entrada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Corresponde </td> 
   <td colname="col2"> <p>A(s) string(s) a ser(em) correspondente(s) ao valor do campo de entrada. </p> <p> <b>Para adicionar uma string</b> 
     <ol id="ol_9E32218C771445D88357960475FAD6EB"> 
      <li id="li_A700747858D0470491783E9B3933DAFE">Clique com o botão direito do mouse <span class="uicontrol"> Corresponde</span>. </li> 
      <li id="li_9D1A2462EA404B0F84426176737CAFED">Clique em <span class="uicontrol"> Adicionar novo</span> &gt; <span class="uicontrol"> String</span>. </li> 
      <li id="li_E84D2439B59548E5B1803C64A295A18E">Insira a string desejada na caixa de texto. </li> 
     </ol> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Este exemplo usa dados coletados do tráfego do site para ilustrar o uso da variável [!DNL String Match] condição. A condição testa se o campo de entrada (cs-uri-stem) corresponde a qualquer uma das duas strings especificadas no parâmetro Matches e terá êxito se o campo cs-uri-stem for a string exata [!DNL /navigation/footer.asp] ou a string exata [!DNL /navigation/header.asp].

![](assets/cfg_Condition_StringMatch.png)
