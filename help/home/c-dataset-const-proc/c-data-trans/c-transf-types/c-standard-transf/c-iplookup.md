---
description: A transformação do IPLookup utiliza dados de geolocalização de IP ou de geolocalização de IP (fornecidos por qualquer fornecedor desses dados e convertidos em um formato proprietário pela Adobe) e transforma os dados em informações geográficas que podem ser usadas na análise.
solution: Analytics
title: IPLookup
topic: Data workbench
uuid: 6fccee39-761f-4854-a7fd-3f8b453e0698
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# IPLookup{#iplookup}

A transformação do IPLookup utiliza dados de geolocalização de IP ou de geolocalização de IP (fornecidos por qualquer fornecedor desses dados e convertidos em um formato proprietário pela Adobe) e transforma os dados em informações geográficas que podem ser usadas na análise.

Duas [!DNL IPLookup] transformações estão listadas no menu Adicionar novo > *Tipo de transformação *:

* [!DNL IPLookup] Quova para [!DNL IP geo-location] dados

* [!DNL IPLookup] Digital Envoy para [!DNL IP geo-intelligence] dados

Ao definir uma [!DNL IPLookup] transformação, escolha a transformação apropriada para seus [!DNL IP geo-location] ou [!DNL IP geo-intelligence] dados.

<table id="table_C438A30AB5E64160A5C486D6887B1D7E"> 
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
   <td colname="col1"> Arquivo </td> 
   <td colname="col2"> Caminho e nome do arquivo de pesquisa. Os caminhos relativos referem-se ao diretório de instalação do servidor de análise de big data. Normalmente, esse arquivo está localizado no diretório Pesquisas no diretório de instalação do servidor da análise de big data. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Endereço IP </td> 
   <td colname="col2"> O campo do qual ler o endereço IP. </td> 
   <td colname="col3"> c-ip </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Saídas </td> 
   <td colname="col2"> <p>Os nomes das strings de saída. </p> <p> As transformações do <span class="wintitle"> IPLookup</span> Quova e do <span class="wintitle"> IPLookup</span> Digital Envoy têm parâmetros de saída diferentes. Certifique-se de usar a transformação apropriada para seus dados de pesquisa de IP. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Neste exemplo, [!DNL IP geo-location] os dados (no arquivo de pesquisa [!DNL Quova.bin]) são usados para criar os campos de saída listados. As saídas (AOL, ASN, Código de área e assim por diante) podem ser usadas para criar dimensões para a análise geográfica do tráfego do visitante.

![](assets/cfg_TransformationType_IPLookup.png)

