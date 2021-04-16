---
description: A seguir, são listadas as métricas incluídas no Perfil de monitoramento histórico do Data Workbench e como elas são derivadas.
title: Métricas no perfil de monitoramento histórico do Data Workbench
uuid: 47b874f7-8acb-4593-9ac9-5997d5279e52
exl-id: 65f0f605-f128-45bb-8f6c-95284b2da740
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 2%

---

# Métricas no perfil de monitoramento histórico do Data Workbench{#metrics-in-the-data-workbench-historical-monitoring-profile}

A seguir, são listadas as métricas incluídas no Perfil de monitoramento histórico do Data Workbench e como elas são derivadas.

| **Críticas de alertas** | A soma da dimensão Crítica de Alerta para cada Ping. |
|---|---|
| **Downloads de Alertas** | A soma da dimensão Alerta abaixo para cada Ping. |
| **Avisos de Alerta** | A soma da dimensão Aviso de alerta para cada Ping. |
| **Todos os componentes** | A contagem de Pings em que o sucesso da verificação de componente é igual a &quot;1&quot; dividido pela métrica Pings multiplicada por 100. |
| **Em Minutos De Atraso** | Essa métrica é a soma dos minutos de atraso de início para cada Ping, divididos pela métrica Pings . |
| **Blocos** | A soma de um para cada Bloco. |
| **Bloquear tudo** | Todos os blocos. |
| **Capacidade geral** | A métrica Tamanho da capacidade vezes 2 mais a métrica Linha de capacidade, dividida por 3. |
| **Linha de Capacidade** | A soma da dimensão Porcentagem da linha de capacidade para cada Ping dividida pela métrica Pings. |
| **Tamanho da capacidade** | A soma da dimensão Porcentagem do tamanho da capacidade para cada Ping, dividida pela métrica Pings. |
| **Comunicações** | O número de Pings em que o sucesso da verificação rápida corresponde a &quot;1&quot;, dividido pela métrica Pings . |
| **Segundos de Verificação Detalhada** | A soma da dimensão Segundos da verificação detalhada para cada Ping em que o tipo de ping é &quot;servidor&quot;, dividida pela métrica Pings. |
| **Dimension GigaBytes** | A soma de Dimension Gigabytes para cada Ping, dividida pela métrica Pings. |
| **Disco &quot;x&quot;** | As métricas de Disco são calculadas considerando a soma da Porcentagem de uso de disco para cada Ping, dividida pela métrica Pings. |
| **Estimativa de minutos de varredura** | Essa é a soma dos Dekaseconds de Varredura Estimados para cada Ping, divididos pela métrica Pings, onde os Dekaseconds de Varredura Estimada são maiores que zero, todos divididos por 6. |
| **Entrada Rápida MB por Minuto** | A soma dos megabytes de entrada rápida por minuto para cada Ping dividida pelo número de Pings quando os megabytes de entrada rápida por minuto são maiores que zero. |
| **Modo de entrada rápido** | Pings em que a dimensão Modo de processamento é igual a &quot;Entrada rápida&quot; dividido por Pings. |
| **MegaBytes de Mesclagem Rápida por Minuto** | A soma de Megabytes de Mesclagem Rápida por Minuto para cada Ping, dividida pela métrica Pings. |
| **Modo de Mesclagem Rápida** | Pings em que Modo de processamento é igual a &quot;união rápida&quot; dividido pela métrica Pings. |
| **Campo GigaBytes** | A soma dos Gigabytes de campo para cada Ping dividida pela métrica Pings. |
| **Carregar** | A soma da dimensão Média de carga para cada Ping, dividida pela métrica Pings. |
| **Leitura de registro** | A soma da dimensão Processamento de leitura de log para cada Ping, dividida pela métrica Pings, dividida por 10. |
| **Página Memória** | A soma da porcentagem do arquivo de página de memória para cada ping, dividida pela métrica Pings . |
| **Memória física** | A soma da dimensão Porcentagem física da memória para cada Ping, dividida pela métrica Pings. |
| **Consulta de memória** | A soma da Porcentagem de Consulta de Memória para cada Ping, dividida pela métrica Pings. |
| **Memória Total GB** | A soma da dimensão Total de megabytes físicos de memória para cada Ping, dividida pela métrica Pings. |
| **Conexões de rede** | Essa é a soma das Conexões de rede para cada Ping dividida pela métrica Pings . |
| **Pings x Capacidade Geral** | A métrica Pings multiplicada pela métrica Capacity Global . |
| **Milissegundos de Latência da Pesquisa** | A soma da dimensão Centis de latência de pesquisa para cada Ping, dividida pela métrica Pings, todos multiplicados por 10. |
| **Query em execução** | A soma de um para cada Ping, onde os Dekaseconds de Varredura Estimada é maior que &quot;0&quot;, dividido pela métrica Pings, onde o Tipo de Ping é igual a &quot;servidor&quot;. |
| **Segundos de verificação rápida** | A soma de segundos de verificação rápida para cada Ping, onde o tipo de ping é igual a &quot;servidor&quot;, dividida pela métrica Pings. |
| **Linhas de saída** | A soma da dimensão Linhas de saída para cada ping dividida pela métrica Pings, multiplicada por 100000. |
| **Modo de tempo real** | O número de Pings em que a dimensão Modo de processamento é igual a &quot;tempo real&quot;, dividido pela métrica Pings, todos multiplicados por 100. |
| **Modo de reprocessamento** | 100 menos o número de Pings, onde o Modo de processamento é igual a &quot;tempo real&quot; dividido pela métrica Pings, multiplicado por 100. |
| **Paralisado** | A soma da dimensão Processamento paralisado no perfil Insight [Status do perfil](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64). |
| **Banco de dados Temp** | A soma da Porcentagem de Espaço de Banco de Dados Temp para cada Ping, dividida pela métrica Pings. |
| **Transformação** | A soma da Porcentagem de transformação para cada Ping dividida pela métrica de Pings dividida por 10. |
