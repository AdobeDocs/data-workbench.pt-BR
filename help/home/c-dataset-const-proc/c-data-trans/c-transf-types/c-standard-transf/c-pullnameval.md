---
description: A transformação PullNameValues é uma operação especial que utiliza os valores no campo de consulta cs-uri e separa cada um dos pares nome-valor em uma sequência separada.
solution: Analytics
title: PullNameValues
topic: Data workbench
uuid: b24db987-78e8-4afc-9113-89aedc0170b2
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# PullNameValues{#pullnamevalues}

A transformação PullNameValues é uma operação especial que utiliza os valores no campo de consulta cs-uri e separa cada um dos pares nome-valor em uma sequência separada.

A coleção inteira de sequências de caracteres de par nome-valor é saída no campo de saída especificado como um vetor de sequências de caracteres.

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode digitar qualquer nome aqui. |  |
| Comentários | Opcional. Notas sobre a transformação. |  |
| Condição | As condições em que essa transformação é aplicada. |  |
| Padrão | O valor padrão a ser usado se a condição for atendida e o valor de entrada não estiver disponível na entrada de log fornecida. |  |
| Saída | O nome da string de saída. |  |

A [!DNL PullNameValues] transformação é usada neste exemplo para capturar o uso do formulário de pesquisa pelos visitantes: quais botões foram selecionados, quais valores foram digitados no formulário e assim por diante. O exemplo usa uma [!DNL String Match] condição (consulte [Condições](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) para isolar o uso dessa transformação somente na página [!DNL /search.php]. O vetor dos pares nome-valor é produzido no campo x-search-namevaluate.

![](assets/cfg_TransformationType_PullNameValues.png)

Usando a transformação conforme definido acima, se o campo cs-uri-stem correspondesse à página [!DNL /search.php] e cs-uri-query contivesse o seguinte:

* Procurar por=Bob&amp;State=Virginia&amp;isMale=true

em seguida, os valores de x-search-names conteriam um vetor contendo as três strings a seguir:

* Procurar=Bob
* Estado=Virgínia
* isMale=true

