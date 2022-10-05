---
description: A transformação REMatch é uma transformação de correspondência de padrões que usa expressões regulares para especificar um ou mais padrões para procurar e capturar na entrada.
title: REMatch
uuid: 8ef80bfa-aea2-45a1-a7d9-38ad33043886
exl-id: 571e6f1c-f557-49c3-9e7c-c31f06132ec7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 3%

---

# REMatch{#rematch}

{{eol}}

A transformação REMatch é uma transformação de correspondência de padrões que usa expressões regulares para especificar um ou mais padrões para procurar e capturar na entrada.

A transformação constrói um campo de saída para cada subpadrão de captura na expressão regular. Se a expressão regular não corresponder ao campo de entrada, as saídas ficarão em branco e, se o campo de saída já existir, os valores serão substituídos pelos valores em branco. Para obter um breve guia sobre o uso de expressões regulares, consulte [Expressões regulares](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

>[!NOTE]
>
>O [!DNL REMatch] a transformação funciona de forma semelhante à [!DNL RETransform] transformação (consulte [RETransform](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-retransform.md#concept-23f80aa0bc204565b337e5c4931f6a74)), que usa expressões regulares para capturar uma string e armazena essa string em um único campo de saída.

[!DNL REMatch] analisa uma string com mais eficiência do que vários [!DNL RETransform] transformações ou uma única [!DNL RETransform] transformação seguida de uma [!DNL Flatten] transformação. Consulte [Nivelar](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-flatten.md#concept-7acd351a6d2444bd960ca412ae3333ce).

<table id="table_7077578512B249E986BC79AE770CBD9A"> 
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
   <td colname="col2"> Nome descritivo da transformação. Você pode inserir qualquer nome aqui. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Diferenciação de maiúsculas e minúsculas </td> 
   <td colname="col2"> Verdadeiro ou falso. Especifica se a correspondência faz distinção entre maiúsculas e minúsculas. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Observações sobre a transformação. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição </td> 
   <td colname="col2"> Condições de aplicação desta transformação. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Expressão </td> 
   <td colname="col2"> A expressão regular usada para correspondência. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> O campo contra o qual a expressão regular é avaliada. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Saídas </td> 
   <td colname="col2"> <p>O nome da string de saída ou do vetor. No caso de vetores de string como entrada, os resultados também são vetores de string. </p> <p> Um campo de saída deve existir para cada subpadrão de captura na expressão. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!DNL REMatch] as transformações podem ser muito lentas e podem ser responsáveis por grande parte do tempo de processamento de dados.

Neste exemplo, um [!DNL REMatch] A transformação analisa uma data do formato AAAA-MM-DD nos campos x-ano, x-mês e x-dia. Para 2007-01-02, os valores de x-ano, x-mês e x-dia seriam 2007, 01 e 02, respectivamente.

![](assets/cfg_TransformationType_REMatch.png)
