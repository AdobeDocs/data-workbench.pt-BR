---
description: A funcionalidade de repetição permite que uma FSU do servidor Insight receba dados de evento adquiridos pelo sensor de uma ou mais fontes e replique os dados para uma ou mais FSUs do servidor Insight que executam o serviço de replicação do servidor Insight.
title: Configurar funcionalidade de repetição
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
exl-id: 61b70772-07fb-4963-b09f-6b2cf97b01a1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 9%

---

# Configurar funcionalidade de repetição{#configuring-repeater-functionality}

A funcionalidade de repetição permite que uma FSU do servidor Insight receba dados de evento adquiridos pelo sensor de uma ou mais fontes e replique os dados para uma ou mais FSUs do servidor Insight que executam o serviço de replicação do servidor Insight.

Consulte [Serviço de Replicação do Servidor Insight](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92). Esse recurso permite a replicação de dados para instalações redundantes para fins de recuperação de desastres. Os servidores de destino atuam como clientes de rede, conectando-se ao FSU de origem para solicitar cópias dos dados do evento para inclusão em vários conjuntos de dados.

Você pode usar a funcionalidade de repetidores em infraestruturas de rede com várias camadas de firewall para obter comunicações de porta única para porta única entre componentes separados por firewalls.

Para obter informações sobre os requisitos do sistema para instalar, configurar e operar [!DNL Repeater], consulte o documento *Requisitos mínimos do sistema*.

Para instalar [!DNL Repeater], você deve executar as etapas listadas para os dois procedimentos a seguir:

* [Configurar uma FSU do servidor Insight para repetidor](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [Configurar o controle de acesso para máquinas de direcionamento](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

Se os firewalls de rede permitirem acesso a seu [!DNL Repeater] a partir de [!DNL Insight], você poderá criar uma conexão conforme descrito em [Criação de uma conexão entre o Insight e o Repetidor](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118).
