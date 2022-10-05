---
description: A transformação PullNameValues é uma operação especial que utiliza os valores no campo de consulta cs-uri e separa cada um dos pares nome-valor em uma string separada.
title: PullNameValues
uuid: b24db987-78e8-4afc-9113-89aedc0170b2
exl-id: 3660ff6e-87dc-42cf-a897-0e2e0e021c07
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 4%

---

# PullNameValues{#pullnamevalues}

{{eol}}

A transformação PullNameValues é uma operação especial que utiliza os valores no campo de consulta cs-uri e separa cada um dos pares nome-valor em uma string separada.

A coleção inteira de sequências de par nome-valor é de saída no campo de saída especificado como um vetor de sequências de caracteres.

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode inserir qualquer nome aqui. |  |
| Comentários | Opcional. Observações sobre a transformação. |  |
| Condição | Condições de aplicação desta transformação. |  |
| Padrão | O valor padrão a ser usado se a condição for atendida e o valor de entrada não estiver disponível na entrada de log fornecida. |  |
| Saída | O nome da string de saída. |  |

O [!DNL PullNameValues] a transformação é usada neste exemplo para capturar o uso do formulário de pesquisa pelos visitantes: quais botões foram selecionados, quais valores foram digitados no formulário e assim por diante. O exemplo usa um [!DNL String Match] (consulte [Condições](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) para isolar o uso dessa transformação somente na página [!DNL /search.php]. O vetor de pares nome-valor é emitido no campo x-search-namvalues.

![](assets/cfg_TransformationType_PullNameValues.png)

Usando a transformação conforme definido acima, se o campo cs-uri-stem correspondeu à página [!DNL /search.php] e cs-uri-query continha o seguinte:

* Pesquisar por=Bob&amp;State=Virginia&amp;isMale=true

em seguida, x-search-namvalues conteria um vetor contendo as três strings a seguir:

* Pesquisar por=Bob
* Estado=Virgínia
* isMale=true
