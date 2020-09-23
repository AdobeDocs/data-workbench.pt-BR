---
description: Informações sobre a configuração geral do Sensor com uma instância de servidor da Web em execução em um servidor da Web.
solution: Analytics
title: Trabalhar com várias instâncias de um servidor da Web
uuid: 778ea95f-e0f2-4c2a-b7ed-7e323fea1e48
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---


# Trabalhar com várias instâncias de um servidor da Web{#working-with-multiple-instances-of-a-web-server}

Informações sobre a configuração geral do Sensor com uma instância de servidor da Web em execução em um servidor da Web.

![](assets/web_inst.png)

Nesse cenário, uma única instância do servidor da Web está gravando dados no arquivo de fila mapeado de memória, que é lido pelo transmissor e enviado para o [!DNL data workbench server].

Quando [!DNL Sensor] estiver instalado em um servidor da Web que esteja executando várias instâncias do coletor, você poderá configurá-lo de uma das duas maneiras:

* Você pode fazer com que todos os módulos do coletor compartilhem um arquivo de fila.

   Ao usar um único arquivo de fila, o gerenciamento, a configuração e a administração são simplificados porque a arquitetura em si é menos complexa. No entanto, com um único arquivo de fila, todo o servidor da Web, independentemente do número de instâncias, é identificado como WEB1.

* Você pode replicar a arquitetura acima várias vezes e ter cada instância do servidor da Web com um arquivo de fila separado.

   Isso permite que você identifique cada uma das instâncias do servidor da Web de forma exclusiva. Em outras palavras, a identificação do servidor da Web (e a SensorID correspondente na [!DNL Sensor] configuração) é uma função dessa configuração.

Em qualquer caso, os dados ainda têm todas as informações de nome do host para que você possa distinguir entre [!DNL www.client.com], [!DNL www2.client.com]e assim por diante. A configuração correta é determinada pelas metas de análise e se os analistas precisam segmentar os dados com base em uma instância específica executada em um servidor da Web.

>[!NOTE]
>
>Normalmente, esse tipo de segmentação é usado apenas na análise operacional e não oferece muito uso prático fora dessa área.

