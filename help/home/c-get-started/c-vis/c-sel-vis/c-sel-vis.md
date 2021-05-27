---
description: Selecionar elementos em uma visualização filtra dinamicamente o conjunto de dados.
title: Fazer seleções em visualizações
uuid: 3900354f-826b-41e8-9bc2-e4856928bad5
exl-id: bb1dd7e4-a9f8-48b5-a12d-433c601b455b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 3%

---

# Fazer seleções em visualizações{#make-selections-in-visualizations}

Selecionar elementos em uma visualização filtra dinamicamente o conjunto de dados.

Quando você faz uma seleção em uma visualização, todas as outras visualizações no espaço de trabalho são atualizadas automaticamente para refletir os dados associados somente aos elementos selecionados.

O espaço de trabalho a seguir mostra uma tabela de Filme na qual o filme *Coquetel* está selecionado. No espaço de trabalho, a tabela Pontuação e a legenda da métrica filtram automaticamente suas exibições para o elemento selecionado (ou seja, suas exibições refletem os dados do filme *Cocktail*).

![](assets/wsp_selection_Basic.png)

Como mostrado no exemplo acima, quando uma seleção é feita, um brilho aparece ao redor da visualização e os elementos não selecionados dentro dessa visualização escurecem. Para facilitar as comparações com o conjunto de dados completo, linhas brancas estreitas chamadas de benchmarks aparecem no gráfico de barras para marcar a forma dos dados originais não filtrados. Para obter mais informações sobre benchmarks, consulte [Noções básicas sobre benchmarks](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).

**Para fazer uma seleção**

É possível fazer seleções em qualquer visualização que exiba pelo menos uma dimensão, exceto gráficos de dispersão e legendas.

Use o mouse e as sequências de teclas a seguir para selecionar os elementos desejados:

| Para... | Usar esta sequência... |
|---|---|
| Selecionar um único elemento | Clique em |
| Selecionar um intervalo de elementos | Clique+arrastar |
| Adicionar um elemento à seleção atual | Ctrl+clique |
| Limpar uma única seleção | Shift+clique |
| Limpar todas as seleções (ou seja, selecionar novamente todos os elementos) | Clique com o botão direito do mouse em qualquer valor na visualização |

**Para limpar uma seleção**

Use o mouse e as sequências de teclas a seguir para limpar uma seleção:

| Para | Usar esta sequência... |
|---|---|
| Limpar uma única seleção | Shift+clique |
| Limpar todas as seleções (ou seja, selecionar novamente todos os elementos) | Clique com o botão direito do mouse em qualquer valor na visualização |
