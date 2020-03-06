---
description: Para usar um cluster, você deve designar um Servidor Insight no cluster para agir como o Servidor Insight mestre.
solution: Insight
title: Instalação do Master Insight Server
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Instalação do Master Insight Server{#installing-the-master-insight-server}

Para usar um cluster, você deve designar um Servidor Insight no cluster para agir como o Servidor Insight mestre.

Um componente do cliente, como [!DNL Insight] ou [!DNL Report] , se conecta ao mestre [!DNL Insight Server] no início de uma sessão. Em pontos subsequentes durante a sessão, o cliente pode se conectar a outros [!DNL Insight Servers] no cluster para executar uma consulta. Essas conexões subsequentes entre o cliente e o outro [!DNL Insight Servers] no cluster são intermediadas pelo mestre [!DNL Insight Server] e são transparentes para o cliente.

Além da intermediação de conexões entre um cliente e outro [!DNL Insight Servers] no cluster, o mestre [!DNL Insight Server] atua como o ponto administrativo central de todo o cluster. Ao administrar um cluster, você atualiza o mestre [!DNL Insight Server]. As alterações administrativas feitas no mestre [!DNL Insight Server] são recuperadas pela outra [!DNL Insight Servers] no cluster.

**Para instalar o mestre[!DNL Insight Server]**

1. Determine qual máquina atuará como mestre [!DNL Insight Server].
1. Instale e configure [!DNL Insight Server] (normalmente, um [!DNL Insight Server] FSU) neste computador, conforme descrito em [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. Instale [!DNL Insight] e configure uma conexão com o mestre [!DNL Insight Server] conforme descrito no *[!DNL Insight]Guia *do Usuário.
