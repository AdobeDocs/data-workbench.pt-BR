---
description: Visualizações são elementos adicionados à tela do painel e configurados para exibir várias métricas e dados baseados em dimensão.
title: Visualizações
uuid: 1e15de30-7761-422a-a836-7a1b49b58daf
exl-id: 7e8b23cd-5e95-4cd5-b07e-3aa53f26fac7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 3%

---

# Visualizações{#visualizations}

Visualizações são elementos adicionados à tela do painel e configurados para exibir várias métricas e dados baseados em dimensão.

Todos os painéis são compostos de uma ou mais visualizações. Cada visualização pode ser criada, removida, redimensionada e reconfigurada independentemente de todas as outras visualizações na tela do painel.

As visualizações também são interativas, permitindo que os usuários segmentem dados rapidamente fazendo seleções em um ou mais elementos de dados na visualização. As seleções feitas em uma visualização aplicarão dinamicamente os filtros em tempo real a outras visualizações na tela. Isso renderiza os mesmos dados em todas as visualizações na tela.

Há oito tipos diferentes de visualizações. Cada uma pode ser adicionada, redimensionada, configurada e removida independentemente de qualquer outra visualização. As visualizações exibem dados definidos no Data Workbench por um arquiteto do Data Workbench.

Os oito tipos de visualizações disponíveis incluem:

* Gráficos de coluna
* Gráficos de barras
* Gráficos de linha
* Tabelas
* Legendas de métricas
* Gráficos de Pizza
* Gráficos de dispersão
* Texto formatado

## Interface do usuário de visualização {#section-54a73865f00742268340cf9123d6c590}

A parte de cabeçalho da visualização contém o título da visualização e as ferramentas de visualização, que variam de acordo com o tipo e o estado da visualização. O corpo da visualização contém o conteúdo e depende do tipo e da configuração da visualização que está sendo exibida. As ferramentas de visualização só aparecem quando o mouse entra na janela de visualização. Caso contrário, estarão ocultas.

![](assets/visualization.png)

* Título da visualização. Descreve esta visualização. O título é gerado automaticamente ou substituído manualmente por um título personalizado.
* Valor exibido. Para a dimensão que está sendo visualizada, o exibe a quantidade de dados mostrada em comparação à quantidade total disponível.
* Indicador de amostra. Mostrado quando os dados visualizados são uma amostra e não um resultado de query 100% completo.
* Ferramentas de visualização. Executa operações específicas nas visualizações. As ferramentas disponíveis dependem do tipo de visualização, do estado e das permissões de usuário atuais.
* Corpo da visualização. Exibe os dados da visualização como configurado. Essa área é interativa e depende do tipo de visualização que está sendo exibido.
