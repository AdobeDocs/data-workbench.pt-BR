---
description: As instruções para instalar uma FSU do servidor Insight e configurá-la para uso administrativo são muito semelhantes àquelas para instalar e configurar uma DPU do servidor Insight.
title: Procedimentos de instalação para uma FSU do servidor Insight
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---

# Procedimentos de instalação para uma FSU do servidor Insight{#installation-procedures-for-an-insight-server-fsu}

{{eol}}

As instruções para instalar uma FSU do servidor Insight e configurá-la para uso administrativo são muito semelhantes àquelas para instalar e configurar uma DPU do servidor Insight.

Para *Proteção do Ponto Final do Centro de Sistemas da MS* em servidores Windows 2012, esses executáveis precisam ser adicionados ao **Processos excluídos:**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

Para instalar e configurar um [!DNL Insight Server] FSU, você deve concluir as seguintes tarefas:

1. Instale o [!DNL Insight Server] arquivos de programa.
1. Instale o [!DNL Insight Server] certificado digital.
1. Verifique as configurações da porta no [!DNL Communications.cfg] arquivo.
1. Modifique o [!DNL Access Control.cfg] para permitir acesso administrativo ao [!DNL the Server] from [!DNL the Client].
1. Modifique o [!DNL server.address] para definir o local de rede do servidor.
1. Defina os parâmetros de utilização da memória do Windows conforme descrito.
1. Registrar [!DNL Insight Server] como um serviço do Windows, conforme descrito.

   Para obter instruções sobre como configurar fontes de dados, permissões e comunicações para um [!DNL Insight Server] FSU, consulte o *Guia de configuração do conjunto de dados*.
