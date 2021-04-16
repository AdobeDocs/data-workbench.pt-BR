---
description: A condição de novo visitante é uma operação de condição usada com dados de site para determinar quais visitantes são considerados para inclusão no conjunto de dados.
title: Condição de novo visitante
uuid: e9733109-5bf3-47ce-974c-d68264291f19
exl-id: a0520edd-bde3-4f55-858c-8974d4224435
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 3%

---

# Condição de novo visitante{#new-visitor-condition}

A condição de novo visitante é uma operação de condição usada com dados de site para determinar quais visitantes são considerados para inclusão no conjunto de dados.

O [!DNL New Visitor Condition] define a primeira entrada de log (ordenada por hora) para um visitante que deve ser usado no conjunto de dados, e todas as entradas de log subsequentes para esse visitante são incluídas no conjunto de dados, independentemente de atender a essa condição. Como [!DNL New Visitor Condition] requer que os dados sejam solicitados pelo visitante e pelo tempo, eles são aplicados somente durante a fase de transformação da construção do conjunto de dados.

O [!DNL New Visitor Condition] mostrado neste exemplo cria um conjunto de dados que inclui apenas essas entradas de log para visitantes que respondem a campanhas de email. Isso é feito usando o teste [!DNL NotEmptyCondition] (consulte [Não vazio](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)) e o campo [!DNL x-campaign-email] como entrada para a expressão regular. Depois que os novos visitantes que atendem à condição são identificados, todas as entradas de log desses visitantes são capturadas.

![](assets/cfg_Transformation_NewVisitorCondition.png)
