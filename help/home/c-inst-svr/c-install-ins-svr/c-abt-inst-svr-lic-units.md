---
description: O Insight Server está disponível em dois tipos de licença.
solution: Insight
title: Sobre as Unidades de Licença do Insight Server
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sobre as Unidades de Licença do Insight Server{#about-insight-server-license-units}

O Insight Server está disponível em dois tipos de licença.

Estes são os dois tipos de licença:

* [Unidade de processamento de dados (DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [Unidade de servidor de arquivos (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## Unidade de processamento de dados (DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

Esse tipo de [!DNL Insight Server] pode processar, armazenar e fornecer dados de um conjunto de dados da Adobe. Como opção, ele pode armazenar os arquivos de log que contêm os dados de origem a partir dos quais o conjunto de dados é construído, ou pode receber esses dados de uma Unidade de Servidor de [!DNL Insight Server] Arquivos (FSU). Uma DPU é o tipo de [!DNL Insight Server] interação direta entre [!DNL Insight] e [!DNL Report] clientes.

Se você estiver instalando uma [!DNL Insight Server] DPU, consulte Procedimentos [de instalação para uma DPU](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc)do Insight Server.

## Unidade de servidor de arquivos (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

Esse tipo de servidor é configurado para receber e armazenar dados de eventos de uma ou mais instâncias de replicação de dados de eventos [!DNL Sensor] ( [!DNL Repeater] [!DNL Insight Server] funcionalidade fornecida com uma licença de uso especial) e transmitir os dados para uma ou mais Unidades de processamento de dados (DPUs) para a construção de conjuntos de dados da Adobe. As DPUs se comunicam com um FSU usando um protocolo que otimiza a transferência de dados de eventos para a DPU e é significativamente mais rápido do que manter arquivos de log em servidores de arquivos comuns. O uso de um FSU também reduz os custos de hardware ao permitir que os dados de registro sejam armazenados em hardware de armazenamento de menor custo e reduz a complexidade administrativa ao permitir que vários [!DNL Sensors] a apontem para um único [!DNL Insight Server].

Se você estiver instalando um [!DNL Insight Server] FSU, consulte Procedimentos [de instalação para um FSU](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)do Insight Server.
