---
description: Você pode selecionar um caminho dentro de um navegador de caminho para criar filtros que incluem dados associados aos elementos no caminho.
solution: Analytics
title: Selecionar um caminho
topic: Data workbench
uuid: 3131df2f-674f-44b8-9006-d8cb1ecf3874
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Selecionar um caminho{#select-a-path}

Você pode selecionar um caminho dentro de um navegador de caminho para criar filtros que incluem dados associados aos elementos no caminho.

Quando você seleciona um caminho de elementos de dimensão base em um navegador de caminho, está selecionando dados para os elementos correspondentes da dimensão de nível.

Por exemplo, suponha que você tenha criado um navegador de caminho mostrando páginas de um site. Cada página é um elemento da dimensão Página e a dimensão de nível para Página é Exibição de página. Quando você seleciona um caminho de páginas em um navegador de caminho, está selecionando dados para as exibições de página associadas a essas páginas.

>[!NOTE]
>
>É possível alterar a dimensão de nível padrão de um navegador de caminho. Para obter instruções sobre como configurar um navegador de caminho, consulte [Configuração de navegadores](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3)de caminho.

1. Clique em um elemento no navegador de caminho para estender o caminho exibido para a esquerda ou direita da raiz.
1. Clique com o botão direito do mouse no elemento desejado e clique em **[!UICONTROL Select path]**. O caminho selecionado é contornado em branco.

   >[!NOTE]
   >
   >Não é possível selecionar um nó inicial ou final.

1. Repita a Etapa 1 para cada elemento que deseja adicionar ao caminho.

   Por exemplo, se você estiver trabalhando com dados de site, poderá selecionar um caminho de páginas em seu site.

   ![](assets/client-path.png)

   Este caminho constitui uma seleção e todas as outras visualizações abertas no espaço de trabalho (incluindo legendas) são atualizadas para exibir dados associados ao caminho criado pelos elementos selecionados. Consulte [Fazer seleções em visualizações](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

