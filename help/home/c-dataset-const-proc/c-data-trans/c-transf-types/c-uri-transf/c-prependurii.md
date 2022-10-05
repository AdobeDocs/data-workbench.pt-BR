---
description: Semelhante à transformação AppendURI , a transformação PrependURI afeta o campo interno usado pelo servidor do Data Workbench para criar a dimensão URI.
title: PrependURI
uuid: 3f2fb1a7-83f7-481e-b892-0937acd379f9
exl-id: c39d9241-ed66-446e-b59d-fdb11942d0e8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 6%

---

# PrependURI{#prependuri}

{{eol}}

Semelhante à transformação AppendURI , a transformação PrependURI afeta o campo interno usado pelo servidor do Data Workbench para criar a dimensão URI.

O [!DNL PrependURI] A transformação funciona adicionando o valor no campo de entrada identificado à frente do valor atualmente no URI.

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode inserir qualquer nome aqui. |  |
| Comentários | Opcional. Observações sobre a transformação. |  |
| Condição | Condições de aplicação desta transformação. |  |
| Padrão | O valor padrão a ser usado se a condição for atendida e o valor de entrada não estiver disponível. |  |
| Entrada | O nome do campo cujo valor é anexado ao URI. |  |

O exemplo a seguir simplesmente prepara o campo s-dns no URI, estendendo a representação da dimensão do URI para incluir o domínio solicitado pelo dispositivo cliente.

![](assets/cfg_TransformationType_PrependURI.png)

Neste exemplo, anexando o campo s-dns ao URI

* [!DNL /modelview.asp&id=login]

resulta no seguinte URL:

* [!DNL www.adobe.com/modelview.asp?id=login]

Agora, o URI é estendido para incluir o domínio solicitado.
