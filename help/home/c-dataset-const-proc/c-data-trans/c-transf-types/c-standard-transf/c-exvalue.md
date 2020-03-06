---
description: Se você estiver trabalhando com dados da Web, poderá usar a transformação ExtractValue para extrair um valor de uma string de consulta, cookie ou campo codificado de forma semelhante nos dados do site.
solution: Analytics
title: ExtractValue
topic: Data workbench
uuid: 305827a2-04e6-421f-82cb-923d62b02e70
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ExtractValue{#extractvalue}

Se você estiver trabalhando com dados da Web, poderá usar a transformação ExtractValue para extrair um valor de uma string de consulta, cookie ou campo codificado de forma semelhante nos dados do site.

Observe que os nomes correspondentes ao valor a ser extraído podem ser diferentes em cada entrada de log.

<table id="table_D16A39BE035043628A4D6F7452952304"> 
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
   <td colname="col1"> Nome de entrada </td> 
   <td colname="col2"> <p>Os nomes dos campos a serem extraídos da Consulta de Entrada. </p> <p> <p>Observação:  Se o Nome de entrada for um vetor (ou seja, há vários nomes presentes), somente um valor será extraído. </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Consulta de entrada </td> 
   <td colname="col2"> O mapeamento codificado (string de consulta, cookie e assim por diante) a partir do qual o valor deve ser extraído. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valor de saída </td> 
   <td colname="col2"> O nome do campo usado para capturar o valor decodificado extraído. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

Se você quiser extrair uma frase de pesquisa, poderá extrair a frase inteira e, se desejado, dividir a frase em termos de pesquisa usando uma [!DNL Tokenize] transformação. Para obter informações sobre a [!DNL Tokenize] transformação, consulte [Tokenize](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-tokenize.md#concept-f460aa5df3a7476e971af29cf5d9b32c).

Este exemplo configura uma [!DNL ExtractValue] transformação para extrair valores do campo x-v-search-querynames de cs(referrer-query) e armazená-los no campo x-search-frase.

![](assets/cfg_TransformationType_ExtractValue.png)

