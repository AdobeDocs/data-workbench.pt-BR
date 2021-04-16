---
description: Um cluster do Servidor Insight é necessário quando a quantidade de dados que você deseja processar e tornar acessível aos usuários do Insight e do Relatório excede a capacidade de um único Servidor Insight.
title: Sobre os clusters do servidor Insight
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---

# Sobre os clusters do servidor Insight{#about-insight-server-clusters}

Um cluster do Servidor Insight é necessário quando a quantidade de dados que você deseja processar e tornar acessível aos usuários do Insight e do Relatório excede a capacidade de um único Servidor Insight.

Ao configurar um cluster [!DNL Insight Server], é possível distribuir um único conjunto de dados de análise em várias máquinas em um cluster para aproveitar o poder de processamento de vários [!DNL Insight Servers].

A primeira etapa na implementação de um cluster [!DNL Insight Server] é alocar as máquinas [!DNL Insight Server] em seu cluster. A primeira máquina [!DNL Insight Server] que você configurou é seu [!DNL Insight Server] principal (às vezes chamado de [!DNL Insight Server] principal).

>[!NOTE]
>
>Se você estiver usando uma [!DNL Insight Server] Unidade de Servidor de Arquivos (FSU), o Adobe recomenda que você configure a FSU como seu [!DNL Insight Server] principal. Para obter informações sobre como configurar uma FSU, consulte o *Guia de Configuração de Conjunto de Dados*.

O principal [!DNL Insight Server] gerencia a comunicação entre o outro [!DNL Insight Servers] no cluster (chamado de servidores de processamento ou, às vezes, servidores de query) e as instâncias de [!DNL Insight] e [!DNL Report]. Para um determinado conjunto de dados, o processamento do arquivo de log ocorre no (um ou mais) designado [!DNL Insight Servers] (principal ou processando), conforme especificado nos arquivos de configuração [!DNL Insight Server]. Ao trabalhar em um ambiente em cluster, [!DNL Insight] as instalações são configuradas para acessar o [!DNL Insight Server] principal, mas as consultas podem ser tratadas por qualquer um dos [!DNL Insight Servers] no cluster.

>[!NOTE]
>
>O arquivo **PAServer.cfg**. Se você quiser enviar trabalhos de cluster do Predictive Analytics para os Servidores Insight, será necessário configurar o arquivo [!DNL PAServer.cfg] para lidar com envios de cluster do lado do servidor. O perfil personalizado deve herdar o [!DNL PAServer.cfg] do perfil de Análise preditiva ([!DNL Server\Profiles\Predictive Analytics\Dataset]). Defina um *Servidor Principal* neste arquivo e salve o [!DNL PAServer.cfg] no site de implementação.
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
>As instruções deste capítulo não se aplicam à criação de um cluster [!DNL Insight Server] composto por mais de cinco (5) [!DNL Insight Servers]. Entre em contato com o Adobe para obter os requisitos do sistema e as recomendações de configuração de perfil para clusters maiores que cinco [!DNL Insight Servers].
