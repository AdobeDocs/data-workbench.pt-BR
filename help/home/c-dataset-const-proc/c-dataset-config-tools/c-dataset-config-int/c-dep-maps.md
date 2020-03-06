---
description: Os mapas de dependência permitem que você visualize e gerencie a configuração dos componentes do seu perfil.
solution: Analytics
title: Mapas de dependência
topic: Data workbench
uuid: c869267c-5fa9-43b8-b4d4-06c7a36bfa8e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mapas de dependência{#dependency-maps}

Os mapas de dependência permitem que você visualize e gerencie a configuração dos componentes do seu perfil.

* **Componentes do conjunto de dados:** Registre fontes, filtros, campos, transformações e dimensões estendidas definidas em seus arquivos, arquivos [!DNL Log Processing.cfg][!DNL Transformation.cfg]e [!DNL dataset include] conjuntos de dados.

* **Componentes do modelo de consulta:** Métricas, dimensões e filtros definidos nas pastas Dimensões, Métricas e Filtros.
* **Espaços de trabalho e visualizações:** Espaços de trabalho, relatórios, opções de menu e camadas de globo.

Para obter mais informações sobre como trabalhar com componentes de modelo de consulta, espaços de trabalho e visualizações em mapas de dependência, consulte o Guia *do Usuário da Análise de* big data.

Os componentes do perfil são representados por pontos coloridos (nós) no mapa. As linhas que conectam os nós descrevem as dependências, ou seja, como os componentes se relacionam entre si. Uma linha entre dois nós significa que uma saída do nó à esquerda é uma entrada do nó à direita, ou seja, o nó direito depende do nó esquerdo.

## Exibindo Componentes de Conjunto de Dados {#section-3e51c09c23cc40aeade2e6ad0fa7c8d2}

1. Clique com o botão direito do mouse no mapa de dependência e clique em **[!UICONTROL Display]**.
1. Escolher **[!UICONTROL Dataset]**. Um X é exibido à esquerda de [!DNL Dataset].

Para obter mais informações sobre as outras opções de exibição, consulte o Guia *do Usuário da Análise de* big data.

A figura a seguir mostra um mapa de dependência cujos nós representam as fontes de log, campos, transformações e dimensões estendidas de um conjunto de dados.

![](assets/vis_DependencyMap.png)

* Um nó amarelo-verde representa uma ou mais fontes de log ou um filtro definido no conjunto de dados. Um nó para uma fonte de log sempre é exibido mais à esquerda no mapa.
* Um nó cinza representa um campo listado no parâmetro Campos em um [!DNL Log Processing.cfg] arquivo ou [!DNL Log Processing Include]arquivo.

* Um nó azul representa uma transformação.
* Um nó verde representa uma dimensão estendida.

>[!NOTE]
>
>Se o conjunto de dados tiver uma única fonte de log, o mapa exibirá a Fonte de Log: nome *da origem do* log. Se o conjunto de dados tiver várias fontes de log, o mapa exibirá o *número* de Fontes de Log, onde o número é a contagem de fontes de log. Por exemplo, se você tiver três fontes de log no conjunto de dados, o mapa exibirá 3 Fontes de Log.

Se não conseguir ver todos os nós no mapa, você pode mover o mapa, aumentar ou diminuir o zoom para exibir o mapa inteiro ou para focalizar em uma seção específica. Para obter mais informações sobre o zoom, consulte o capítulo Trabalhar com visualizações do Guia ** do usuário da Análise de big data.

Quando você clica em um nó, todos os nós que dependem desse nó e todos os nós dos quais esse nó depende são realçados e seus nomes são exibidos.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>Um caminho destacado em um mapa de dependência não constitui uma seleção.

Ao clicar com o botão direito do mouse em um nó, você pode ver informações de identificação sobre cada componente mostrado no mapa e escolher opções de menu que permitem exibir mais detalhes sobre o componente ou editar o componente. Além disso, é possível realizar pesquisas de texto e exibir informações de desempenho para transformações e dimensões estendidas.

Para obter informações sobre essas funções para mapas de dependência, consulte o capítulo Interfaces administrativas do Guia *do usuário da Análise de* big data.
