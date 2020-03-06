---
description: A transformação ChangeCase altera as letras maiúsculas e minúsculas da string no parâmetro Input, conforme especificado pelo parâmetro Action.
solution: Analytics
title: ChangeCase
topic: Data workbench
uuid: 676e79e6-324e-43d1-8982-b44596d0eeac
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ChangeCase{#changecase}

A transformação ChangeCase altera as letras maiúsculas e minúsculas da string no parâmetro Input, conforme especificado pelo parâmetro Action.

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode digitar qualquer nome aqui. |  |
| Ação | Superior ou inferior. Especifica se a caixa deve ser alterada para superior ou inferior. | lower |
| Comentários | Opcional. Notas sobre a transformação. |  |
| Condição | As condições em que essa transformação é aplicada. |  |
| Entrada | O nome do campo da entrada do registro a ser usado como entrada. |  |
| Saída | O nome do campo de saída. |  |

Neste exemplo, que usa campos de dados coletados do tráfego do site, o caso da string no campo s-dns é alterado para letra minúscula e o novo valor é gerado no novo campo, x-lowercase-dns.

![](assets/cfg_TransformationType_ChangeCase.png)

