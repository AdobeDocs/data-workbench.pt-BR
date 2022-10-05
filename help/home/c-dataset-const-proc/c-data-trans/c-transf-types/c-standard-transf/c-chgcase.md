---
description: A transformação ChangeCase altera as letras maiúsculas e minúsculas da string no parâmetro Input , conforme especificado pelo parâmetro Action .
title: ChangeCase
uuid: 676e79e6-324e-43d1-8982-b44596d0eeac
exl-id: 2002fe22-d31c-4286-9f73-59ef205f1384
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 8%

---

# ChangeCase{#changecase}

{{eol}}

A transformação ChangeCase altera as letras maiúsculas e minúsculas da string no parâmetro Input , conforme especificado pelo parâmetro Action .

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode inserir qualquer nome aqui. |  |
| Ação | Superior ou inferior. Especifica se a caixa deve ser alterada para superior ou inferior. | lower |
| Comentários | Opcional. Observações sobre a transformação. |  |
| Condição | Condições de aplicação desta transformação. |  |
| Entrada | O nome do campo da entrada de log a ser usada como entrada. |  |
| Saída | O nome do campo de saída. |  |

Neste exemplo, que usa campos de dados coletados do tráfego do site, o caso da cadeia de caracteres no campo s-dns é alterado para minúsculas e o novo valor é emitido no novo campo, x-lowercase-dns.

![](assets/cfg_TransformationType_ChangeCase.png)
