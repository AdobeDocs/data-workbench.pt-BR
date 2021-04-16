---
description: Para usar um cluster, você deve designar um servidor Insight no cluster para agir como o servidor Insight principal.
title: Instalar o servidor Insight principal
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# Instalar o servidor Insight principal{#installing-the-master-insight-server}

Para usar um cluster, você deve designar um servidor Insight no cluster para agir como o servidor Insight principal.

Um componente cliente, como [!DNL Insight] ou [!DNL Report], conecta-se ao [!DNL Insight Server] principal no início de uma sessão. Em pontos subsequentes durante a sessão, o cliente pode se conectar a outro [!DNL Insight Servers] no cluster para executar uma consulta. Essas conexões subsequentes entre o cliente e o outro [!DNL Insight Servers] no cluster são intermediadas pelo principal [!DNL Insight Server] e são transparentes para o cliente.

Além de intermediar conexões entre um cliente e outro [!DNL Insight Servers] no cluster, o [!DNL Insight Server] principal atua como o ponto administrativo central de todo o cluster. Ao administrar um cluster, você atualiza o [!DNL Insight Server] principal. As alterações administrativas feitas no [!DNL Insight Server] principal são recuperadas pelo outro [!DNL Insight Servers] no cluster.

**Para instalar o principal[!DNL Insight Server]**

1. Determine qual máquina atuará como o [!DNL Insight Server] principal.
1. Instale e configure [!DNL Insight Server] (normalmente, um [!DNL Insight Server] FSU) nesta máquina, conforme descrito em [Servidor Insight](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. Instale [!DNL Insight] e configure uma conexão para o [!DNL Insight Server] principal, conforme descrito no *[!DNL Insight]Guia do Usuário*.
