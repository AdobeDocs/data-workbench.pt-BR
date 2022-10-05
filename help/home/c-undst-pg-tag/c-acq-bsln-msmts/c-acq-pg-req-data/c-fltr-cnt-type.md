---
description: A finalidade do recurso de filtragem do tipo conteúdo do Sensor é eliminar a necessidade de armazenar e processar informações que não são úteis para fins de análise.
title: Filtrar por tipo de conteúdo
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
exl-id: 0ed93a18-ef47-462b-8609-3ec98b037e6b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 4%

---

# Filtrar por tipo de conteúdo{#filtering-by-content-type}

{{eol}}

A finalidade do recurso de filtragem do tipo conteúdo do Sensor é eliminar a necessidade de armazenar e processar informações que não são úteis para fins de análise.

A maioria dos dados de solicitação que estão disponíveis por meio da API de um servidor da Web não é útil na análise de negócios. Armazenamento e processamento são caros e [!DNL Sensor’s] a filtragem do tipo conteúdo permite evitar armazenamento e processamento desnecessários.

Para maximizar o desempenho do processamento de dados do log da Web e reduzir a quantidade de dados de medição que devem ser armazenados, [!DNL Site] O adquire dados de medição (dados de solicitação, entradas de log, dados de log e assim por diante) para todas as solicitações do tipo de conteúdo da Web, exceto para tipos de conteúdo especificamente listados (como folhas de estilo em cascata, solicitações de imagem e assim por diante), que são filtrados antes de serem transmitidos para o servidor do Data Workbench por [!DNL Sensor]. Essa filtragem pode ser desabilitada para um servidor da Web inteiro e também pode ser substituída para um objeto de conteúdo específico ao adicionar o par de nome-valor &quot;Log=1&quot; à string de consulta de um objeto incorporado específico (por exemplo, [!DNL https://www.mysite.com/advertisement.gif?Log=1]).
