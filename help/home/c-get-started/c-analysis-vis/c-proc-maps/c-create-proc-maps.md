---
description: Você pode criar mapas de processos 2D e 3D arrastando e soltando elementos de gráficos de barras, tabelas e visualizações de hierarquia em um mapa em branco.
title: Criar um mapa de processos
uuid: dbcde637-0411-4296-99ca-5510e0285e4b
exl-id: 2e417a8e-5b1c-4dce-9e4e-ac7ed044564c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 1%

---

# Criar um mapa de processos{#create-a-process-map}

Você pode criar mapas de processos 2D e 3D arrastando e soltando elementos de gráficos de barras, tabelas e visualizações de hierarquia em um mapa em branco.

Os elementos que você pode adicionar devem ser elementos da dimensão base do mapa de processos. Também é possível arrastar e soltar nós de um mapa de processos para outro, desde que os mapas estejam usando a mesma dimensão base. Além disso, o mapa inteiro pode ser ampliado ou movido para se concentrar em um nó específico, ou pode ser alterado para outros tipos de visualização. Consulte [Zoom em Visualizações](../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530).

**Para adicionar elementos a um mapa de processos usando uma tabela ou gráfico de barras**

* Em qualquer tabela ou gráfico de barras com a mesma dimensão base do mapa de processos, pressione Ctrl+Alt enquanto clica e arrasta elementos individuais para o mapa de processos. O cursor do mouse exibe a palavra &quot;Não&quot; até que o mouse chegue ao mapa de processos.

   >[!NOTE]
   >
   >Os elementos que você pode adicionar devem ser elementos da dimensão base do mapa de processos.

   ![](assets/vis_2DProcessMap_addPages.png)

**Para adicionar elementos a um mapa de processos usando uma exibição de hierarquia**

>[!NOTE]
>
>O Adobe recomenda adicionar nós do nível mais alto da hierarquia que você está analisando.

1. Em qualquer tabela ou gráfico de barras com a mesma dimensão base do mapa de processos, clique com o botão direito do mouse em um elemento ou no rótulo da dimensão base e clique em **[!UICONTROL Hierarchy View]**.
1. Pressione Ctrl+Alt enquanto você clica e arrasta os elementos para o mapa de processos. O cursor do mouse exibe a palavra &quot;Não&quot; até que o mouse chegue ao mapa.

   >[!NOTE]
   >
   >Os elementos que você pode adicionar devem ser elementos da dimensão base do mapa de processos.

   Arrastar um único elemento para um mapa de processos cria um nó de mapa somente para esse elemento, mas se você selecionar vários elementos (um grupo) ou uma pasta contendo vários elementos, arrastar da hierarquia cria um único nó para esse grupo ou pasta. Por exemplo, se você estiver trabalhando com dados do site, arrastar uma pasta chamada [!DNL site.com/cgi-bin] em um mapa faz um nó chamado [!DNL site.com/cgi-bin/*], que representa todas as páginas e diretórios que são filhos dessa pasta.

Para obter mais informações sobre exibições de hierarquia de página, consulte [Aplicando Exibições de Hierarquia](../../../../home/c-get-started/c-analysis-vis/c-tables/c-hier-vews.md#concept-b461183424a841eb94f8143a0eaf9bff).

**Para adicionar nós a um mapa de processos a partir de outro mapa de processos**

>[!NOTE]
>
>Os mapas de processo devem ter a mesma dimensão base.

* Copie um nó do primeiro para o segundo mapa de processos usando os seguintes métodos:

   * Para copiar nós individuais, clique e arraste cada nó até o segundo mapa de processos.
   * Para copiar vários nós, clique e arraste com a tecla Ctrl pressionada para criar uma caixa ao redor dos nós que deseja copiar, em seguida, clique e arraste os nós realçados para o segundo mapa de processos. Todos os nós realçados são copiados para o segundo mapa de processos.
