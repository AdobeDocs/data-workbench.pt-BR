---
description: Depois de adicionar o novo campo ao Log Processing.cfg e criar a nova transformação Dividir e a dimensão estendida, é possível exibir a nova dimensão estendida criada assim que o estágio de Entrada rápida do reprocessamento de dados terminar.
solution: Insight,Analytics
title: Exibição dos resultados do experimento
topic: Data workbench
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exibição dos resultados do experimento{#viewing-the-experiment-results}

Depois de adicionar o novo campo ao Log Processing.cfg e criar a nova transformação Dividir e a dimensão estendida, é possível exibir a nova dimensão estendida criada assim que o estágio de Entrada rápida do reprocessamento de dados terminar.

Essa dimensão, por padrão, exibe o número de sessões para cada um dos grupos de experimentos.

**Para exibir a dimensão do experimento**

* Em qualquer espaço de trabalho em [!DNL Insight], abra uma tabela com a dimensão de experimento que você criou.

   Os elementos de dimensão do experimento, que representam cada experimento que você está executando no momento e cada grupo em cada experimento, são exibidos com o número atual de sessões para cada grupo. Cada grupo é nomeado no seguinte formato usando o nome do experimento seguido pelo nome do grupo:

   *Nome do Experimento.Nome do Grupo*

   Por exemplo: [!DNL New Homepage.Control]

A tabela a seguir mostra a dimensão Grupos de Experimentos Controlados que foi criada em cada um [!DNL Transformation.cfg] dos experimentos e seus grupos.

O experimento New Homepage é mostrado na parte inferior da tabela com seus dois grupos: Control e index2.

![](assets/controlledexpgrps.png)

Agora você pode usar a dimensão do experimento e qualquer métrica relevante para explorar e interpretar os resultados do experimento, bem como criar relatórios úteis detalhando esses resultados.
