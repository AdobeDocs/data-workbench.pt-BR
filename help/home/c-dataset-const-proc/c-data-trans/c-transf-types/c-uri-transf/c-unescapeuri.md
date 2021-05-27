---
description: A transformação do URI de escape evita o escape de qualquer caractere em uma string que foi escapada.
title: UnescapeURI
uuid: 25e87cc7-812d-4d77-be94-16093e8955fe
exl-id: abf20906-5052-4bbe-9ffb-522b850669a6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 6%

---

# UnescapeURI{#unescapeuri}

A transformação do URI de escape evita o escape de qualquer caractere em uma string que foi escapada.

>[!NOTE]
>
>Os caracteres com escape substituem os caracteres não seguros em uma string de URI. Eles são representados por um triplet que consiste em um sinal de porcentagem seguido por dois dígitos hexadecimais (por exemplo, %20).

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode inserir qualquer nome aqui. |  |
| Comentários | Opcional. Observações sobre a transformação. |  |
| Condição | Condições de aplicação desta transformação. |  |
| Padrão | O valor padrão a ser usado se a condição for atendida e o valor de entrada não estiver disponível. |  |
| Entrada | A cadeia de caracteres do URI a ser removida. |  |
| Saída | O nome do campo no qual a cadeia de caracteres sem escape deve ser armazenada. |  |

A transformação a seguir remove o escape do valor docname em um campo de cabeçalho HTTP e armazena a saída no campo x-docname-unescaped:

![](assets/cfg_TransformationType_UnescapeURI.png)

Se o valor de docname fosse

* [!DNL mysite.net/lending%20and%20leasing%20forms/document%20library/credit%20application.doc]

então o valor de x-docname-unescape seria

* [!DNL mysite.net/lending and leasing forms/document library/credit application.doc]
