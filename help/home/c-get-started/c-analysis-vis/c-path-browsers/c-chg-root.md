---
description: Você pode alterar a raiz de um navegador de caminho designando um elemento exibido como raiz ou adicionando um novo elemento à visualização.
solution: Analytics
title: Alterar a raiz do navegador de caminho
topic: Data workbench
uuid: 0bb9b004-9736-411b-bd22-cac04f4733a6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Alterar a raiz do navegador de caminho{#change-the-path-browser-s-root}

Você pode alterar a raiz de um navegador de caminho designando um elemento exibido como raiz ou adicionando um novo elemento à visualização.

>[!NOTE]
>
>Não é possível definir um nó inicial ou final como a raiz de um navegador de caminho.

**Para definir a raiz de um navegador de caminho**

* Clique com o botão direito do mouse no elemento desejado e clique em **[!UICONTROL Set as root]**.

**Para adicionar um novo elemento ao navegador de caminho**

1. Abra um gráfico ou tabela mostrando a dimensão cujos elementos você deseja exibir no navegador de caminho.

   Por exemplo, se você estiver trabalhando com dados do site, abra um gráfico de página ou tabela e identifique a página que deseja definir como raiz.

1. Pressione Ctrl+Alt e arraste o elemento desejado até a posição raiz no navegador de caminho.

   >[!NOTE]
   >
   >Você pode alterar a dimensão base associada a um navegador de caminho arrastando um elemento da dimensão desejada para o navegador de caminho. Esse elemento se torna a nova raiz do navegador de caminho, e o rótulo no canto superior esquerdo do navegador de caminho é alterado para refletir a dimensão desse elemento.

   Por exemplo, suponha que você crie um navegador de caminho de página mostrando a Sequência de Páginas para cada Sessão. Se você arrastar um elemento da dimensão Termo de pesquisa para o navegador de caminho, o elemento de termo de pesquisa se tornaria a nova raiz e o rótulo mostraria agora a Sequência de termos de pesquisa para cada sessão.

   >[!NOTE]
   >
   >Arrastar um elemento para um navegador de caminho pode alterar a dimensão base associada ao navegador de caminho, mas não altera a dimensão de nível, a dimensão de grupo ou a métrica. Portanto, é necessário ter cuidado ao escolher uma dimensão base que faça sentido quando usada com a dimensão de nível, dimensão de grupo e métrica do navegador de caminho. Para alterar a dimensão do nível, a dimensão do grupo ou a métrica, edite o arquivo do navegador do caminho [!DNL *.vw] em um editor de texto, como o Bloco de notas. Consulte [Configuração de navegadores](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3)de caminho.

