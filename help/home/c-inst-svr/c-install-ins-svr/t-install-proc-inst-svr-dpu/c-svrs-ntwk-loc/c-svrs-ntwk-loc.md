---
description: Os clientes do servidor Insight (Relatório e Insight) usam nomes comuns para se referirem aos servidores Insight.
title: Definir o local de rede do servidor
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
exl-id: def360b8-f146-45ca-ae61-fd213adef68b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 4%

---

# Definir o local de rede do servidor{#defining-the-server-s-network-location}

Os clientes do servidor Insight (Relatório e Insight) usam nomes comuns para se referirem aos servidores Insight.

Por exemplo, ao conectar [!DNL Insight] ou [!DNL Report] a um [!DNL Insight Server], você identifica o servidor pelo seu nome comum (por exemplo, [!DNL Server.MyCompany.com]). Internamente, o cliente resolve o nome comum para um endereço IP numérico antes de enviar uma solicitação ao servidor.

Para resolver nomes comuns para endereços IP, os clientes [!DNL Insight Server’s] usam um arquivo de pesquisa local chamado arquivo de endereço. O arquivo de endereço lista os nomes comuns de [!DNL Insight Servers] instalados em sua organização e identifica seus endereços IP numéricos. Um cliente recebe automaticamente uma cópia do arquivo de endereço quando abre um perfil no [!DNL Insight Server].

Quando um cliente emite uma solicitação para um [!DNL Insight Server], ele tenta resolver o nome comum do servidor por meio do arquivo de endereço. Se o arquivo de endereço identificar um endereço IP para o servidor solicitado, o cliente encaminhará a solicitação para o endereço especificado. Se o endereço não estiver definido (por exemplo, o arquivo de endereço não define o nome comum do servidor), a solicitação falhará. Como opção, você pode configurar clientes para resolver endereços por meio do mecanismo DNS (Domain Naming Service) normal do ambiente operacional, se um nome não estiver definido no arquivo de endereço do cliente. Para obter instruções, consulte o parâmetro Pai na tabela [Parâmetros de NetworkLocation](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05) na seção a seguir.
