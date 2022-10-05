---
description: Um cluster do Servidor Insight é necessário quando a quantidade de dados que você deseja processar e tornar acessível aos usuários do Insight e do Relatório excede a capacidade de um único Servidor Insight.
title: Sobre os clusters do servidor Insight
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---

# Sobre os clusters do servidor Insight{#about-insight-server-clusters}

{{eol}}

Um cluster do Servidor Insight é necessário quando a quantidade de dados que você deseja processar e tornar acessível aos usuários do Insight e do Relatório excede a capacidade de um único Servidor Insight.

Ao configurar um [!DNL Insight Server] cluster, você pode distribuir um único conjunto de dados de análise em várias máquinas em um cluster para aproveitar o poder de processamento de várias [!DNL Insight Servers].

O primeiro passo na implementação de um [!DNL Insight Server] o cluster é alocar o [!DNL Insight Server] computadores no cluster. O primeiro [!DNL Insight Server] a máquina que você configurou é a sua principal [!DNL Insight Server] (às vezes chamada de principal [!DNL Insight Server]).

>[!NOTE]
>
>Se estiver usando um [!DNL Insight Server] Unidade de servidor de arquivos (FSU), o Adobe recomenda que você configure a FSU como sua unidade principal [!DNL Insight Server]. Para obter informações sobre como configurar uma FSU, consulte o *Guia de configuração do conjunto de dados*.

O principal [!DNL Insight Server] gerencia a comunicação entre os outros [!DNL Insight Servers] no cluster (chamado de servidores de processamento ou, às vezes, servidores de query) e instâncias de [!DNL Insight] e [!DNL Report]. Para um determinado conjunto de dados, o processamento do arquivo de log ocorre no (um ou mais) designado [!DNL Insight Servers] (principal ou de transformação), conforme especificado no [!DNL Insight Server] arquivos de configuração. Ao trabalhar em um ambiente em cluster, [!DNL Insight] as instalações estão configuradas para acessar o principal [!DNL Insight Server], mas as consultas podem ser tratadas por qualquer um dos [!DNL Insight Servers] no cluster.

>[!NOTE]
>
>O **PAServer.cfg** arquivo. Se você quiser enviar trabalhos de cluster do Predictive Analytics para os servidores Insight, será necessário configurar o [!DNL PAServer.cfg] para lidar com envios de cluster do lado do servidor. O perfil personalizado deve herdar a variável [!DNL PAServer.cfg] no perfil do Predictive Analytics ([!DNL Server\Profiles\Predictive Analytics\Dataset]). Defina um *Servidor principal* neste arquivo e salve o [!DNL PAServer.cfg] ao local de implementação.
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
>As instruções deste capítulo não se aplicam à criação de um [!DNL Insight Server] cluster constituído por mais de cinco (5) [!DNL Insight Servers]. Entre em contato com o Adobe para obter os requisitos do sistema e as recomendações de configuração de perfil para clusters maiores que cinco [!DNL Insight Servers].
