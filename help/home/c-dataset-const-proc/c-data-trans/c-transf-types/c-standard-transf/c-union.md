---
description: A transformação Union utiliza um conjunto de entradas e cria um vetor de cadeias de caracteres como saída.
title: União
uuid: 2f8bd332-727e-4a4e-a3e7-a52ea2b0a33a
exl-id: 841b5133-d587-409c-b39e-47169beb2ddf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 4%

---

# União{#union}

{{eol}}

A transformação Union utiliza um conjunto de entradas e cria um vetor de cadeias de caracteres como saída.

Se uma das entradas for por si só um vetor, cada elemento no vetor de entrada será associado a um elemento no vetor de saída (ou seja, a transformação não cria um vetor de vetores).

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode inserir qualquer nome aqui. |  |
| Comentários | Opcional. Observações sobre a transformação. |  |
| Condição | Condições de aplicação desta transformação. |  |
| Padrão | O valor padrão a ser usado se a condição for atendida e o valor de entrada não estiver disponível. |  |
| Entradas | Um ou mais valores de entrada. |  |
| Saída | O nome do campo de saída. |  |

Este exemplo usa campos de dados do tráfego do site para criar uma lista dos códigos postais associados aos visitantes do site (ou seja, dentro de cada entrada de log). Os dados fornecem duas fontes possíveis para essas informações: um em cs-uri-query e outro em um [!DNL zipcode] do cookie. Se nenhum desses campos contiver um código postal, o valor padrão de 00000 será usado.

![](assets/cfg_TransformationType_Union.png)

Embora seja possível que ambos os valores estejam disponíveis em uma única entrada de log, você pode selecionar qual valor usar ao criar uma dimensão com base na saída da transformação. Em um caso de uso típico, você criaria uma dimensão simples que utiliza o primeiro ou o último dos valores encontrados. Para obter informações sobre como criar dimensões simples, consulte [Dimension estendidas](../../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).
