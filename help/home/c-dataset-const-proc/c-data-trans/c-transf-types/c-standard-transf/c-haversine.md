---
description: Em matemática, a fórmula do penteado é uma equação que dá distâncias de círculo entre dois pontos de uma esfera identificada de suas longitudes e latitudes.
title: Haversine
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
exl-id: e700c0a0-1a1a-4c56-bb4f-1deb1b39b059
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 4%

---

# Haversine{#haversine}

{{eol}}

Em matemática, a fórmula do penteado é uma equação que dá distâncias de círculo entre dois pontos de uma esfera identificada de suas longitudes e latitudes.

Como a fórmula, a variável [!DNL Haversine] a transformação requer dois conjuntos de [!DNL Latitude] e [!DNL Longitude] , utilizando estas quatro entradas para calcular a distância real entre duas localizações na Terra.

Essa distância pode ser representada como quilômetros ou milhas mudando o sinalizador &quot;Em Quilômetros&quot; de falso para verdadeiro.

![](assets/cfg_TransformationType_Haversine.png)

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode inserir qualquer nome aqui. |  |
| Comentários | Opcional. Observações sobre a transformação. |  |
| Condição | Condições de aplicação desta transformação. |  |
| Campo Latitude 1 | A latitude do ponto 1. |  |
| Campo Latitude 2 | A latitude do ponto 2. |  |
| Campo de longitude 1 | A longitude do ponto 1. |  |
| Campo Longitude 2 | A longitude do ponto 2. |  |
| Saída | Depois de calculada, a variável [!DNL Output] contém distâncias entre os pontos designados como elementos em um Dimension. |  |

Como exemplo, se você codificar em uma latitude e longitude de sua loja como Lat1, Lon1 e usar uma pesquisa de IP lat e long para seus clientes, as distâncias para uma loja da qual a maioria dos clientes compram ou vêm podem ser determinadas.

>[!NOTE]
>
>Se você quiser identificar distâncias para outros locais, cada local individual deve ter seu próprio conjunto de campos lat e lon.
