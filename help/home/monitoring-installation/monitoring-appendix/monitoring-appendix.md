---
description: Este documento descreve os perfis com seus campos, dimensões e métricas empregadas pelo Perfil de monitoramento da análise de big data.
solution: Analytics
title: Dimensões e métricas do perfil do Análise de big data
topic: Data workbench
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensões e métricas do perfil do Análise de big data{#data-workbench-profile-dimensions-and-metrics}

Este documento descreve os perfis com seus campos, dimensões e métricas empregadas pelo Perfil de monitoramento da análise de big data.

Para monitorar os servidores da análise de big data, os dados são coletados usando um script que analisa o Status detalhado e também captura informações específicas do servidor. As informações do servidor da análise de big data são então passadas para uma chamada de tag de página para o Sensor da análise de big data para coletar e salvar em um arquivo VSL.

## Perfis empregados pelo perfil de monitoramento da análise de big data {#section-b5b1234f55c3407dae8e68b031b7cd7f}

Esses perfis fornecem dimensões e métricas que permitem visualizar o estado do servidor e os dados de desempenho:

* [Dimensões no perfil Status do perfil do Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Dimensões no perfil Status do Insight Server](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Dimensões no perfil Histórico do Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Métricas no perfil Monitoramento histórico do Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

Os perfis de Status permitem que você veja como a análise de big data está sendo executada atualmente de uma perspectiva operacional. O perfil Status **do** Perfil e o perfil Status **do** Servidor coletam dados do Status Detalhado e dos servidores da análise de big data. Todos os dados coletados são colocados no `cs-uri-query` campo para uso.

Os perfis **** históricos permitem avaliar o impacto das alterações de configuração e hardware usando dados históricos. O perfil histórico pode ser o mais útil, pois permite avaliar o impacto das alterações de configuração e hardware ao longo do tempo.
