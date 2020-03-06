---
description: Regras de sintaxe para fórmulas.
solution: Analytics
title: Sintaxe para qualquer expressão
topic: Data workbench
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sintaxe para qualquer expressão{#syntax-for-any-expression}

Regras de sintaxe para fórmulas.

* Quando em uma fórmula, as palavras-chave fazem distinção entre maiúsculas e minúsculas e devem ser digitadas exatamente como aparecem.
* Quando em uma fórmula, os nomes de métrica, dimensão e filtro que incluem espaços devem usar sublinhados entre palavras. Por exemplo: [!DNL Page_Views]
* Para sequências de caracteres em expressões, você deve escapar de algumas aspas simples, aspas duplas e barras invertidas. Por exemplo:

   * [!DNL “can’t”] é aceitável e não precisa de ser escapada, mas [!DNL ‘can’t’] é inaceitável e tem de ser escapada como [!DNL ‘can\’t’].

   * [!DNL c:\windows] deve ser escapada como [!DNL c:\\windows].

