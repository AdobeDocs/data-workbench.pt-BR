---
description: Os clientes do Insight Server (Relatório e Insight) usam nomes comuns para se referir aos Servidores Insight.
solution: Analytics
title: Definir o local de rede do servidor
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 4%

---


# Definir o local de rede do servidor{#defining-the-server-s-network-location}

Os clientes do Insight Server (Relatório e Insight) usam nomes comuns para se referir aos Servidores Insight.

Por exemplo, quando você se conecta [!DNL Insight] ou [!DNL Report] a um servidor, você o identifica pelo nome comum (por exemplo, [!DNL Insight Server][!DNL Server.MyCompany.com]). Internamente, o cliente resolve o nome comum para um endereço IP numérico antes de enviar uma solicitação ao servidor.

Para resolver nomes comuns para endereços IP, [!DNL Insight Server’s] os clientes usam um arquivo de pesquisa local chamado arquivo de endereço. O arquivo de endereço lista os nomes comuns dos [!DNL Insight Servers] instalados em sua organização e identifica seus endereços IP numéricos. Um cliente recebe automaticamente uma cópia do arquivo de endereço quando abre um perfil no [!DNL Insight Server].

Quando um cliente emite uma solicitação para um servidor, ele tenta [!DNL Insight Server]resolver o nome comum do servidor por meio do arquivo de endereço. Se o arquivo de endereço identificar um endereço IP para o servidor solicitado, o cliente encaminhará a solicitação para o endereço especificado. Se o endereço não estiver definido (por exemplo, o arquivo de endereço não define o nome comum do servidor), a solicitação falhará. Opcionalmente, você pode configurar clientes para resolver endereços por meio do mecanismo DNS (Domain Naming Service) normal do ambiente operacional se um nome não estiver definido no arquivo de endereço do cliente. Para obter instruções, consulte o parâmetro Pai na tabela [Parâmetros](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05) NetworkLocation na seção a seguir.
