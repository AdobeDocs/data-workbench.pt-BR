---
description: A transformação RETransform (expressão regular) é uma transformação de correspondência de padrões que usa expressões regulares para especificar um padrão para procurar e capturar na entrada e armazena a string capturada em um campo de saída designado.
solution: Analytics
title: RETransform
topic: Data workbench
uuid: 60b5b60e-678a-416d-b5c3-57b1bbefce7d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# RETransform{#retransform}

A transformação RETransform (expressão regular) é uma transformação de correspondência de padrões que usa expressões regulares para especificar um padrão para procurar e capturar na entrada e armazena a string capturada em um campo de saída designado.

As expressões regulares são avaliadas em relação a toda a string de entrada. Se a entrada não corresponder ao padrão especificado na expressão regular, nenhum dado será capturado. Para obter um breve guia sobre como usar expressões regulares, consulte Expressões [regulares](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

>[!NOTE]
>
>A [!DNL RETransform] transformação opera de forma semelhante à [!DNL REMatch] transformação (consulte [REMatch](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-rematch.md#concept-7f0b1caad1df46aabef4448f88261a8e)), que constrói um campo de saída para cada subpadrão de captura na expressão regular. Você pode pensar [!DNL RETransform] como uma combinação de [!DNL REMatch] e [!DNL Format] transformações. Se o parâmetro Ação (consulte Ação na tabela a seguir) estiver definido como &quot;RESULTADOS&quot;, então [!DNL RETransform] funcionará como uma combinação de [!DNL REMatch] e [!DNL Union] transformações.

<table id="table_51B7342E6A5E4E31913BD0F6A6ACC424"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Nome descritivo da transformação. Você pode digitar qualquer nome aqui. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Notas sobre a transformação. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição </td> 
   <td colname="col2"> As condições em que essa transformação é aplicada. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Padrão </td> 
   <td colname="col2"> O valor padrão a ser usado se a condição for cumprida e o valor de entrada não estiver disponível ou a expressão regular não corresponder ao valor de entrada. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ação </td> 
   <td colname="col2"> <p>Especifica como o resultado é tratado. A configuração padrão de RESULTADOS simplesmente aceita os padrões correspondentes e cria um vetor de sequências de caracteres dos padrões que estão sendo extraídos. </p> <p> Como alternativa, a ação pode ser uma string de formatação para criar uma saída de string simples de um formato específico. Com essa técnica, você especifica o número correspondente à localização de cada padrão correspondente entre os sinais de %. Por exemplo, o primeiro padrão correspondente seria %1%, e o terceiro padrão correspondente seria %3%. Você especificaria outros caracteres na string de formatação literalmente. </p> </td> 
   <td colname="col3"> RESULTADOS </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Expressão </td> 
   <td colname="col2"> A expressão regular usada para correspondência. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> O campo em relação ao qual a expressão regular é avaliada. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Saída </td> 
   <td colname="col2"> O nome da string de saída. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!DNL RETransform] as transformações podem ser muito lentas e podem ser responsáveis por grande parte do tempo de processamento de dados.

Este exemplo isola a versão do sistema operacional Windows que um visitante do site está usando e cria um campo x-windows-version a partir desse valor. O valor de saída nesse caso seria simplesmente o número da versão.

![](assets/cfg_TransformationType_RegularExpression.png)

Se você quiser incluir a string &quot;Version&quot; na frente do número da versão para leitura, altere o parâmetro Action de &quot;RESULTS&quot; para &quot;Version %1%&quot;. Para incluir um sinal de porcentagem (%) literal na saída, escape-o com um segundo sinal de porcentagem, como em &quot;%%&quot;.
