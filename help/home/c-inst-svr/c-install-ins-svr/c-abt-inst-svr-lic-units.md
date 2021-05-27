---
description: O Insight Server está disponível em dois tipos de licença.
title: Sobre as unidades de licença do servidor Insight
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
exl-id: 82d6fa29-d36e-480d-a975-f5a5e60a32d2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
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

Esse tipo de [!DNL Insight Server] pode processar, armazenar e veicular dados de um conjunto de dados de Adobe. Opcionalmente, ele pode armazenar os arquivos de log que contêm os dados de origem a partir dos quais o conjunto de dados é construído, ou pode receber esses dados de uma [!DNL Insight Server] Unidade de Servidor de Arquivos (FSU). Uma DPU é o tipo de [!DNL Insight Server] com o qual os clientes [!DNL Insight] e [!DNL Report] interagem diretamente.

Se estiver instalando uma [!DNL Insight Server] DPU, consulte [Procedimentos de instalação para uma DPU do servidor Insight](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc).

## Unidade de servidor de arquivos (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

Esse tipo de servidor é configurado para receber e armazenar dados de evento de uma ou mais [!DNL Sensor] ou instâncias de replicação de dados de evento (a funcionalidade [!DNL Repeater] fornecida com uma licença de uso especial) e fazer o fluxo dos dados para uma ou mais [!DNL Insight Server] Unidades de processamento de dados (DPUs) para criar conjuntos de dados de Adobe. As DPUs se comunicam com uma FSU usando um protocolo que otimiza a transferência de dados do evento para a DPU e é significativamente mais rápido do que manter arquivos de log em servidores de arquivos comuns. O uso de uma FSU também reduz os custos de hardware ao permitir que os dados de log sejam armazenados em hardware de armazenamento de custo mais baixo e reduz a complexidade administrativa ao permitir que vários [!DNL Sensors] apontem para um único [!DNL Insight Server].

Se estiver instalando uma FSU [!DNL Insight Server], consulte [Procedimentos de instalação para uma FSU do servidor Insight](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016).
