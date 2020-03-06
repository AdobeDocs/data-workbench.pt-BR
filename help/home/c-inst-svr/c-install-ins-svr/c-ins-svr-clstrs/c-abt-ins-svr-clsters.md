---
description: Um cluster do Insight Server é necessário quando a quantidade de dados que você deseja processar e tornar acessível aos usuários do Insight e do Relatório excede a capacidade de um único Insight Server.
solution: Insight
title: Sobre os clusters do Insight Server
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sobre os clusters do Insight Server{#about-insight-server-clusters}

Um cluster do Insight Server é necessário quando a quantidade de dados que você deseja processar e tornar acessível aos usuários do Insight e do Relatório excede a capacidade de um único Insight Server.

Ao configurar um [!DNL Insight Server] cluster, você pode distribuir um único conjunto de dados de análise por várias máquinas em um cluster para aproveitar a potência de processamento de várias [!DNL Insight Servers]máquinas.

A primeira etapa na implementação de um [!DNL Insight Server] cluster é alocar as [!DNL Insight Server] máquinas no cluster. A primeira [!DNL Insight Server] máquina que você configurou é sua máquina mestre [!DNL Insight Server] (às vezes chamada de primária [!DNL Insight Server]).

>[!NOTE]
>
>Se você estiver usando uma unidade de servidor de [!DNL Insight Server] arquivos (FSU), a Adobe recomenda que você configure o FSU como seu mestre [!DNL Insight Server]. Para obter informações sobre como configurar um FSU, consulte o Guia *de configuração de* conjuntos de dados.

O mestre [!DNL Insight Server] gerencia a comunicação entre o outro [!DNL Insight Servers] no cluster (chamado de servidores de processamento ou, às vezes, servidores de consulta) e instâncias de [!DNL Insight] e [!DNL Report]. Para um dado conjunto de dados, o processamento de arquivos de log ocorre no (um ou mais) designado [!DNL Insight Servers] (mestre ou processamento) conforme especificado nos arquivos de [!DNL Insight Server] configuração. Ao trabalhar em um ambiente clusterizado, [!DNL Insight] as instalações são configuradas para acessar o mestre [!DNL Insight Server], mas as consultas podem ser tratadas por qualquer um dos [!DNL Insight Servers] membros do cluster.

>[!NOTE]
>
>O arquivo **PAServer.cfg** . Se você quiser enviar trabalhos de cluster do Predictive Analytics para os Servidores Insight, será necessário configurar o [!DNL PAServer.cfg] arquivo para lidar com envios de cluster do lado do servidor. O perfil personalizado deve herdar o perfil [!DNL PAServer.cfg] do Predictive Analytics ( [!DNL Server\Profiles\Predictive Analytics\Dataset]). Defina um servidor ** mestre neste arquivo e salve-o [!DNL PAServer.cfg] no site de implementação. >
>
```>
>PAServer = PAServerConfig: 
>   Master Server = serverInfo: 
>       Address = string: 
>       Port = int: 80
>       Use SSL = bool: false
>```>



>[!IMPORTANT]
>
>As instruções deste capítulo não se aplicam à criação de um [!DNL Insight Server] cluster composto por mais de cinco (5) [!DNL Insight Servers]. Entre em contato com a Adobe para obter os requisitos do sistema e as recomendações de configuração de perfil para clusters maiores que cinco [!DNL Insight Servers].

