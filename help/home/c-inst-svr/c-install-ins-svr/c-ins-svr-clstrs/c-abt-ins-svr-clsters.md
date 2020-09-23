---
description: Um cluster do Insight Server é necessário quando a quantidade de dados que você deseja processar e tornar acessível aos usuários do Insight e do Relatório excede a capacidade de um único Insight Server.
solution: Analytics
title: Sobre os clusters do servidor Insight
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---


# Sobre os clusters do servidor Insight{#about-insight-server-clusters}

Um cluster do Insight Server é necessário quando a quantidade de dados que você deseja processar e tornar acessível aos usuários do Insight e do Relatório excede a capacidade de um único Insight Server.

Ao configurar um [!DNL Insight Server] cluster, você pode distribuir um único conjunto de dados de análise por várias máquinas em um cluster para aproveitar a capacidade de processamento de várias [!DNL Insight Servers]máquinas.

A primeira etapa na implementação de um [!DNL Insight Server] cluster é alocar as [!DNL Insight Server] máquinas no cluster. A primeira [!DNL Insight Server] máquina configurada é a principal [!DNL Insight Server] (às vezes chamada de primária [!DNL Insight Server]).

>[!NOTE]
>
>Se você estiver usando uma unidade de servidor de [!DNL Insight Server] arquivos (FSU), o Adobe recomenda que você configure o FSU como principal [!DNL Insight Server]. Para obter informações sobre como configurar um FSU, consulte o Guia *de configuração de* conjuntos de dados.

O principal [!DNL Insight Server] gerencia a comunicação entre os outros [!DNL Insight Servers] no cluster (chamados servidores de processamento ou, às vezes, servidores de query) e instâncias de [!DNL Insight] e [!DNL Report]. Para um dado conjunto de dados, o processamento de arquivos de log ocorre no (um ou mais) designado [!DNL Insight Servers] (principal ou processando) conforme especificado nos arquivos de [!DNL Insight Server] configuração. Ao trabalhar em um ambiente clusterizado, [!DNL Insight] as instalações são configuradas para acessar o principal [!DNL Insight Server], mas os query podem ser manipulados por qualquer um dos [!DNL Insight Servers] dentro do cluster.

>[!NOTE]
>
>O arquivo **PAServer.cfg** . Se você quiser enviar trabalhos de cluster do Predictive Analytics para os Servidores Insight, será necessário configurar o [!DNL PAServer.cfg] arquivo para lidar com envios de cluster do lado do servidor. O perfil personalizado deve herdar o  [!DNL PAServer.cfg] do perfil Predictive Analytics ([!DNL Server\Profiles\Predictive Analytics\Dataset]). Defina um Servidor ** Principal neste arquivo e salve-o [!DNL PAServer.cfg] no site de implementação.
>
>
```
>PAServer = PAServerConfig: 
>   Master Server = serverInfo: 
>       Address = string: 
>       Port = int: 80
>       Use SSL = bool: false
>```

>[!IMPORTANT]
>
>As instruções deste capítulo não se aplicam à criação de um [!DNL Insight Server] cluster composto por mais de cinco (5) [!DNL Insight Servers]. Entre em contato com a Adobe para obter os requisitos do sistema e as recomendações de configuração do perfil para clusters maiores que cinco [!DNL Insight Servers].
