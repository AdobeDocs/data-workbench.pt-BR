---
description: Em matemática, a fórmula da haversina é uma equação que dá distâncias circulares entre dois pontos em uma esfera identificada de suas longitudes e latitudes.
solution: Analytics
title: Haversine
topic: Data workbench
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Haversine{#haversine}

Em matemática, a fórmula da haversina é uma equação que dá distâncias circulares entre dois pontos em uma esfera identificada de suas longitudes e latitudes.

Como a fórmula, a [!DNL Haversine] transformação requer dois conjuntos de [!DNL Latitude] e [!DNL Longitude] configurações, usando essas quatro entradas para calcular a distância real através da Terra entre dois locais.

Esta distância pode ser representada como milhas ou quilômetros mudando a bandeira &quot;Em Quilômetros&quot; de false para true.

![](assets/cfg_TransformationType_Haversine.png)

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode digitar qualquer nome aqui. |  |
| Comentários | Opcional. Notas sobre a transformação. |  |
| Condição | As condições em que essa transformação é aplicada. |  |
| Campo Latitude 1 | A latitude do ponto 1. |  |
| Campo Latitude 2 | A latitude do ponto 2. |  |
| Campo Longitude 1 | A longitude do ponto 1. |  |
| Campo Longitude 2 | A longitude do ponto 2. |  |
| Saída | Depois de calculado, o [!DNL Output] campo contém distâncias entre os pontos designados como elementos em uma Dimensão. |  |

Por exemplo, se você codificar em uma latitude e longitude de sua loja como Lat1, Lon1 e usar uma pesquisa de IP longa e longa para seus clientes, as distâncias para uma loja da qual a maioria dos clientes compra ou vem podem ser determinadas.

>[!NOTE]
>
>Se você quiser identificar distâncias para outros locais, cada local individual deve ter seu próprio conjunto de campos lat e long.

