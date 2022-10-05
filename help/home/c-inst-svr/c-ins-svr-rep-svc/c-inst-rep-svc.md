---
description: O serviço Insight ServerReplication permite que você transmita os dados do evento coletados e armazenados em uma máquina do Insight Server para outra máquina do Insight Server.
title: Instalar serviço de replicação
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---

# Instalar serviço de replicação{#installing-the-replication-service}

{{eol}}

O serviço Insight ServerReplication permite que você transmita os dados do evento coletados e armazenados em uma máquina do Insight Server para outra máquina do Insight Server.

Normalmente, a máquina na qual os dados são coletados e armazenados é configurada para ser executada como uma [!DNL Repeater] máquina. Consulte [Funcionalidade de repetição](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). O [!DNL Replication Service], que é configurado pelo [!DNL Replicate.cfg] , ativa um [!DNL Insight Server] máquina para recuperar dados do [!DNL Repeater] e armazená-lo localmente. O [!DNL Insight Server] máquina é chamada de máquina alvo. Vários [!DNL Insight Server] As DPUs podem se conectar a um único [!DNL Repeater] para solicitar cópias dos dados do evento para inclusão em vários conjuntos de dados.

Você pode usar o [!DNL Replication Service] em infraestruturas de rede com várias camadas de firewalls para obter comunicações de porta única para porta única entre componentes separados por firewalls.

**Para instalar o[!DNL Replication Service]**

O [!DNL Replicate.cfg] O arquivo deve ser instalado como parte de seu [!DNL Insight Server] instalação. Você pode encontrar o arquivo na variável [!DNL Components] pasta da sua [!DNL Insight Server] diretório de instalação. Caso não tenha esse arquivo, entre em contato com o Adobe.
