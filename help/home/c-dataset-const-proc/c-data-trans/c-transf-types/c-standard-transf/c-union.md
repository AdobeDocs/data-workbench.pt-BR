---
description: A transformação Union utiliza um conjunto de entradas e cria um vetor de cadeias de caracteres como saída.
title: União
uuid: 2f8bd332-727e-4a4e-a3e7-a52ea2b0a33a
exl-id: 841b5133-d587-409c-b39e-47169beb2ddf
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 3%

---

# União{#union}

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

Este exemplo usa campos de dados do tráfego do site para criar uma lista dos códigos postais associados aos visitantes do site (ou seja, dentro de cada entrada de log). Os dados fornecem duas fontes possíveis para essas informações: um em cs-uri-query e o outro em um campo [!DNL zipcode] do cookie. Se nenhum desses campos contiver um código postal, o valor padrão de 00000 será usado.

![](assets/cfg_TransformationType_Union.png)

Embora seja possível que ambos os valores estejam disponíveis em uma única entrada de log, você pode selecionar qual valor usar ao criar uma dimensão com base na saída da transformação. Em um caso de uso típico, você criaria uma dimensão simples que utiliza o primeiro ou o último dos valores encontrados. Para obter informações sobre como criar dimensões simples, consulte [Dimension estendido](../../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).
