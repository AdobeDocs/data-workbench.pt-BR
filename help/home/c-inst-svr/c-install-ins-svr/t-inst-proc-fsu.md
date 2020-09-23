---
description: As instruções para instalar um FSU do Insight Server e configurá-lo para uso administrativo são muito semelhantes às instruções para instalar e configurar uma DPU do Insight Server.
solution: Analytics
title: Procedimentos de instalação para uma FSU do servidor Insight
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---


# Procedimentos de instalação para uma FSU do servidor Insight{#installation-procedures-for-an-insight-server-fsu}

As instruções para instalar um FSU do Insight Server e configurá-lo para uso administrativo são muito semelhantes às instruções para instalar e configurar uma DPU do Insight Server.

Para o *MS System Center Endpoint Protection* nos servidores Windows 2012, esses executáveis precisam ser adicionados aos processos **excluídos:**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

Para instalar e configurar um [!DNL Insight Server] FSU, você deve concluir as seguintes tarefas:

1. Instale os arquivos do [!DNL Insight Server] programa.
1. Instale o certificado [!DNL Insight Server] digital.
1. Verifique as configurações de porta no [!DNL Communications.cfg] arquivo.
1. Modifique o [!DNL Access Control.cfg] arquivo para permitir acesso administrativo a [!DNL the Server] partir de [!DNL the Client].
1. Modifique o [!DNL server.address] arquivo para definir o local de rede do servidor.
1. Defina os parâmetros de utilização da memória do Windows conforme descrito.
1. Registre-se [!DNL Insight Server] como um serviço do Windows, conforme descrito.

   Para obter instruções sobre como configurar fontes de dados, permissões e comunicações para um [!DNL Insight Server] FSU, consulte o Guia *de Configuração de* Conjunto de Dados.

