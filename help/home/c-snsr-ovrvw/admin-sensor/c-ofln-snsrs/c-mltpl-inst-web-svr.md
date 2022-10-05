---
description: Informações sobre a configuração geral do Sensor com uma instância do servidor da Web em execução em um servidor da Web.
title: Trabalhar com várias instâncias de um servidor da Web
uuid: 778ea95f-e0f2-4c2a-b7ed-7e323fea1e48
exl-id: a371f9ed-6c27-4b3d-843f-ae5621013410
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---

# Trabalhar com várias instâncias de um servidor da Web{#working-with-multiple-instances-of-a-web-server}

{{eol}}

Informações sobre a configuração geral do Sensor com uma instância do servidor da Web em execução em um servidor da Web.

![](assets/web_inst.png)

Nesse cenário, uma única instância do servidor da Web está gravando dados no arquivo de fila mapeado de memória, que é lido pelo transmissor e enviado para o [!DNL data workbench server].

When [!DNL Sensor] for instalado em um servidor da Web que esteja executando várias instâncias do coletor, você poderá configurá-lo de uma das duas formas a seguir:

* Você pode fazer com que todos os módulos coletores compartilhem um arquivo de fila.

   Ao usar um único arquivo de fila, o gerenciamento, a configuração e a administração são algo simplificado, pois a arquitetura em si é menos complexa. No entanto, com um único arquivo de fila, todo o servidor da Web, independentemente do número de instâncias, é identificado como WEB1.

* Você pode replicar a arquitetura acima várias vezes e fazer com que cada instância do servidor da Web tenha um arquivo de fila separado.

   Isso permite identificar cada uma das instâncias do servidor da Web de forma exclusiva. Em outras palavras, a identificação do servidor da Web (e a SensorID correspondente no [!DNL Sensor] configuração) é uma função dessa configuração.

Em qualquer caso, os dados ainda têm todas as informações do nome do host para que você possa distinguir entre [!DNL www.client.com], [!DNL www2.client.com]e assim por diante. A configuração correta é determinada pelas metas de análise e se os analistas precisam segmentar os dados com base em uma instância específica em execução em um servidor da Web.

>[!NOTE]
>
>Normalmente, esse tipo de segmentação é usado apenas em análises operacionais e não oferece muito uso prático fora dessa área.
