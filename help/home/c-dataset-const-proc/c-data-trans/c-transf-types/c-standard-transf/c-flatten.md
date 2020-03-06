---
description: A transformação Nivelar pega um vetor de sequências de caracteres e mapeia cada valor em seu próprio campo.
solution: Analytics
title: Nivelar
topic: Data workbench
uuid: 00b06a5c-506b-45fe-9773-44d65b8ec233
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Nivelar{#flatten}

A transformação Nivelar pega um vetor de sequências de caracteres e mapeia cada valor em seu próprio campo.

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode digitar qualquer nome aqui. |  |
| Comentários | Opcional. Notas sobre a transformação. |  |
| Condição | As condições em que essa transformação é aplicada. |  |
| Padrão | O valor padrão a ser usado se a condição for cumprida e o valor de entrada não estiver disponível para a entrada do registro. |  |
| Entrada | Um vetor de valores de string para mapear para os nomes de campo de saída. |  |
| Saídas | Um conjunto de nomes de campos de saída. |  |

Considerações para [!DNL Flatten]

* Se o vetor de entrada contiver mais valores do que os campos de saída definidos, os valores de entrada extras serão simplesmente descartados.
* Se o vetor de entrada contiver menos valores do que os campos de saída definidos, os campos de saída extras receberão o valor padrão (se definido) ou uma string vazia se nenhum valor padrão for definido.

Aqui, a [!DNL Flatten] transformação é usada para pegar um vetor de produtos (x-products) e separá-los em quatro campos (x-product1, ..., x-product4).

![](assets/cfg_TransformationType_Flatten.png)

Se o valor de entrada contivesse as strings B57481, C46355 e Z97123, os campos de saída teriam os valores mostrados aqui:

* x-product1 = B57481
* x-product2 = C46355
* x-product3 = Z97123
* x-product4 = Vazio (há mais entradas do que saídas e não há valor padrão especificado.)

