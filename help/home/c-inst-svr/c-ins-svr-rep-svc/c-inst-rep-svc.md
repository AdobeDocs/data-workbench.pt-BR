---
description: O serviço Insight ServerReplication permite que você transmita os dados do evento coletados e armazenados em uma máquina do Insight Server para outra máquina do Insight Server.
title: Instalar serviço de replicação
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---

# Instalar serviço de replicação{#installing-the-replication-service}

O serviço Insight ServerReplication permite que você transmita os dados do evento coletados e armazenados em uma máquina do Insight Server para outra máquina do Insight Server.

Normalmente, a máquina na qual os dados são coletados e armazenados é configurada para ser executada como uma máquina [!DNL Repeater]. Consulte [Funcionalidade de repetição](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). O [!DNL Replication Service], que é configurado pelo arquivo [!DNL Replicate.cfg], permite que uma máquina [!DNL Insight Server] recupere dados da máquina [!DNL Repeater] e armazene-os localmente. A máquina [!DNL Insight Server] é chamada de máquina de destino. Várias [!DNL Insight Server] DPUs podem se conectar a um único [!DNL Repeater] para solicitar cópias dos dados do evento para inclusão em vários conjuntos de dados.

Você pode usar o [!DNL Replication Service] em infraestruturas de rede com várias camadas de firewalls para obter comunicações de porta única para porta única entre componentes separados por firewalls.

**Para instalar o[!DNL Replication Service]**

O arquivo [!DNL Replicate.cfg] deve ser instalado como parte da instalação [!DNL Insight Server]. Você pode encontrar o arquivo na pasta [!DNL Components] do diretório de instalação [!DNL Insight Server]. Caso não tenha esse arquivo, entre em contato com o Adobe.
