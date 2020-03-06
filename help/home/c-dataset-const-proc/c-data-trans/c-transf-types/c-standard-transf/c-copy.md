---
description: A transformação Copiar simplesmente copia o valor no campo de entrada para o campo de saída especificado. Se o campo de entrada puder ser um vetor de strings, o campo de saída deve começar com "x-".
solution: Analytics
title: Copiar
topic: Data workbench
uuid: 073f53bf-befb-4fba-a8f8-260ffcdd007c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Copiar{#copy}

A transformação Copiar simplesmente copia o valor no campo de entrada para o campo de saída especificado. Se o campo de entrada puder ser um vetor de strings, o campo de saída deve começar com &quot;x-&quot;.

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode digitar qualquer nome aqui. |  |
| Comentários | Opcional. Notas sobre a transformação. |  |
| Condição | As condições em que essa transformação é aplicada. |  |
| Padrão | Usado se o teste de condição for verdadeiro e o valor de entrada não estiver disponível na entrada de log fornecida. |  |
| Entrada | O nome do campo a partir do qual copiar. |  |
| Saída | O nome do campo de saída. |  |

Neste exemplo, que usa campos de dados coletados do tráfego do site, o campo de saída, x-purchase-success, recebe o valor literal de &quot;1&quot; cada vez que cs-uri-stem corresponde [!DNL /checkout/confirmed.php]. Se o sistema não [!DNL Condition] estiver satisfeito (ou seja, cs-uri-stem não corresponde [!DNL /checkout/confirmed.php]), x-purchase-success não será alterado.

![](assets/cfg_TransformationType_Copy.png)

