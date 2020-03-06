---
description: Você pode criar um navegador de caminho a partir de um gráfico, tabela ou mapa de processos.
solution: Analytics
title: Criação de navegadores de caminho
topic: Data workbench
uuid: 84a5e587-fb02-461b-aec8-1b6ad473ebc3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Criação de navegadores de caminho{#creating-path-browsers}

Você pode criar um navegador de caminho a partir de um gráfico, tabela ou mapa de processos.

**Para criar um navegador de caminho a partir de um gráfico ou tabela**

1. Adicione um navegador de caminho à sua área de trabalho. A visualização está em branco, exceto pelo rótulo (Sequência de...) no canto superior esquerdo.
1. Abra um gráfico ou tabela mostrando a dimensão cujos elementos você deseja exibir no navegador de caminho. Por exemplo, se você estiver trabalhando com dados do site, abra um gráfico de página ou tabela e identifique a página que deseja definir como raiz.
1. Pressione Ctrl+Alt e arraste o elemento desejado para o navegador de caminho. O rótulo no canto superior esquerdo do navegador de caminho muda para refletir a dimensão base cujo elemento você arrasta para o navegador de caminho.

>[!NOTE]
>
>Arrastar um elemento para um navegador de caminho pode alterar a dimensão base associada ao navegador de caminho, mas não altera a dimensão de nível, a dimensão de grupo ou a métrica. Portanto, é necessário ter cuidado ao escolher uma dimensão base que faça sentido quando usada com a dimensão de nível, dimensão de grupo e métrica do navegador de caminho. Para alterar a dimensão do nível, a dimensão do grupo ou a métrica, edite o arquivo do navegador do caminho [!DNL *.vw] em um editor de texto, como o Bloco de notas. Consulte [Configuração de navegadores](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3)de caminho.

**Para criar um navegador de caminho a partir de um mapa de processos**

>[!NOTE]
>
>Um navegador de caminho criado a partir de um mapa de processos exibe apenas os elementos mostrados no mapa de processos. Outros elementos da dimensão base não são exibidos.

1. Crie um mapa de processos. Consulte [Criação de mapas](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-create-proc-maps.md#concept-daf5b14dae7a442191611b1b9c1122bf)de processo.
1. Arraste o elemento desejado do mapa do processo para o navegador de caminho. O elemento se torna a raiz do navegador de caminho.

>[!NOTE]
>
>Quando você cria um navegador de caminho a partir de um mapa de processo, o navegador de caminho ignora os elementos da dimensão de nível sem elementos de dimensão base associados. Quando você arrasta um nó de um mapa de processo para um navegador de caminho, a dimensão básica do navegador de caminho (denominado Mapa) é definida pelo mapa de processo e seus elementos são limitados aos elementos no mapa de processo. Como resultado, alguns elementos da dimensão de nível do navegador de caminho não têm elementos de dimensão base associados e não são representados no navegador de caminho.

