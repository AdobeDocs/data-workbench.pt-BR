---
description: Este documento descreve os perfis com seus campos, dimensões e métricas empregados pelo Perfil de monitoramento do Data Workbench.
title: Dimensões e métricas do perfil do Data Workbench
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
exl-id: cfad9897-2ea3-47e4-aa36-416e0fde9358
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 5%

---

# Dimensões e métricas do perfil do Data Workbench{#data-workbench-profile-dimensions-and-metrics}

Este documento descreve os perfis com seus campos, dimensões e métricas empregados pelo Perfil de monitoramento do Data Workbench.

Para monitorar servidores do Data Workbench, os dados são coletados usando um script que analisa o Status Detalhado e captura informações específicas do servidor. As informações do servidor do Data Workbench são passadas para uma chamada de tag de página para o Sensor do Data Workbench coletar e salvar em um arquivo de VSL.

## Perfis empregados pelo perfil de monitoramento do Data Workbench {#section-b5b1234f55c3407dae8e68b031b7cd7f}

Esses perfis fornecem dimensões e métricas que permitem exibir dados de estado e desempenho do servidor:

* [Dimension no perfil de status do perfil do Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Dimension no perfil de status do servidor Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Dimension no perfil histórico do Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Métricas no perfil de monitoramento histórico do Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

Os perfis de status permitem ver como o Data Workbench está sendo executado atualmente de uma perspectiva operacional. O perfil **Status do perfil** e o perfil **Status do servidor** coletam dados do Status detalhado e dos servidores do Data Workbench. Todos os dados coletados são colocados no campo `cs-uri-query` para uso.

Os **Historic profiles** permitem avaliar o impacto das alterações de configuração e hardware usando dados históricos. O perfil histórico pode ser o mais útil, pois permite avaliar o impacto das alterações de configuração e hardware ao longo do tempo.
