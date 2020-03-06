---
description: A transformação do URI Unescape evita a escape de todos os caracteres em uma string que foram escapados.
solution: Analytics
title: UnescapeURI
topic: Data workbench
uuid: 25e87cc7-812d-4d77-be94-16093e8955fe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# UnescapeURI{#unescapeuri}

A transformação do URI Unescape evita a escape de todos os caracteres em uma string que foram escapados.

>[!NOTE]
>
>Os caracteres com escape substituem os caracteres não seguros em uma string de URI. Eles são representados por um triplete que consiste em um sinal de porcentagem seguido por dois dígitos hexadecimais (por exemplo, %20).

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode digitar qualquer nome aqui. |  |
| Comentários | Opcional. Notas sobre a transformação. |  |
| Condição | As condições em que essa transformação é aplicada. |  |
| Padrão | O valor padrão a ser usado se a condição for cumprida e o valor de entrada não estiver disponível. |  |
| Entrada | A string de URI a ser sem escape. |  |
| Saída | O nome do campo no qual a sequência de caracteres sem escape deve ser armazenada. |  |

A transformação a seguir não escapa do valor docname em um campo de cabeçalho HTTP e armazena a saída no campo x-docname-unescape:

![](assets/cfg_TransformationType_UnescapeURI.png)

Se o valor do docname fosse

* [!DNL mysite.net/lending%20and%20leasing%20forms/document%20library/credit%20application.doc]

então o valor de x-docname-unescape seria

* [!DNL mysite.net/lending and leasing forms/document library/credit application.doc]

