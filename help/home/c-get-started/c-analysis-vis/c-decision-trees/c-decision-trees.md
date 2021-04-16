---
description: Árvores de decisão são uma visualização de análise preditiva usada para avaliar as características e os relacionamentos do visitante. O Construtor de árvore de decisão gera uma visualização da árvore com base em um caso positivo e um conjunto de entradas especificados.
title: Construtor de árvore de decisão
uuid: 1f7e91ea-e5d9-4d8e-9fcf-cae4de42dfdd
exl-id: d93e6a34-be59-4af5-84c3-c13deb98b57b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 23%

---

# Construtor de árvore de decisão{#decision-tree-builder}

Árvores de decisão são uma visualização de análise preditiva usada para avaliar as características e os relacionamentos do visitante. O Construtor de árvore de decisão gera uma visualização da árvore com base em um caso positivo e um conjunto de entradas especificados.

Uma Árvore de decisão é um classificador binário com um conjunto de regras (ou filtros) responsável por identificar os visitantes que atendem a regras específicas com base em um caso positivo. Um conjunto de árvores de decisão para classificar visitantes que atendem (ou não) a esse caso positivo. As regras geram um mapa da árvore para fornecer um nível de confiança que atenda a esses resultados de casos positivos.

A árvore decisória é construída examinando os dados de cada nível e escolhendo aquele que proporciona o máximo ganho de informação num ponto de divisão especificado. Pontos divididos para cada nível de variável gera dois conjuntos:

* Valores inferiores ou iguais ao ponto dividido, e
* Valores maiores que o ponto dividido.

Usar árvores de decisão para

* Faça análise e interpretação significativas em menos tempo.
* Empregue a geração de segmentos automatizados.
* Faça inferências rapidamente a partir de um modelo com base em uma grande quantidade de dados.

![](assets/decision_tree_parts.png)

<table id="table_FCC5D63EF8A843D79B2338BD951025EA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Barra de ferramentas e menus</b> </p> <p>A barra de ferramentas inclui botões e comandos de menu para a Árvore de decisão, incluindo recursos para definir o Caso positivo e adicionar Listagens de entrada. </p> <p>Como outras visualizações, a caixa <span class="uicontrol"> Elemento</span> permite arrastar e soltar Dimension e Elementos, embora você também possa arrastar diretamente do painel Localizadores. </p> <p>Para obter mais informações, consulte <a href="../../../../home/c-get-started/c-analysis-vis/c-decision-trees/c-decision-trees-menu.md#concept-bfc4e80651a243d3966cc770b205606c"> Opções da árvore de decisão</a>. </p> </td> 
   <td colname="col2"> <p><b>Listagem de entrada</b> </p> <p>Essa área exibe as entradas no modelo de árvore. Eles são codificados por cores para corresponder nós na área Exibição em árvore. </p> <p>Clicar com o botão direito do mouse em uma entrada permite remover a entrada do modelo e redefinir. </p> <p>Se você passar o mouse sobre um nó de árvore, ele exibirá as condições de divisão ao longo da ramificação para esse nó e a previsão nesse nó com seu valor de confiança. </p> </td> 
   <td colname="col3"> <p><b>Exibição em árvore</b> </p> <p>Essa área exibe o modelo de árvore com nós de folha codificados por cores com base em sua previsão: verde para uma previsão True do Caso Positivo e vermelho para uma previsão False. </p> <p>Os nós divididos são codificados por cores para as entradas que correspondem à condição de seleção. Passar o mouse sobre um nó exibe informações sobre a divisão e expande a listagem de entradas para exibir os pontos divididos na ramificação e a distribuição do conjunto de treinamento. </p> <p>Os nós abaixo de um limite não são exibidos por padrão. Clique em um nó expansível (indicado por um símbolo +) para explorar uma ramificação. Clique no nó raiz para retornar à exibição em árvore completa. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_E800327344194A6DBF37F273D8462E2A"></a> -->
