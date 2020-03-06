---
description: O Insight Server Replication Service permite transmitir os dados de eventos coletados e armazenados em uma máquina do Insight Server para outra máquina do Insight Server.
solution: Insight
title: Instalação do serviço de replicação
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Instalação do serviço de replicação{#installing-the-replication-service}

O Insight Server Replication Service permite transmitir os dados de eventos coletados e armazenados em uma máquina do Insight Server para outra máquina do Insight Server.

Normalmente, a máquina na qual os dados são coletados e armazenados é configurada para ser executada como uma [!DNL Repeater] máquina. Consulte Funcionalidade [de repetição](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). O [!DNL Replication Service], que é configurado pelo [!DNL Replicate.cfg] arquivo, permite que uma [!DNL Insight Server] máquina recupere dados da [!DNL Repeater] máquina e armazene-os localmente. A [!DNL Insight Server] máquina é chamada de máquina de destino. Várias [!DNL Insight Server] DPUs podem se conectar a uma única [!DNL Repeater] para solicitar cópias dos dados do evento para inclusão em vários conjuntos de dados.

Você pode usar o em infraestruturas de rede com várias camadas de firewalls para obter comunicações de porta única para porta única entre componentes separados por firewalls. [!DNL Replication Service]

**Para instalar o[!DNL Replication Service]**

O [!DNL Replicate.cfg] arquivo deve ser instalado como parte da sua [!DNL Insight Server] instalação. Você pode encontrar o arquivo dentro da [!DNL Components] pasta do diretório de [!DNL Insight Server] instalação. Se você não tiver esse arquivo, entre em contato com a Adobe.
