---
description: As instruções para instalar uma FSU do servidor Insight e configurá-la para uso administrativo são muito semelhantes àquelas para instalar e configurar uma DPU do servidor Insight.
title: Procedimentos de instalação para uma FSU do servidor Insight
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---

# Procedimentos de instalação para uma FSU do servidor Insight{#installation-procedures-for-an-insight-server-fsu}

As instruções para instalar uma FSU do servidor Insight e configurá-la para uso administrativo são muito semelhantes àquelas para instalar e configurar uma DPU do servidor Insight.

Para *MS System Center Endpoint Protection* em servidores Windows 2012, esses executáveis precisam ser adicionados ao **Processos excluídos:**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

Para instalar e configurar uma FSU [!DNL Insight Server], você deve concluir as seguintes tarefas:

1. Instale os arquivos do programa [!DNL Insight Server].
1. Instale o certificado digital [!DNL Insight Server].
1. Verifique as configurações da porta no arquivo [!DNL Communications.cfg].
1. Modifique o arquivo [!DNL Access Control.cfg] para permitir acesso administrativo a [!DNL the Server] de [!DNL the Client].
1. Modifique o arquivo [!DNL server.address] para definir o local de rede do servidor.
1. Defina os parâmetros de utilização da memória do Windows conforme descrito.
1. Registre [!DNL Insight Server] como um serviço do Windows conforme descrito.

   Para obter instruções sobre como configurar fontes de dados, permissões e comunicações para uma FSU [!DNL Insight Server], consulte o *Guia de Configuração do Conjunto de Dados*.
