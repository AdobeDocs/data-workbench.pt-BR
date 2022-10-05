---
description: A transformação Tokenize aplica uma expressão regular à sequência de caracteres de entrada.
title: Tokenize
uuid: f8430e6c-ec14-4ba6-aeae-92c9f2520a63
exl-id: c1f39b5b-4717-44f6-99c7-4e6a215f3542
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 4%

---

# Tokenize{#tokenize}

{{eol}}

A transformação Tokenize aplica uma expressão regular à sequência de caracteres de entrada.

No entanto, difere de [!DNL RETransform], [!DNL Tokenize] não precisa corresponder à string inteira: a expressão regular usada para a variável [!DNL Tokenize] transformação pode corresponder a um subconjunto da entrada. Depois que uma correspondência é encontrada, [!DNL Tokenize] aplica a expressão regular novamente, iniciando no caractere após o fim da última correspondência.

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode inserir qualquer nome aqui. |  |
| Diferenciação de maiúsculas e minúsculas | Verdadeiro ou falso. Especifica se a correspondência faz distinção entre maiúsculas e minúsculas. |  |
| Comentários | Opcional. Observações sobre a transformação. |  |
| Condição | Condições de aplicação desta transformação. |  |
| Padrão | O valor padrão a ser usado se a condição for atendida e o valor de entrada não estiver disponível ou a expressão regular não corresponder ao valor de entrada. |  |
| Expressão | A expressão regular usada para correspondência. |  |
| Saídas | Os nomes das cadeias de caracteres de saída. É possível ter várias saídas para uma determinada string de entrada. O número de saídas deve corresponder ao número de subpadrões de captura na expressão regular. |  |

No exemplo a seguir, a variável [!DNL Tokenize] a transformação usa uma expressão regular para capturar os nomes das cadeias de caracteres de consulta (em cs-uri-query) e exibir o subpadrão capturado (o nome da consulta) como x-pull-query-name.

![](assets/cfg_TransformationType_Tokenize.png)

Para a sequência de consulta &quot;a=b&amp;c=d&quot;, a saída seria um vetor contendo &quot;a&quot; e &quot;c.&quot;

Para obter informações sobre expressões regulares, consulte [Expressões regulares](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).
