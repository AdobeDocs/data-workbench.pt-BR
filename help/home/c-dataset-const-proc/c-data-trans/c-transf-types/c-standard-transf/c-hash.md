---
description: A transformação Hash cria uma string quase exclusiva que representa um número de 64 bits a partir dos valores de entrada.
title: Hash
uuid: 13bc14e6-75e2-4711-8f98-50fd18802be5
exl-id: 6912a1d2-9ae8-42ba-94bd-a7a28cbdfae6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 4%

---

# Hash{#hash}

A transformação Hash cria uma string quase exclusiva que representa um número de 64 bits a partir dos valores de entrada.

Essa transformação fornece o mesmo valor de hash quando são fornecidas as mesmas entradas.

>[!NOTE]
>
>O valor resultante é quase exclusivo porque a transformação usa um número de 64 bits como o espaço de possíveis valores de hash. Para um milhão de entradas exclusivas para a transformação [!DNL hash], há uma chance de 1 em 38.000.000 de obter um valor de hash duplicado.

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode inserir qualquer nome aqui. |  |
| Comentários | Opcional. Observações sobre a transformação. |  |
| Condição | Condições de aplicação desta transformação. |  |
| Padrão | O valor padrão a ser usado se o valor de entrada não estiver disponível. |  |
| Entradas | O conjunto de entradas a ser usado para criar o valor de hash. |  |
| Saída | O nome do campo para saída. |  |

Neste exemplo, os valores dos campos c-ip e cs(user-agent) são usados para criar uma ID de rastreamento, que é armazenada no campo x-trackingid .

![](assets/cfg_TransformationType_Hash.png)

>[!NOTE]
>
>Este exemplo não representa uma solução ideal para a criação de IDs de rastreamento exclusivas. No entanto, em situações em que as informações do log de arquivamento são usadas, esse pode ser o melhor método.
