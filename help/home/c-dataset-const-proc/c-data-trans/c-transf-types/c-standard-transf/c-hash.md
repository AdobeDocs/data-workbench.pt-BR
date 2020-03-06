---
description: A transformação Hash cria uma string quase exclusiva que representa um número de 64 bits dos valores de entrada.
solution: Analytics
title: Hash
topic: Data workbench
uuid: 13bc14e6-75e2-4711-8f98-50fd18802be5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Hash{#hash}

A transformação Hash cria uma string quase exclusiva que representa um número de 64 bits dos valores de entrada.

Essa transformação fornece o mesmo valor de hash quando as mesmas entradas são fornecidas.

>[!NOTE]
>
>O valor resultante é quase exclusivo porque a transformação usa um número de 64 bits como o espaço de possíveis valores de hash. Para um milhão de entradas únicas para a [!DNL hash] transformação, há uma chance de 1 em 38.000.000 de obter um valor de hash duplicado.

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode digitar qualquer nome aqui. |  |
| Comentários | Opcional. Notas sobre a transformação. |  |
| Condição | As condições em que essa transformação é aplicada. |  |
| Padrão | O valor padrão a ser usado se o valor de entrada não estiver disponível. |  |
| Entradas | O conjunto de entradas a ser usado para criar o valor de hash. |  |
| Saída | O nome do campo para saída. |  |

Neste exemplo, os valores dos campos c-ip e cs(user-agent) são usados para criar uma ID de rastreamento, que é armazenada no campo x-trackingid.

![](assets/cfg_TransformationType_Hash.png)

>[!NOTE]
>
>Este exemplo não representa uma solução ideal para a criação de IDs de rastreamento exclusivas. No entanto, em situações em que as informações do log de arquivamento são usadas, esse pode ser o melhor método.

