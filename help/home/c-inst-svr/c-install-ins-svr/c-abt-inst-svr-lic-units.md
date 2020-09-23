---
description: O Insight Server está disponível em dois tipos de licença.
solution: Analytics
title: Sobre as unidades de licença do servidor Insight
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 7%

---


# Sobre as unidades de licença do servidor Insight{#about-insight-server-license-units}

O Insight Server está disponível em dois tipos de licença.

Estes são os dois tipos de licença:

* [Unidade de processamento de dados (DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [Unidade de servidor de arquivos (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## Unidade de processamento de dados (DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

Esse tipo de [!DNL Insight Server] pode processar, armazenar e fornecer dados de um conjunto de dados de Adobe. It optionally can store the log files that contain the source data from which the dataset is constructed, or it can receive that data from an [!DNL Insight Server] File Server Unit (FSU). Uma DPU é o tipo de [!DNL Insight Server] interação direta entre [!DNL Insight] e [!DNL Report] clientes.

Se você estiver instalando uma [!DNL Insight Server] DPU, consulte Procedimentos [de instalação para uma DPU](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc)do Insight Server.

## Unidade de servidor de arquivos (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

Esse tipo de servidor é configurado para receber e armazenar dados do evento de uma ou mais instâncias de replicação de dados do evento [!DNL Sensor] ( [!DNL Repeater] funcionalidade fornecida com uma licença de uso especial) e transmitir os dados para uma ou mais Unidades de processamento de [!DNL Insight Server] dados (DPUs) para a construção de conjuntos de dados do Adobe. As DPUs se comunicam com um FSU usando um protocolo que otimiza a transferência de dados do evento para a DPU e é significativamente mais rápido do que manter arquivos de registro em servidores de arquivos comuns. The use of an FSU also reduces hardware costs by enabling log data to be stored on lower cost storage hardware and reduces administrative complexity by allowing multiple [!DNL Sensors] to point to a single [!DNL Insight Server].

Se você estiver instalando um [!DNL Insight Server] FSU, consulte Procedimentos [de instalação para um FSU](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)do Insight Server.
