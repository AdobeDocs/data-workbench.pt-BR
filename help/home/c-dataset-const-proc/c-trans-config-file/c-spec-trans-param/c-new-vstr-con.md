---
description: A Nova condição do visitante é uma operação de condição usada com dados do site para determinar quais visitantes são considerados para inclusão no conjunto de dados.
solution: Analytics
title: Nova condição do visitante
topic: Data workbench
uuid: e9733109-5bf3-47ce-974c-d68264291f19
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Nova condição do visitante{#new-visitor-condition}

A Nova condição do visitante é uma operação de condição usada com dados do site para determinar quais visitantes são considerados para inclusão no conjunto de dados.

O [!DNL New Visitor Condition] define a primeira entrada de log (ordenada por hora) para um visitante que deve ser usada no conjunto de dados, e todas as entradas de log subsequentes para esse visitante são incluídas no conjunto de dados, independentemente de atender a essa condição. Como os dados [!DNL New Visitor Condition] exigem que sejam ordenados pelo visitante e pelo tempo, são aplicados somente durante a fase de transformação da construção do conjunto de dados.

O [!DNL New Visitor Condition] mostrado neste exemplo cria um conjunto de dados que inclui apenas as entradas de registro para visitantes que respondem a campanhas por email. Isso é feito usando o [!DNL NotEmptyCondition] teste (consulte [Não vazio](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)) e o [!DNL x-campaign-email] campo como entrada para a expressão regular. Depois que os novos visitantes que atenderem à condição forem identificados, todas as entradas de log desses visitantes serão capturadas.

![](assets/cfg_Transformation_NewVisitorCondition.png)

