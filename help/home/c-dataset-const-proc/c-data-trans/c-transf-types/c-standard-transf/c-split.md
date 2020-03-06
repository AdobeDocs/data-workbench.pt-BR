---
description: A transformação Dividir divide uma string em um vetor de subsequências com base em um caractere delimitador específico.
solution: Analytics
title: Dividir
topic: Data workbench
uuid: 116e8465-8fb1-41eb-9a28-412cee54ab87
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Split{#split}

A transformação Dividir divide uma string em um vetor de subsequências com base em um caractere delimitador específico.

[!DNL Split] é especialmente útil para extrair valores individuais de uma coleção de valores associados a um único valor de nome de consulta URI.

<table id="table_C97DA4E45DA844FAB8D61AABA22FF809"> 
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
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Notas sobre a transformação. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição </td> 
   <td colname="col2"> As condições em que essa transformação é aplicada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Delimitador </td> 
   <td colname="col2"> <p>String usada para separar a string de entrada em subsequências. Deve ter um único caractere de comprimento. </p> <p> Se você mantiver pressionada a tecla Ctrl e clicar com o botão direito do mouse no parâmetro Delimitador, um menu Inserir será exibido. Esse menu contém uma lista de caracteres especiais que são usados com frequência como delimitadores. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> O nome do campo cujo valor é dividido para criar o vetor da string de saída. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Saída </td> 
   <td colname="col2"> O nome do campo de saída. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Considere um site no qual os produtos comprados por um cliente são listados como parte do valor de consulta cs-uri quando a página de confirmação associada a uma compra bem-sucedida é acessada. A seguir está um exemplo de tal string:

* /checkout/confirmed.asp?prod_seleted=B57481,C46355,Z97123

O campo cs-uri-stem é usado para determinar se a página que está sendo solicitada pela entrada do registro é a página de confirmação. Os códigos dos produtos que o cliente comprou são listados como valores separados por vírgulas do nome prod_seleted na consulta cs-uri. A [!DNL Split] transformação pode ser usada para extrair essas informações dividindo os códigos do produto na vírgula se o valor de cs-uri-stem corresponder ao valor especificado na [!DNL String Match] condição. Consulte Correspondência [de string](../../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-f8d132085c6b4500bfbe4515b848142f). A transformação a seguir detalha a solução para esse problema.

![](assets/cfg_TransformationType_Split.png)

Aqui, o campo de saída é x-products, que seria usado para criar a dimensão estendida desejada que mapeia os produtos comprados para as sessões durante as quais a compra foi realizada.
