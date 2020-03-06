---
description: Semelhante à transformação AppendURI, a transformação PrependURI afeta o campo interno usado pelo servidor da análise de big data para construir a dimensão URI.
solution: Analytics
title: PrependURI
topic: Data workbench
uuid: 3f2fb1a7-83f7-481e-b892-0937acd379f9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# PrependURI{#prependuri}

Semelhante à transformação AppendURI, a transformação PrependURI afeta o campo interno usado pelo servidor da análise de big data para construir a dimensão URI.

A [!DNL PrependURI] transformação funciona adicionando o valor no campo de entrada identificado à frente do valor atualmente no URI.

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode digitar qualquer nome aqui. |  |
| Comentários | Opcional. Notas sobre a transformação. |  |
| Condição | As condições em que essa transformação é aplicada. |  |
| Padrão | O valor padrão a ser usado se a condição for cumprida e o valor de entrada não estiver disponível. |  |
| Entrada | O nome do campo cujo valor é anexado ao URI. |  |

O exemplo a seguir simplesmente abre o campo s-dns no URI, estendendo a representação da dimensão URI para incluir o domínio solicitado pelo dispositivo cliente.

![](assets/cfg_TransformationType_PrependURI.png)

Neste exemplo, como antecipar o campo s-dns para o URI

* [!DNL /modelview.asp&id=login]

resulta no seguinte URL:

* [!DNL www.adobe.com/modelview.asp?id=login]

Agora, o URI é estendido para incluir o domínio solicitado.
