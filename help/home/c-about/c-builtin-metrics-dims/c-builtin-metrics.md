---
description: O Data Workbench inclui métricas incorporadas.
title: Métricas embutidas
uuid: 1e4d91dc-0130-4296-8395-fd2ddb03f6ef
exl-id: a8a2a8dd-dc13-4eb3-92ce-09f02252ecf0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 1%

---

# Métricas embutidas{#built-in-metrics}

{{eol}}

O Data Workbench inclui métricas incorporadas.

A tabela a seguir lista as métricas internas disponíveis para o Data Workbench:

| Métrica integrada | Descrição |
|---|---|
| Em | A partir do tempo do conjunto de dados em intervalos de 100 nanossegundos desde 1º de janeiro de 1600 00:00 UTC. O carimbo de data e hora de início é o último horário no conjunto de dados para o qual todos os dados foram definitivamente processados. |
| Bytes de Log Lidos | A quantidade total de dados compactados (em bytes) que foi processada até o momento durante a fase de processamento de log. |
| Total de Bytes de Log | A quantidade total de dados compactados (em bytes) em arquivos de log que correspondem aos critérios das fontes de log configuradas e ao intervalo de datas inicial e final do conjunto de dados. Se o processamento de log estiver pausado no arquivo de configuração do Modo de Processamento de Log, o Total de Bytes de Log será igual ao Total de Bytes de Log Lidos. |
| Andamento do processamento de log | A porcentagem de conclusão da fase de processamento de log do processamento de dados do Servidor Insight. |
| Total de entradas de log decodificadas | O número de entradas nos arquivos de log que foram decodificados com êxito como parte da fase de processamento de log do processamento de dados do Insight Server. |
| Total de Entradas de Log Filtradas | O número de entradas nos arquivos de log que após serem decodificados foram aceitas pelo filtro do robô e as condições de entrada do log e outros filtros que são aplicados como parte da fase de processamento de log do processamento de dados do Insight Server. |
| Total de Entradas de Log | O número de entradas nos arquivos de log que foram processados até o momento pela fase de processamento de log do processamento de dados do Insight Server. |
| Total de Entradas de Log Processadas | O número de entradas de log filtradas que foram incorporadas ao conjunto de dados do Adobe. |
| Andamento da transformação | A porcentagem de conclusão da fase de transformação do processamento de dados do Insight Server. |
| Bytes de Log Descompactados Lidos | A quantidade total de dados descompactados (em bytes) que foi processada até o momento durante a fase de processamento de log. |
