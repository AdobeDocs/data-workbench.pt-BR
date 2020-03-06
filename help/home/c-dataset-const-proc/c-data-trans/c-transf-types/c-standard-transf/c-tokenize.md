---
description: A transformação Tokenize aplica repetidamente uma expressão regular contra a string de entrada.
solution: Analytics
title: Tokenize
topic: Data workbench
uuid: f8430e6c-ec14-4ba6-aeae-92c9f2520a63
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Tokenize{#tokenize}

A transformação Tokenize aplica repetidamente uma expressão regular contra a string de entrada.

No entanto, diferentemente [!DNL RETransform], [!DNL Tokenize] não precisa corresponder à string inteira: a expressão regular usada para a [!DNL Tokenize] transformação pode corresponder a um subconjunto da entrada. Depois que uma correspondência é encontrada, [!DNL Tokenize] aplica a expressão regular novamente, começando pelo caractere após o final da última correspondência.

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode digitar qualquer nome aqui. |  |
| Diferenciação de maiúsculas e minúsculas | Verdadeiro ou falso. Especifica se a correspondência faz distinção entre maiúsculas e minúsculas. |  |
| Comentários | Opcional. Notas sobre a transformação. |  |
| Condição | As condições em que essa transformação é aplicada. |  |
| Padrão | O valor padrão a ser usado se a condição for cumprida e o valor de entrada não estiver disponível ou a expressão regular não corresponder ao valor de entrada. |  |
| Expressão | A expressão regular usada para correspondência. |  |
| Saídas | Os nomes das strings de saída. É possível ter várias saídas para uma determinada string de entrada. O número de saídas deve corresponder ao número de subpadrões de captura na expressão regular. |  |

No exemplo a seguir, a [!DNL Tokenize] transformação usa uma expressão regular para capturar os nomes das strings de consulta (em cs-uri-query) e exibir o subpadrão capturado (o nome da consulta) como x-pull-query-name.

![](assets/cfg_TransformationType_Tokenize.png)

Para a string de consulta &quot;a=b&amp;c=d&quot;, a saída seria um vetor contendo &quot;a&quot; e &quot;c.&quot;

Para obter informações sobre expressões regulares, consulte Expressões [regulares](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).
