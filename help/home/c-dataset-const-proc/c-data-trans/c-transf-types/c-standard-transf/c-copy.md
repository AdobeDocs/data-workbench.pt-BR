---
description: A transformação Copy simplesmente copia o valor no campo de entrada para o campo de saída especificado. Se o campo de entrada puder ser um vetor de cadeias de caracteres, o campo de saída deverá começar com "x-".
title: Copiar
uuid: 073f53bf-befb-4fba-a8f8-260ffcdd007c
exl-id: 04e97006-1e8e-4123-bbbc-b90a5231170f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 6%

---

# Copiar{#copy}

{{eol}}

A transformação Copy simplesmente copia o valor no campo de entrada para o campo de saída especificado. Se o campo de entrada puder ser um vetor de cadeias de caracteres, o campo de saída deverá começar com &quot;x-&quot;.

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode inserir qualquer nome aqui. |  |
| Comentários | Opcional. Observações sobre a transformação. |  |
| Condição | Condições de aplicação desta transformação. |  |
| Padrão | Usado se o teste de condição for verdadeiro e o valor de entrada não estiver disponível na entrada de log fornecida. |  |
| Entrada | O nome do campo do qual copiar. |  |
| Saída | O nome do campo de saída. |  |

Neste exemplo, que usa campos de dados coletados do tráfego do site, o campo de saída, x-purchase-success, recebe o valor literal de &quot;1&quot; sempre que cs-uri-stem corresponde [!DNL /checkout/confirmed.php]. Se a variável [!DNL Condition] não está satisfeito (ou seja, cs-uri-stem não corresponde [!DNL /checkout/confirmed.php]), x-purchase-success não é alterado.

![](assets/cfg_TransformationType_Copy.png)
