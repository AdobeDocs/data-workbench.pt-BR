---
description: As expressões de métrica, dimensão e filtro podem usar identificadores para fazer referência a métricas nomeadas, dimensões e filtros.
solution: Analytics
title: Sintaxe para identificadores
topic: Data workbench
uuid: 9cfa188a-05ca-4163-a268-e33fce9a1929
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sintaxe para identificadores{#syntax-for-identifiers}

As expressões de métrica, dimensão e filtro podem usar identificadores para fazer referência a métricas nomeadas, dimensões e filtros.

Esses identificadores fazem distinção entre maiúsculas e minúsculas e devem ser digitados exatamente como estão definidos.

Um identificador válido pode conter um ou mais dos seguintes:

* Sublinhados (_). Os sublinhados em um identificador representam espaços na métrica, dimensão ou nome do filtro. Por exemplo, a dimensão Referenciador de sessão seria chamada [!DNL Session_Referrer] em uma expressão.
* Sinais de porcentagem (%)
* Letras maiúsculas (A-Z)
* Letras minúsculas (a-z)
* Sinais de dólar ($)
* Números (0-9), exceto como o primeiro caractere em um identificador.
* Caracteres não ASCII

Todos os outros caracteres são ilegais em um identificador.

Essas mesmas regras se aplicam aos nomes de métricas, dimensões e filtros quando são usados fora de expressões, exceto que os nomes podem conter espaços, mas não sublinhados. Por exemplo, você pode definir a dimensão Referenciador de sessão no [!DNL Transformation.cfg] arquivo como Referenciador de sessão, mas não [!DNL Session_Referrer].
