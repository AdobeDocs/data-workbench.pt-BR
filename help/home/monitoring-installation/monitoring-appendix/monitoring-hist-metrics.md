---
description: A seguir, são mostradas as métricas incluídas no Perfil de monitoramento histórico da análise de big data e como elas são derivadas.
solution: Analytics
title: Métricas no perfil de Monitoramento Histórico da Análise de big data
topic: Data workbench
uuid: 47b874f7-8acb-4593-9ac9-5997d5279e52
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Métricas no perfil de Monitoramento Histórico da Análise de big data{#metrics-in-the-data-workbench-historical-monitoring-profile}

A seguir, são mostradas as métricas incluídas no Perfil de monitoramento histórico da análise de big data e como elas são derivadas.

| **Críticos de alerta** | A soma da dimensão Crítica de alerta para cada Ping. |
|---|---|
| **Downloads de alerta** | A soma da dimensão Alerta para baixo para cada Ping. |
| **Avisos de alerta** | A soma da dimensão Aviso de alerta para cada Ping. |
| **Todos os componentes** | A contagem de Pings em que o sucesso da verificação de componentes é igual a &quot;1&quot; dividido pela métrica Pings multiplicada por 100. |
| **Em minutos de atraso** | Essa métrica é a soma dos Minutos de Atraso da Data de Início de cada Ping, dividida pela métrica Pings. |
| **Blocos** | A soma de um para cada bloco. |
| **Bloquear tudo** | Todos os blocos. |
| **Capacidade geral** | A métrica Tamanho da capacidade vezes 2 mais a métrica Linha da capacidade, dividida por 3. |
| **Linha de capacidade** | A soma da dimensão Porcentagem da Linha de Capacidade para cada Ping dividida pela métrica Pings. |
| **Tamanho da capacidade** | A soma da dimensão Porcentagem do Tamanho da Capacidade para cada Ping, dividida pela métrica Pings. |
| **Comunicações** | O número de Pings nos quais o Quick Check Success corresponde a &quot;1&quot;, dividido pela métrica Pings. |
| **Segundos de verificação detalhados** | A soma da dimensão Segundos de verificação detalhada para cada Ping, em que o tipo de ping é &quot;servidor&quot;, dividida pela métrica Pings. |
| **Dimension GigaBytes** | A soma dos Gigabytes de dimensão para cada Ping, dividida pela métrica Pings. |
| **Disco &quot;x&quot;** | As métricas de Disco são calculadas utilizando a soma da porcentagem de uso de disco para cada Ping, dividida pela métrica Pings. |
| **Estimativa de minutos de varredura** | Essa é a soma dos Dekasegundos de Varredura Estimados para cada Ping, dividida pela métrica Pings, na qual os Dekasegundos de Varredura Estimada são maiores que zero, todos divididos por 6. |
| **Entrada rápida MB por minuto** | A soma de MegaBytes de Entrada Rápida por Minuto para cada Ping dividida pelo número de Pings quando MegaBytes de Entrada Rápida por Minuto é maior que zero. |
| **Modo de entrada rápida** | Pings nos quais a dimensão Modo de processamento é igual a &quot;Entrada rápida&quot; dividida por Pings. |
| **MegaBytes de Mesclagem Rápida por Minuto** | A soma de Megabytes de Mesclagem Rápida por Minuto para cada Ping, dividida pela métrica Pings. |
| **Modo de mesclagem rápida** | Pings nos quais o Modo de processamento é igual a &quot;união rápida&quot; dividido pela métrica Pings. |
| **GigaBytes de campo** | A soma da dimensão Gigabytes de campo para cada Ping dividida pela métrica Pings. |
| **Carregar** | A soma da dimensão Média de carga para cada Ping, dividida pela métrica Pings. |
| **Leitura do registro** | A soma da dimensão Processamento de leitura de registro para cada Ping, dividida pela métrica Pings, dividida por 10. |
| **Página de memória** | A soma da porcentagem do arquivo de página de memória para cada Ping, dividida pela métrica Pings. |
| **Memória física** | A soma da dimensão Porcentagem física da memória para cada Ping, dividida pela métrica Pings. |
| **Consulta de memória** | A soma da Porcentagem de consulta de memória para cada Ping, dividida pela métrica Pings. |
| **Memória Total GB** | A soma da dimensão Total de MegaBytes Físicos de Memória para cada Ping, dividida pela métrica Pings. |
| **Conexões de rede** | Essa é a soma das Conexões de rede para cada Ping dividida pela métrica Pings. |
| **Pings x Capacidade Geral** | A métrica Pings multiplicada pela métrica Capacity Global. |
| **Milissegundos de latência da pesquisa** | A soma da dimensão Centros de latência de pesquisa para cada Ping, dividida pela métrica Pings, todos multiplicados por 10. |
| **Consulta em Execução** | A soma de um para cada Ping em que os Dekaseconds de Varredura Estimados é maior que &quot;0&quot;, dividida pela métrica Pings em que o Tipo de Ping é igual a &quot;servidor&quot;. |
| **Segundos de verificação rápida** | A soma dos Segundos de verificação rápida para cada Ping em que o Tipo de ping é igual a &quot;servidor&quot;, dividida pela métrica Pings. |
| **Linhas de saída** | A soma da dimensão Linhas de saída para cada ping dividida pela métrica Pings, multiplicada por 100000. |
| **Modo de tempo real** | O número de Pings em que a dimensão Modo de processamento é igual a &quot;tempo real&quot;, dividido pela métrica Pings, todos multiplicados por 100. |
| **Modo de reprocessamento** | 100 menos o número de Pings em que o Modo de processamento é igual a &quot;tempo real&quot; dividido pela métrica Pings, multiplicado por 100. |
| **Paralisado** | A soma da dimensão Processando parado no perfil Status [do](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64) perfil do Insight. |
| **DB temporário** | A soma da porcentagem de espaço temporário no banco de dados para cada Ping, dividida pela métrica Pings. |
| **Transformação** | A soma da Porcentagem de transformação para cada Ping dividida pela métrica Pings dividida por 10. |

