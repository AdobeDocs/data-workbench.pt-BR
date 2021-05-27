---
description: Após adicionar o novo campo ao Log Processing.cfg e criar a nova transformação Split e a dimensão estendida, é possível visualizar a nova dimensão estendida criada assim que o estágio Entrada rápida do reprocessamento de dados terminar.
solution: Analytics,Analytics
title: Exibir os resultados do experimento
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
exl-id: cada693c-79cb-4f49-a2f0-6ff60425be1c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 4%

---

# Exibir os resultados do experimento{#viewing-the-experiment-results}

Após adicionar o novo campo ao Log Processing.cfg e criar a nova transformação Split e a dimensão estendida, é possível visualizar a nova dimensão estendida criada assim que o estágio Entrada rápida do reprocessamento de dados terminar.

Essa dimensão, por padrão, exibe o número de sessões para cada um dos grupos de experimentos.

**Para exibir a dimensão do experimento**

* Em qualquer espaço de trabalho em [!DNL Insight], abra uma tabela com a dimensão de experimento que você criou.

   Os elementos da dimensão de experimento, que representam cada experimento que você está executando atualmente e cada grupo em cada experimento, são exibidos com o número atual de sessões para cada grupo. Cada grupo é nomeado no seguinte formato usando o nome do experimento seguido pelo nome do grupo:

   *Nome do experimento.Nome do grupo*

   Por exemplo: [!DNL New Homepage.Control]

A tabela a seguir mostra a dimensão Grupos de experiência controlados que foi criada em [!DNL Transformation.cfg] e cada um dos experimentos e seus grupos.

O experimento da Nova Página Inicial é mostrado na parte inferior da tabela com seus dois grupos: Controle e índice2.

![](assets/controlledexpgrps.png)

Agora você pode usar a dimensão de experimento e qualquer métrica relevante para explorar e interpretar os resultados do experimento, bem como criar relatórios úteis detalhando esses resultados.
