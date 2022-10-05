---
description: Você pode criar um navegador de caminho a partir de um gráfico, tabela ou mapa de processos.
title: Criar navegadores de caminho
uuid: 84a5e587-fb02-461b-aec8-1b6ad473ebc3
exl-id: 9fa11b84-da73-447a-8b10-7eab381e3f66
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# Criar navegadores de caminho{#creating-path-browsers}

{{eol}}

Você pode criar um navegador de caminho a partir de um gráfico, tabela ou mapa de processos.

**Para criar um navegador de caminho a partir de um gráfico ou tabela**

1. Adicione um navegador de caminho ao seu espaço de trabalho. A visualização fica em branco, exceto pelo rótulo (Sequência de...) no canto superior esquerdo.
1. Abra um gráfico ou tabela mostrando a dimensão cujos elementos você deseja exibir no navegador de caminho. Por exemplo, se você estiver trabalhando com dados do site, abra um gráfico de página ou tabela e identifique a página que deseja definir como a raiz.
1. Pressione Ctrl+Alt e arraste o elemento desejado para o navegador de caminho. O rótulo no canto superior esquerdo do navegador de caminho muda para refletir a dimensão base cujo elemento você arrasta para o navegador de caminho.

>[!NOTE]
>
>Arrastar um elemento para um navegador de caminho pode alterar a dimensão base associada ao navegador de caminho, mas não altera a dimensão de nível, a dimensão de grupo ou a métrica. Portanto, você deve ter cuidado ao escolher uma dimensão base que faça sentido quando usada com a dimensão de nível do navegador de caminho, dimensão de grupo e métrica. Para alterar a dimensão do nível, a dimensão do grupo ou a métrica, você deve editar o navegador de caminho [!DNL *.vw] em um editor de texto, como o Bloco de notas. Consulte [Configuração de navegadores de caminho](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).

**Para criar um navegador de caminho a partir de um mapa de processos**

>[!NOTE]
>
>Um navegador de caminho criado a partir de um mapa de processos exibe apenas os elementos mostrados no mapa de processos. Outros elementos da dimensão base não são exibidos.

1. Criar um mapa de processos. Consulte [Criação de mapas de processos](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-create-proc-maps.md#concept-daf5b14dae7a442191611b1b9c1122bf).
1. Arraste o elemento desejado do mapa de processos para o navegador de caminhos. O elemento se torna a raiz do navegador de caminho.

>[!NOTE]
>
>Ao criar um navegador de caminho a partir de um mapa de processos, o navegador de caminhos ignora os elementos da dimensão de nível sem elementos de dimensão base associados. Quando você arrasta um nó de um mapa de processos para um navegador de caminhos, a dimensão base do navegador de caminhos (chamada Mapa) é definida pelo mapa de processos e seus elementos são limitados aos elementos no mapa de processos. Como resultado, alguns elementos da dimensão de nível do navegador de caminho não têm elementos de dimensão base associados e não são representados no navegador de caminho.
