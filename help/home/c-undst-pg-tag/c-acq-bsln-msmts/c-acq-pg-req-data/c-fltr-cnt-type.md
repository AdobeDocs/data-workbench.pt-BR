---
description: A finalidade do recurso de filtragem do tipo de conteúdo do Sensor é eliminar a necessidade de armazenar e processar informações que não são úteis para fins de análise.
solution: Analytics
title: Filtragem por tipo de conteúdo
topic: Data workbench
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Filtragem por tipo de conteúdo{#filtering-by-content-type}

A finalidade do recurso de filtragem do tipo de conteúdo do Sensor é eliminar a necessidade de armazenar e processar informações que não são úteis para fins de análise.

Muitos dos dados de solicitação que estão disponíveis por meio da API de um servidor da Web não são úteis na análise de negócios. O armazenamento e o processamento são caros e a filtragem do tipo de [!DNL Sensor’s] conteúdo permite evitar o armazenamento e o processamento desnecessários.

Para maximizar o desempenho do processamento de dados de log da Web e reduzir a quantidade de dados de medição que devem ser armazenados, [!DNL Site] adquire dados de medição (dados de solicitação, entradas de log, dados de log e assim por diante) para todas as solicitações de tipo de conteúdo da Web, exceto para tipos de conteúdo especificamente listados (como folhas de estilo em cascata, solicitações de imagem e assim por diante), que são filtrados antes de serem transmitidos ao servidor de análise de big data por [!DNL Sensor]. Essa filtragem pode ser desativada para um servidor da Web inteiro e também pode ser substituída para um objeto de conteúdo específico adicionando o par nome-valor &quot;Log=1&quot; à string de consulta de um objeto incorporado específico (por exemplo, [!DNL http://www.mysite.com/advertisement.gif?Log=1]).
