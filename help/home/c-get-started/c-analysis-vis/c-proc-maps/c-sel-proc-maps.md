---
description: É possível fazer seleções nos mapas de processo para criar filtros que incluam ou excluam dados associados a um nó específico.
solution: Analytics
title: Fazer uma seleção a partir de um mapa de processos
topic: Data workbench
uuid: 7fd00090-c9ab-4bb6-8584-7de7b6f4b68c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Fazer uma seleção a partir de um mapa de processos{#make-a-selection-from-a-process-map}

É possível fazer seleções nos mapas de processo para criar filtros que incluam ou excluam dados associados a um nó específico.

Fazer uma seleção dentro de um mapa de processo envolve a dimensão de grupo do mapa, que determina como os elementos da dimensão base (ou seja, os nós no mapa) são agrupados para formar as conexões entre nós.

>[!NOTE]
>
>É possível alterar a dimensão de grupo padrão para um mapa de processos. Consulte [Configurando Mapas](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6)de Processo.

Quando você faz uma seleção com base em um nó dentro de um mapa de processo, está selecionando todos os elementos da dimensão de grupo que envolveram esse nó. Para entender melhor a função da dimensão de grupo, considere os seguintes exemplos:

* Os filmes podem ser agrupados pelos visualizadores que os classificaram. Cada visualizador é um elemento da dimensão Usuário, de modo que a dimensão Usuário seria a dimensão de grupo para o mapa de processos. Quando você faz uma seleção de um nó para um filme específico, cria um filtro que mostra os dados para os usuários que classificaram ou não esse filme.
* As páginas do site podem ser agrupadas pelas sessões em que foram visualizadas. Cada sessão é um elemento da dimensão Sessão, de modo que a dimensão Sessão seria a dimensão de grupo para o mapa do processo. Quando você faz uma seleção de um nó para uma página específica, cria um filtro que mostra os dados das sessões durante as quais essa página foi ou não visualizada.

**Para fazer uma seleção**

1. Clique com o botão direito do mouse em qualquer nó em um mapa de processos.
1. Clique em uma das seguintes opções para fazer uma seleção com base no nó:

   * **[!UICONTROL Select]*** **[!UICONTROL group dimension name +s]*** **[!UICONTROL through node name]**: Filtra os dados para incluir todos os elementos da dimensão de grupo que passaram pelo nó filtrando todas as sessões que não passaram pelo nó.

   * **[!UICONTROL Select]*** **[!UICONTROL group dimension name +s]*** **[!UICONTROL NOT through node name]**: Filtra os dados para incluir todos os elementos da dimensão de grupo que não passaram pelo nó filtrando todas as sessões que passaram pelo nó.

![](assets/vis_2DProcessMap_Selections_Movie.png)

![](assets/vis_2DProcessMap_Selections_Page.png)

Quando você faz uma seleção em um mapa de processo 3D, o nó para o qual a seleção é feita é circulado. Os benchmarks são exibidos em cada barra, o que ajuda a comparar valores de métricas com e sem a seleção. Consulte [Compreensão de benchmarks](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).

![](assets/vis_3DProcessMap_Selection.png)

