---
description: As árvores de decisão são uma visualização de análise preditiva usada para avaliar as características e os relacionamentos do visitante. O Construtor de árvore de decisão gera uma visualização da árvore com base em um caso positivo e um conjunto de entradas especificados.
solution: Analytics
title: Árvore de decisão Construtor
topic: Data workbench
uuid: 1f7e91ea-e5d9-4d8e-9fcf-cae4de42dfdd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Construtor de árvore decisória{#decision-tree-builder}

As árvores de decisão são uma visualização de análise preditiva usada para avaliar as características e os relacionamentos do visitante. O Construtor de árvore de decisão gera uma visualização da árvore com base em um caso positivo e um conjunto de entradas especificados.

Uma Árvore de decisão é um classificador binário com um conjunto de regras (ou filtros) responsável por identificar os visitantes que atendem a regras específicas com base em um caso positivo. Um conjunto de árvores de decisão para classificar visitantes que atendem (ou não) a esse caso positivo. As regras geram um mapa da árvore para fornecer um nível de confiança que atenda a esses resultados de casos positivos.

Uma árvore decisória é construída examinando entradas em cada nível e escolhendo aquela que oferece o máximo ganho de informação em um ponto de divisão especificado. Os pontos divididos para cada nível de variável geram dois conjuntos:

* Valores inferiores ou iguais ao ponto de divisão, e
* Valores maiores que o ponto dividido.

Usar árvores de decisão para

* Execute análises e interpretações significativas em menos tempo.
* Empregue a geração automatizada de segmentos.
* Faça inferências rapidamente a partir de um modelo com base em uma grande quantidade de dados.

![](assets/decision_tree_parts.png)

<table id="table_FCC5D63EF8A843D79B2338BD951025EA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Barra de ferramentas e menus</b> </p> <p>A barra de ferramentas inclui botões e comandos de menu para a Árvore decisória, incluindo recursos para definir o Caso positivo e adicionar Listagens de entrada. </p> <p>Como outras visualizações, a caixa <span class="uicontrol"> Elemento</span> permite arrastar e soltar Dimensão e Elementos, embora você também possa arrastar diretamente do painel Localizadores. </p> <p>Para obter mais informações, consulte Opções <a href="../../../../home/c-get-started/c-analysis-vis/c-decision-trees/c-decision-trees-menu.md#concept-bfc4e80651a243d3966cc770b205606c"></a>da árvore decisória. </p> </td> 
   <td colname="col2"> <p><b>Lista de entrada</b> </p> <p>Essa área exibe as entradas no modelo de árvore. Eles são codificados por cores para corresponder aos nós na área de Exibição em árvore. </p> <p>Clicar com o botão direito do mouse em uma entrada permite remover a entrada do modelo e redefinir. </p> <p>Se você passar o mouse sobre um nó de árvore, ele exibirá as condições de divisão ao longo do ramo para esse nó e a previsão nesse nó com seu valor de confiança. </p> </td> 
   <td colname="col3"> <p><b>Exibição em árvore</b> </p> <p>Essa área exibe o modelo de árvore com nós de folha codificados por cor com base em sua previsão: verde para uma previsão Verdadeiro do Caso Positivo, e vermelho para uma previsão Falsa. </p> <p>Os nós divididos são codificados por cores para as entradas que correspondem à condição de seleção. Passar o mouse sobre um nó exibe informações sobre a divisão e expande a listagem de entradas para exibir os pontos divididos ao longo da ramificação e a distribuição do conjunto de treinamento. </p> <p>Os nós abaixo de um limite não são exibidos por padrão. Clique em um nó expansível (indicado por um símbolo +) para explorar uma ramificação. Clique no nó raiz para retornar à exibição completa da árvore. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_E800327344194A6DBF37F273D8462E2A"></a> -->

