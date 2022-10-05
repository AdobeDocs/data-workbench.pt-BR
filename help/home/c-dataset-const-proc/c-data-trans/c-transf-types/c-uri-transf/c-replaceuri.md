---
description: A transformação ReplaceURI altera o valor na dimensão URI interna para um novo valor.
title: ReplaceURI
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
exl-id: 03a6f306-5e2e-488c-8d79-a14938dcd635
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 5%

---

# ReplaceURI{#replaceuri}

{{eol}}

A transformação ReplaceURI altera o valor na dimensão URI interna para um novo valor.

If [!DNL URI Prefix] for especificado, o valor resultante será simplesmente o prefixo URI concatenado com o valor de entrada fornecido.

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode inserir qualquer nome aqui. |  |
| Comentários | Opcional. Observações sobre a transformação. |  |
| Condição | Condições de aplicação desta transformação. |  |
| Padrão | O valor padrão a ser usado se a condição for atendida e o valor de entrada não estiver disponível. |  |
| Entrada | O valor para substituir o URI. |  |
| Prefixo URI | O valor (string) a ser anexado ao valor na variável [!DNL Input] campo. |  |

>[!NOTE]
>
>Antes de aplicar [!DNL ReplaceURI] transformações, você deve criar uma nova dimensão simples com um pai de [!DNL Page View]de uma cópia de cs-uri-stem ou cs-uri. Para obter ajuda com isso, entre em contato com o Adobe.

Este exemplo demonstra o uso de [!DNL ReplaceURI] para substituir &quot;page=*pageid*&quot; sequências de consulta com &quot; [!DNL homepage.html]&quot; *pageid* indica que a página inicial do site foi visualizada. O resultado final é uma exibição mais fácil de usar do URI.

![](assets/cfg_TransformationType_ReplaceURI.bmp)

Para a transformação mostrada, a página

* [!DNL www.examplesite.com/info.html?page=1550]

seria alterado para

* [!DNL www.examplesite.com/homepage.html]
