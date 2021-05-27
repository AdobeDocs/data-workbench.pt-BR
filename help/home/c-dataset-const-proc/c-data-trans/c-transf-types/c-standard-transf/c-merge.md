---
description: A transformação Merge pega os valores do campo de entrada (normalmente um vetor de strings), os combina em uma única string separada pelo delimitador especificado e coloca a string resultante no campo de saída especificado.
title: Mesclar
uuid: 9ca2ab22-d854-47b0-8189-f563c1e83d1c
exl-id: 75fa824b-f68d-4ec4-a75d-0f742a7bb1ba
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 4%

---

# Mesclar{#merge}

A transformação Merge pega os valores do campo de entrada (normalmente um vetor de strings), os combina em uma única string separada pelo delimitador especificado e coloca a string resultante no campo de saída especificado.

<table id="table_2458E008C9A14B31A774E6819D07E9BE"> 
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
   <td colname="col1"> Padrão </td> 
   <td colname="col2"> O valor padrão a ser usado se a condição for atendida e o valor de entrada não estiver disponível. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Delimitador </td> 
   <td colname="col2"> <p>Sequência de caracteres usada para separar os elementos individuais do vetor da cadeia de caracteres de entrada na cadeia de caracteres de saída única. </p> <p> Se você pressionar a tecla Ctrl e clicar com o botão direito do mouse no parâmetro Delimitador, um menu <span class="wintitle"> Inserir</span> é exibido. Esse menu contém uma lista de caracteres especiais que geralmente são usados como delimitadores. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> Um vetor de valores de string que são combinados para formar a string de saída. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Saída </td> 
   <td colname="col2"> O nome da string de saída. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

Neste exemplo, um vetor de entrada de cadeias de caracteres é considerado como contendo um conjunto de produtos que foram selecionados para compra. Esses produtos são colocados em uma única string de saída e são separados por &quot;::&quot; (dois pontos).

![](assets/cfg_TransformationType_Merge.png)

Portanto, se o campo de entrada x-products contivesse os valores de string B57481, C46355 e Z97123, a string de saída resultante x-show-products seria B57481::C46355::Z97123.
