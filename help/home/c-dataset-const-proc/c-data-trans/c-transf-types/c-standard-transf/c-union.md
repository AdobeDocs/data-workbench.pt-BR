---
description: A transformação da União utiliza um conjunto de entradas e cria um vetor de cadeias de caracteres como saída.
solution: Analytics
title: União
topic: Data workbench
uuid: 2f8bd332-727e-4a4e-a3e7-a52ea2b0a33a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# União{#union}

A transformação da União utiliza um conjunto de entradas e cria um vetor de cadeias de caracteres como saída.

Se uma das entradas for um vetor, cada elemento no vetor de entrada será associado a um elemento no vetor de saída (ou seja, a transformação não criará um vetor de vetores).

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode digitar qualquer nome aqui. |  |
| Comentários | Opcional. Notas sobre a transformação. |  |
| Condição | As condições em que essa transformação é aplicada. |  |
| Padrão | O valor padrão a ser usado se a condição for cumprida e o valor de entrada não estiver disponível. |  |
| Entradas | Um ou mais valores de entrada. |  |
| Saída | O nome do campo de saída. |  |

Este exemplo usa campos de dados do tráfego do site para criar uma lista de códigos postais associados aos visitantes do site (ou seja, em cada entrada de registro). Os dados fornecem duas fontes possíveis para essas informações: um em cs-uri-query e o outro em um [!DNL zipcode] campo do cookie. Se nenhum desses campos contiver um código postal, o valor padrão de 00000 será usado.

![](assets/cfg_TransformationType_Union.png)

Embora seja possível que ambos os valores estejam disponíveis em uma única entrada de log, você pode selecionar qual valor usar ao criar uma dimensão com base na saída da transformação. Em um caso de uso típico, você criaria uma dimensão simples que utiliza o primeiro ou o último dos valores encontrados. Para obter informações sobre como criar dimensões simples, consulte Dimensões [estendidas](../../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).
