---
description: Os mapas de dependência permitem visualizar e gerenciar a configuração dos componentes do seu perfil.
title: Mapas de dependências
uuid: c869267c-5fa9-43b8-b4d4-06c7a36bfa8e
exl-id: 4618c735-f507-4abc-a4b4-d52a37c64c60,733407ca-3326-406a-a642-a3ea3d3f6b8b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 1%

---

# Mapas de dependências{#dependency-maps}

Os mapas de dependência permitem visualizar e gerenciar a configuração dos componentes do seu perfil.

* **Componentes do conjunto de dados:** Fontes de registro, filtros, campos, transformações e dimensões estendidas definidas nos  [!DNL Log Processing.cfg],  [!DNL Transformation.cfg]e  [!DNL dataset include] arquivos do conjunto de dados.

* **Componentes do modelo de query:**  métricas, dimensões e filtros definidos nas pastas Dimension, Métricas e Filtros.
* **Espaços de trabalho e visualizações:**  espaços de trabalho, relatórios, opções de menu e camadas de globo.

Para obter mais informações sobre como trabalhar com componentes de modelo de consulta, espaços de trabalho e visualizações em mapas de dependência, consulte o *Guia de Usuário do Data Workbench*.

Os componentes do perfil são representados por pontos coloridos (nós) no mapa. As linhas que conectam os nós descrevem dependências, ou seja, como os componentes se relacionam entre si. Uma linha entre dois nós significa que uma saída do nó à esquerda é uma entrada do nó à direita, ou seja, o nó à direita depende do nó à esquerda.

## Exibir componentes do conjunto de dados {#section-3e51c09c23cc40aeade2e6ad0fa7c8d2}

1. Clique com o botão direito do mouse no mapa de dependências e clique em **[!UICONTROL Display]**.
1. Escolher **[!UICONTROL Dataset]**. Um X é exibido à esquerda de [!DNL Dataset].

Para obter mais informações sobre as outras opções de exibição, consulte o *Guia do Usuário do Data Workbench*.

A figura a seguir mostra um mapa de dependência cujos nós representam as fontes de log de um conjunto de dados, campos, transformações e dimensões estendidas.

![](assets/vis_DependencyMap.png)

* Um nó amarelo-verde representa uma ou mais fontes de log ou um filtro definido no conjunto de dados. Um nó para uma fonte de log sempre é exibido mais à esquerda no mapa.
* Um nó cinza representa um campo listado no parâmetro Campos em um arquivo [!DNL Log Processing.cfg] ou [!DNL Log Processing Include].

* Um nó azul representa uma transformação.
* Um nó verde representa uma dimensão estendida.

>[!NOTE]
>
>Se o conjunto de dados tiver uma única fonte de log, o mapa exibirá Fonte de Log: *nome da fonte de log*. Se seu conjunto de dados tiver várias fontes de log, o mapa exibirá *número* Fontes de Log, onde número é a contagem de fontes de log. Por exemplo, se você tiver três fontes de log em seu conjunto de dados, seu mapa exibirá três Fontes de Log.

Se não conseguir ver todos os nós no mapa, você pode mover o mapa, aumentar ou diminuir o zoom para exibir o mapa inteiro ou para se concentrar em uma seção específica. Para obter mais informações sobre zoom, consulte o capítulo Trabalhar com visualizações do *Guia do usuário do Data Workbench*.

Quando você clica em um nó, todos os nós que dependem desse nó e todos os nós dos quais esse nó depende são realçados e seus nomes são exibidos.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>Um caminho destacado em um mapa de dependência não constitui uma seleção.

Ao clicar com o botão direito do mouse em um nó, é possível ver as informações de identificação sobre cada componente mostrado no mapa e escolher as opções de menu que permitem exibir mais detalhes sobre o componente ou editar o componente. Além disso, você pode realizar pesquisas de texto e exibir informações de desempenho para transformações e dimensões estendidas.

Para obter informações sobre essas funções para mapas de dependência, consulte o capítulo Interfaces Administrativas do *Guia do Usuário do Data Workbench*.
