---
description: Um navegador de caminho permite analisar a sequência em que os elementos de uma determinada dimensão foram acessados.
title: Navegadores de caminho
uuid: 548091dc-935f-41ac-b67c-39080988f1ea
exl-id: 563cf0e3-39d7-49b7-b808-b0233169fb1a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 0%

---

# Navegadores de caminho{#path-browsers}

Um navegador de caminho permite analisar a sequência em que os elementos de uma determinada dimensão foram acessados.

Você cria um navegador de caminho arrastando e soltando um elemento de uma dimensão em uma visualização de navegador de caminho em branco. O elemento que você arrasta e solta no navegador de caminho se torna a raiz do navegador de caminho. O navegador de caminho exibe caminhos que passam pela raiz, permitindo que você veja a sequência de elementos que foram acessados antes e depois da raiz.

O navegador de caminho a seguir mostra a sequência de filmes que os visualizadores classificaram antes e depois de classificar o filme *O Aviador*, que é a raiz do navegador de caminho. Cada nome de filme é um elemento da dimensão Filme, que é definida em um conjunto de dados que consiste em dados de filme que inclui nomes de filmes e classificações dos visualizadores desses filmes.

![](assets/vis_PathBrowser_Movies.png)

Você pode criar navegadores de caminho para mostrar a sequência em que os elementos de qualquer dimensão no conjunto de dados foram acessados. Por exemplo, se você estiver trabalhando com dados do site, é possível criar um navegador de caminho que mostra a sequência de páginas do site que foram acessadas antes e depois da raiz de cada sessão em que a raiz foi visualizada ou para cada visitante do site que visualizou a raiz.

![](assets/vis_PathBrowser_Pages.png)

Cada navegador de caminho tem uma dimensão base associada, dimensão de grupo, dimensão de nível e métrica, que fornece chaves para interpretar os dados mostrados no navegador de caminho.

* **Dimensão básica:** ao arrastar e soltar um elemento raiz no navegador de caminho, você está arrastando e soltando um elemento da dimensão base. Todos os outros elementos que aparecem nos caminhos são elementos da dimensão base. Você pode alterar a dimensão base arrastando e soltando um elemento de outra dimensão no navegador de caminho.
* **Dimensão de nível:** cada dimensão no conjunto de dados tem uma dimensão de nível associada (também chamada de principal). A dimensão de nível do navegador de caminho deve ser a mesma dimensão de nível (ou pai) da dimensão base do navegador de caminho. Uma dimensão de nível do navegador de caminho é importante por dois motivos principais:

   * À medida que você segue um caminho de um elemento de dimensão básico para o próximo, você move de um elemento de dimensão de nível para o próximo. Por exemplo, suponha que você tenha criado um navegador de caminho mostrando páginas de um site. Cada página é um elemento da dimensão Página e a dimensão de nível para Página é Exibição de página. À medida que você muda de uma página para outra, você muda de uma exibição de página para outra.
   * Ao selecionar um caminho de elementos de dimensão base em um navegador de caminho, você está selecionando dados para os elementos correspondentes da dimensão de nível. A seleção sempre inclui os elementos da dimensão de nível que estão relacionados à raiz e é refinada adicionando mais elementos ao caminho. Por exemplo, ao selecionar um caminho de páginas, como raiz > A > B, você está selecionando dados para as exibições de página associadas à raiz, onde a próxima página é A e a próxima é B.

      Para obter informações sobre como selecionar um caminho em um navegador de caminho, consulte [Selecionar caminhos](../../../../home/c-get-started/c-analysis-vis/c-path-browsers/t-sel-paths.md#task-bf44d08c71954ef2adec4b82f840adeb). Para obter informações sobre seleções, consulte [Fazer seleções em visualizações](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).
   >[!NOTE]
   >
   >O navegador de caminho ignora os elementos da dimensão de nível sem elementos de dimensão base associados. Essa situação pode ocorrer ao criar um navegador de caminho a partir de um mapa de processos. Consulte [Criação de navegadores de caminho](../../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-create-path-browsers.md#concept-e120de6a740d4b6f98dda9e2b638f6ff).

* **Dimensão de grupo:** a dimensão de grupo determina como os elementos da dimensão de nível são agrupados para formar os caminhos de um navegador de caminho. Especificamente, os elementos de dimensão de nível associados a um único caminho em um navegador de caminho não podem abranger mais de um elemento de uma dimensão de grupo.

   Para entender isso, considere um exemplo de uso de dados da Web. Suponha que as dimensões base, nível e grupo do navegador de caminho sejam Página, Exibição de página e Sessão, respectivamente. Um caminho no navegador de caminho mostra a sequência de página A > B > C. A dimensão do grupo (Sessão) informa que as exibições de página (elementos da dimensão Exibição de página) associadas à sequência de página A > B > C ocorreram durante qualquer sessão única. É importante observar que pode haver várias sessões durante as quais houve exibições de página para a sequência de página A > B > C. Portanto, o caminho que mostra a sequência de página A > B > C representa todas as sessões individuais nas quais ocorreram as exibições de página para essa sequência.

* **Métrica**: A espessura do caminho que leva a um determinado elemento é proporcional ao valor da métrica para esse elemento. Caminhos mais grossos indicam valores de métrica maiores que caminhos mais finos.

O rótulo no canto superior esquerdo do navegador de caminho nomeia as dimensões base e de grupo representadas na visualização. O nome da dimensão de nível não é visível na visualização do navegador de caminho. O rótulo assume o formato &quot;Sequência de *nome da dimensão base*+s para cada *nome da dimensão do grupo*.&quot; Por exemplo, o rótulo Sequência de filmes para cada Usuário informa que a dimensão base é Filme e a dimensão do grupo é Usuário.

![](assets/vis_PathBrowser_Movies.png)

Ao clicar com o botão direito do mouse em qualquer elemento no navegador de caminho, você pode ver o nome da métrica associada ao navegador de caminho e seu valor para esse elemento.

![](assets/vis_PathBrowser_RightClick.png)

>[!NOTE]
>
>Você pode alterar as dimensões e métricas padrão de um navegador de caminho. Para obter instruções para configurar uma visualização do navegador de caminho, consulte [Configuração de navegadores de caminho](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).
