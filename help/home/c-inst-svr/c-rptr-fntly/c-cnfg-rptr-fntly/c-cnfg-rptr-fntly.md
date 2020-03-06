---
description: A funcionalidade de repetição permite que um FSU do Insight Server receba dados de eventos adquiridos pelo sensor de uma ou mais fontes e replique os dados em um ou mais FSUs do Insight Server que executam o Insight Server Replication Service.
solution: Insight
title: Configuração da funcionalidade de repetição
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuração da funcionalidade de repetição{#configuring-repeater-functionality}

A funcionalidade de repetição permite que um FSU do Insight Server receba dados de eventos adquiridos pelo sensor de uma ou mais fontes e replique os dados em um ou mais FSUs do Insight Server que executam o Insight Server Replication Service.

Consulte Serviço [de Replicação do](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92)Insight Server. Esse recurso permite a replicação de dados para instalações redundantes para fins de recuperação de desastres. Os servidores de destino atuam como clientes de rede, conectando-se ao FSU de origem para solicitar cópias dos dados do evento para inclusão em vários conjuntos de dados.

Você pode usar a funcionalidade de repetidores em infraestruturas de rede com várias camadas de firewalls para obter comunicações de porta única para porta única entre componentes separados por firewalls.

Para obter informações sobre os requisitos do sistema para instalação, configuração e operação [!DNL Repeater], consulte o documento Requisitos ** mínimos do sistema.

Para instalar [!DNL Repeater], execute as etapas listadas para os dois procedimentos a seguir:

* [Configuração de um FSU do Insight Server para Repetidor](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [Configurando o controle de acesso para computadores de destino](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

Se os firewalls de rede permitirem acesso a sua [!DNL Repeater] partir de [!DNL Insight], você poderá criar uma conexão conforme descrito em [Criando uma conexão entre o Insight e o Repetidor](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118).
