---
description: Um Gráfico de dispersão 3D gráfico os elementos de uma dimensão de dados (como Dias ou Site de referência) em uma grade tridimensional em que os eixos x, y e z representam várias métricas.
title: Gráficos de dispersão 3D
uuid: 5e23547c-dbb4-490c-94bc-0731deee612e
exl-id: 18f18cab-a31b-4ffe-89c5-412a5645af2e
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 1%

---

# Gráficos de dispersão 3D{#d-scatter-plots}

Um Gráfico de dispersão 3D gráfico os elementos de uma dimensão de dados (como Dias ou Site de referência) em uma grade tridimensional em que os eixos x, y e z representam várias métricas.

Como o [Gráfico de dispersão 2D](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html#Scatter_Plots), essa visualização é útil ao tentar entender a relação entre um grande número de itens diferentes usando métricas diferentes.

**Para usar a visualização do Gráfico de dispersão 3D:**

1. Abra um novo espaço de trabalho.

   Após abrir um novo espaço de trabalho, talvez seja necessário clicar em **Add** > **Temporariamente Unlock**.
1. Clique com o botão direito do mouse e selecione **Visualization** > **3D Scatter Plot**.

   Um menu que lista **[!UICONTROL Dimensions]** abrirá.

1. Selecione uma dimensão para a query.

   O Gráfico de dispersão 3D abrirá as métricas padrão para essa dimensão.

   ![](assets/3D_main.png)

   Selecionar o menu **[!UICONTROL Days]** exibe o seguinte Gráfico de dispersão 3D com essas métricas padrão nos seguintes eixos: **[!UICONTROL x=Visits]**, **[!UICONTROL y=Retention]** e **[!UICONTROL z=Visits]**.

1. Alterar métricas. Clique com o botão direito do mouse no rótulo da métrica no eixo x, y ou z e selecione **[!UICONTROL Change Metric]**. Em seguida, selecione uma métrica diferente para o eixo selecionado.

   ![](assets/3D_change.png)

   >[!IMPORTANT]
   >
   >
   >    
   >    
   >    * Arraste uma métrica para um dos rótulos de três eixos e solte-a para alterar o eixo selecionado para a métrica solta.
   >    * Arraste uma métrica para qualquer outro lugar na visualização e solte-a para alterar a métrica de raio para esse eixo.
   >    * Arraste uma dimensão para qualquer lugar na visualização e solte-a para alterar a dimensão da visualização.


1. Altere a métrica Raio. Clique com o botão direito do mouse no título na parte superior da página (intitulada após a dimensão selecionada) e selecione **[!UICONTROL Change Radius Metric]**.

   A métrica de raio define o tamanho do ponto plotado com base na seleção da métrica. A posição relativa dos pontos não muda no gráfico de dispersão, mas os tamanhos dos pontos representados na visualização aumentam com base no valor da métrica.

   ![](assets/3D_change_radius.png)

1. Aplique o **[!UICONTROL Orthographic Camera]**. Essa opção permite identificar os pontos representados em relação à perspectiva real com base na métrica do raio para evitar distorções tridimensionais.

   Quando o Gráfico de Dispersão 3D é exibido primeiro, ele é exibido em uma projeção rotativa tridimensional, o que causa alguma distorção para pontos mais próximos da perspectiva, ou &quot;câmera&quot; virtual. (Os gráficos mais próximos à câmera mostram-se muito maiores do que os pontos que giram mais longe da câmera.)

   Para evitar essa distorção de perspectiva, selecione a opção **[!UICONTROL Orthographic Camera]** clicando com o botão direito do mouse no título e selecionando no menu . Isso permite representar os objetos tridimensionais em duas dimensões. Isso renderiza os pontos plotados como planos e exibe os pontos como relativos à métrica de raio, diminuindo os deslocamentos tridimensionais.

1. Selecione pontos no gráfico de dispersão.

   * **Para remover um ponto ou grupo de pontos**: Clique no ponto.
   * **Para adicionar outro ponto ou grupo de pontos à sua seleção**:  **Ctrl** +  **** clique no ponto ou  **Ctrl** +  **** arraste vários pontos.

   * **Para remover um ponto ou grupo de pontos de sua seleção**:  **Shift** + ponto de  **** cliques ou  **Shift** **+** **** arrastar em vários pontos.

<!-- <a id="section_9C30F9799F1440F09278327002E6B47A"></a> -->
