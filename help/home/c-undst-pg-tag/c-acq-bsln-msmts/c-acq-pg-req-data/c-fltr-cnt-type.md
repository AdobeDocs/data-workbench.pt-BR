---
description: A finalidade do recurso de filtragem do tipo conteúdo do Sensor é eliminar a necessidade de armazenar e processar informações que não são úteis para fins de análise.
title: Filtrar por tipo de conteúdo
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
exl-id: 0ed93a18-ef47-462b-8609-3ec98b037e6b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 4%

---

# Filtrar por tipo de conteúdo{#filtering-by-content-type}

A finalidade do recurso de filtragem do tipo conteúdo do Sensor é eliminar a necessidade de armazenar e processar informações que não são úteis para fins de análise.

A maioria dos dados de solicitação que estão disponíveis por meio da API de um servidor da Web não é útil na análise de negócios. O armazenamento e o processamento são caros e a filtragem do tipo conteúdo [!DNL Sensor’s] permite evitar armazenamento e processamento desnecessários.

Para maximizar o desempenho do processamento de dados do log da Web e reduzir a quantidade de dados de medição que devem ser armazenados, [!DNL Site] adquire dados de medição (dados de solicitação, entradas de log, dados de log, etc.) para todas as solicitações do tipo conteúdo da Web, exceto para tipos de conteúdo listados especificamente (como folhas de estilo em cascata, solicitações de imagem e assim por diante), que são filtrados antes de serem transmitidos para o servidor do Data Workbench por [!DNL Sensor]. Essa filtragem pode ser desativada para um servidor da Web inteiro e também pode ser substituída para um objeto de conteúdo específico ao adicionar o par de nome-valor &quot;Log=1&quot; à string de consulta de um objeto incorporado específico (por exemplo, [!DNL http://www.mysite.com/advertisement.gif?Log=1]).
