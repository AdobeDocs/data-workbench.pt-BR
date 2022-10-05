---
description: Regras de sintaxe para fórmulas.
title: Sintaxe para qualquer expressão
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
exl-id: ca1a52c1-b5bd-48bd-95cd-f8059913bd0a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 13%

---

# Sintaxe para qualquer expressão{#syntax-for-any-expression}

{{eol}}

Regras de sintaxe para fórmulas.

* Quando em uma fórmula, as palavras-chave fazem distinção entre maiúsculas e minúsculas e devem ser digitadas exatamente como aparecem.
* Quando em uma fórmula, métricas, dimensões e nomes de filtros que incluem espaços devem usar sublinhados entre palavras. Por exemplo: [!DNL Page_Views]
* Para cadeias de caracteres em expressões, você deve evitar aspas simples, aspas duplas e barras invertidas. Por exemplo:

   * [!DNL “can’t”] é aceitável e não precisa de ser evitada, mas [!DNL ‘can’t’] é inaceitável e deve ser evitado como [!DNL ‘can\’t’].

   * [!DNL c:\windows] deve ser evitado como [!DNL c:\\windows].
