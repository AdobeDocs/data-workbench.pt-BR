---
description: O perfil de status do perfil do Data Workbench fornece informações atuais sobre a integridade do servidor do Data Workbench com base no perfil, em vez de métricas do servidor ou dados históricos.
title: Espaço de trabalho Status do perfil do Data Workbench
uuid: b54713c8-863d-4376-8ebf-4a2985e28c76
exl-id: 40b9b0bf-4fd9-48d8-875b-514921c520cd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 4%

---

# Espaço de trabalho Status do perfil do Data Workbench{#data-workbench-profile-status-workspace}

O perfil de status do perfil do Data Workbench fornece informações atuais sobre a integridade do servidor do Data Workbench com base no perfil, em vez de métricas do servidor ou dados históricos.

## Status do perfil de Data Workbench {#section-65d1fa393cfd450cbacef3cba823fcc1}

Esse perfil de status fornece as informações atuais do servidor do Data Workbench, mas não em tempo real, pois o agente é pesquisado a cada dez minutos e os relatórios sempre incluem essa latência de dez minutos. Mais precisamente, os conjuntos de dados gerados por esse perfil fornecem a última observação do servidor a partir do agente, que com mais frequência tem um período de pesquisa padrão de dez minutos.

Para obter informações de referência adicionais sobre as dimensões usadas no perfil de status do perfil do Data Workbench, consulte [Perfil de status do insight](../../../home/monitoring-installation/monitoring-profiles/monitoring-profile-using.md#concept-d4cd7da41c8a42bab4aea25418264e64).

![](assets/Status_General_Status.png)

Este relatório é mais para monitorar operações do que componentes ou flutuações de tráfego específicas.

![](assets/Status_General_page.png)

Isso nos dá uma ideia de quem está em que modo: Se vermos uma alta taxa de Entrada Rápida para um determinado perfil, então esse perfil está no modo de Entrada Rápida.

Se a métrica Parada for 1, o servidor será paralisado. Se o valor for 0, o servidor não será paralisado.

**Leitura de log para grandes cargas em lote**

![](assets/Status_General_stalled_log.png)
