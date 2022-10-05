---
description: Para usar um cluster, você deve designar um servidor Insight no cluster para agir como o servidor Insight principal.
title: Instalar o servidor Insight principal
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# Instalar o servidor Insight principal{#installing-the-master-insight-server}

{{eol}}

Para usar um cluster, você deve designar um servidor Insight no cluster para agir como o servidor Insight principal.

Um componente cliente como [!DNL Insight] ou [!DNL Report] conecta-se ao principal [!DNL Insight Server] no início de uma sessão. Em pontos subsequentes durante a sessão, o cliente pode se conectar a outros [!DNL Insight Servers] no cluster para executar um query. Estas conexões subsequentes entre o cliente e o outro [!DNL Insight Servers] no cluster são intermediadas pelo principal [!DNL Insight Server] e sejam transparentes para o cliente.

Para além da intermediação de ligações entre um cliente e outros [!DNL Insight Servers] no cluster, o principal [!DNL Insight Server] atua como o ponto administrativo central de todo o cluster. Ao administrar um cluster, você atualiza o principal [!DNL Insight Server]. As alterações administrativas que você faz na principal [!DNL Insight Server] são recuperadas pela outra [!DNL Insight Servers] no cluster.

**Para instalar o principal[!DNL Insight Server]**

1. Determine qual máquina atuará como o principal [!DNL Insight Server].
1. Instalar e configurar [!DNL Insight Server] (normalmente, um [!DNL Insight Server] FSU) nesta máquina, conforme descrito em [Servidor Insight](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. Instalar [!DNL Insight] e configure uma conexão com o principal [!DNL Insight Server] conforme descrito no *[!DNL Insight]Guia do usuário*.
