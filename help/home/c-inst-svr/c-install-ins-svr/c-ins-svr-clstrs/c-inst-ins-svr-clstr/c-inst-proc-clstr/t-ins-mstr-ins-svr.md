---
description: Para usar um cluster, você deve designar um Servidor Insight no cluster para agir como o Servidor Insight principal.
solution: Analytics
title: Instalar o servidor Insight principal
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---


# Instalar o servidor Insight principal{#installing-the-master-insight-server}

Para usar um cluster, você deve designar um Servidor Insight no cluster para agir como o Servidor Insight principal.

Um componente cliente, como [!DNL Insight] ou [!DNL Report] , se conecta ao principal [!DNL Insight Server] no início de uma sessão. Em pontos subsequentes durante a sessão, o cliente pode se conectar a outros [!DNL Insight Servers] no cluster para executar um query. Essas conexões subsequentes entre o cliente e o outro [!DNL Insight Servers] no cluster são intermediadas pelo principal [!DNL Insight Server] e são transparentes para o cliente.

Além da intermediação de conexões entre um cliente e outro [!DNL Insight Servers] no cluster, o principal [!DNL Insight Server] atua como o ponto administrativo central de todo o cluster. Ao administrar um cluster, você atualiza o principal [!DNL Insight Server]. As alterações administrativas feitas no principal [!DNL Insight Server] são recuperadas pelo outro [!DNL Insight Servers] no cluster.

**Para instalar o principal[!DNL Insight Server]**

1. Determine qual computador atuará como o principal [!DNL Insight Server].
1. Instale e configure [!DNL Insight Server] (normalmente, um [!DNL Insight Server] FSU) neste computador, conforme descrito em [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. Instale [!DNL Insight] e configure uma conexão com a principal [!DNL Insight Server] conforme descrito no *[!DNL Insight]Guia* do Usuário.
