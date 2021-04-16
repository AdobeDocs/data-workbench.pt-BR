---
description: Métrica, dimensão e expressões de filtro podem usar identificadores para fazer referência a métricas, dimensões e filtros nomeados.
title: Sintaxe para identificadores
uuid: 9cfa188a-05ca-4163-a268-e33fce9a1929
exl-id: 79bc5585-7b21-4a9d-b044-28ff4bc5a885
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 3%

---

# Sintaxe para identificadores{#syntax-for-identifiers}

Métrica, dimensão e expressões de filtro podem usar identificadores para fazer referência a métricas, dimensões e filtros nomeados.

Esses identificadores fazem distinção entre maiúsculas e minúsculas e devem ser digitados exatamente como estão definidos.

Um identificador válido pode conter um ou mais dos seguintes itens:

* Sublinhados (_). Os sublinhados em um identificador representam espaços na métrica, dimensão ou nome do filtro. Por exemplo, a dimensão Referenciador de sessão seria chamada de [!DNL Session_Referrer] em uma expressão.
* Sinal de porcentagem (%)
* Letras maiúsculas (A-Z)
* Letras minúsculas (a-z)
* Sinais em dólar ($)
* Números (0-9), exceto como o primeiro caractere em um identificador.
* Caracteres não ASCII

Todos os outros caracteres são inválidos em um identificador.

Essas mesmas regras se aplicam aos nomes das métricas, dimensões e filtros quando são usados fora das expressões, exceto que os nomes podem conter espaços, mas não sublinhados. Por exemplo, você pode definir a dimensão Referenciador de sessão no arquivo [!DNL Transformation.cfg] como Referenciador de sessão, mas não [!DNL Session_Referrer].
