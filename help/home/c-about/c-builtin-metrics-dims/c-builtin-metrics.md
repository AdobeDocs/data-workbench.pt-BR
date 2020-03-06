---
description: A análise de big data inclui métricas incorporadas.
solution: Analytics
title: Métricas incorporadas
topic: Data workbench
uuid: 1e4d91dc-0130-4296-8395-fd2ddb03f6ef
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Métricas incorporadas{#built-in-metrics}

A análise de big data inclui métricas incorporadas.

A tabela a seguir lista as métricas incorporadas disponíveis para a análise de big data:

| Métrica integrada | Descrição |
|---|---|
| A partir de | A partir do tempo do conjunto de dados em intervalos de 100 nanossegundos desde 1º de janeiro de 1600 00:00 UTC. O carimbo de data e hora de início é a última hora no conjunto de dados para a qual todos os dados foram definitivamente processados. |
| Bytes de log lidos | A quantidade total de dados compactados (em bytes) processados até o momento durante a fase de processamento do log. |
| Total de bytes de log | A quantidade total de dados compactados (em bytes) em arquivos de log que correspondem aos critérios de fontes de log configuradas e o intervalo de datas de início e término do conjunto de dados. Se o processamento de log for pausado no arquivo de configuração do Modo de processamento de log, o Total de bytes de log será igual ao Total de bytes de log lidos. |
| Andamento do processamento do log | A porcentagem de conclusão da fase de processamento de log do processamento de dados do Insight Server. |
| Total de entradas de log decodificadas | O número de entradas nos arquivos de log que foram decodificados com êxito como parte da fase de processamento de log do processamento de dados do Insight Server. |
| Total de entradas de log filtradas | O número de entradas nos arquivos de log que depois de decodificados foram aceitas pelo filtro do robô e as condições de entrada do log e outros filtros que são aplicados como parte da fase de processamento do log do processamento de dados do Insight Server. |
| Total de entradas de log | O número de entradas nos arquivos de log que foram processadas até o momento pela fase de processamento de log do processamento de dados do Insight Server. |
| Total de entradas de log processadas | O número de entradas de log filtradas que foram incorporadas ao conjunto de dados da Adobe. |
| Andamento da transformação | A porcentagem de conclusão da fase de transformação do processamento de dados do Insight Server. |
| Bytes de Log Descompactados Lidos | A quantidade total de dados descompactados (em bytes) processados até o momento durante a fase de processamento do log. |

