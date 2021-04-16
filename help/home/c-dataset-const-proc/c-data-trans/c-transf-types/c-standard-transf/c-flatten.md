---
description: A transformação Nivelar pega um vetor de sequências de caracteres e mapeia cada valor em seu próprio campo.
title: Flatten
uuid: 00b06a5c-506b-45fe-9773-44d65b8ec233
exl-id: 63f3e4bc-238f-4e15-8ae5-2f805bd080d3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Flatten{#flatten}

A transformação Nivelar pega um vetor de sequências de caracteres e mapeia cada valor em seu próprio campo.

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode inserir qualquer nome aqui. |  |
| Comentários | Opcional. Observações sobre a transformação. |  |
| Condição | Condições de aplicação desta transformação. |  |
| Padrão | O valor padrão a ser usado se a condição for atendida e o valor de entrada não estiver disponível para a entrada de log. |  |
| Entrada | Um vetor de valores de string para mapear para os nomes de campo de saída. |  |
| Saídas | Um conjunto de nomes de campo de saída. |  |

Considerações para [!DNL Flatten]

* Se o vetor de entrada contiver mais valores do que os campos de saída definidos, os valores de entrada extras serão simplesmente soltos.
* Se o vetor de entrada contiver menos valores do que existem campos de saída definidos, os campos de saída extras receberão o valor padrão (se definido) ou uma string vazia, se nenhum valor padrão for definido.

Aqui, a transformação [!DNL Flatten] é usada para pegar um vetor de produtos (x-products) e separá-los em quatro campos (x-product1, ..., x-product4).

![](assets/cfg_TransformationType_Flatten.png)

Se o valor de entrada contivesse as cadeias de caracteres B57481, C46355 e Z97123, os campos de saída teriam os valores mostrados aqui:

* x-product1 = B57481
* x-product2 = C46355
* x-product3 = Z97123
* x-product4 = Empty (há mais entradas do que saídas e não há valor padrão especificado.)
