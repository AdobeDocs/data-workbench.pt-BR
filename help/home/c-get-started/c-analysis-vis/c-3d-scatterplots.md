---
description: Um Gráfico de dispersão 3D faz o gráfico dos elementos de uma dimensão de dados (como Dias ou Site de referência) em uma grade tridimensional na qual os eixos x, y e z representam várias métricas.
solution: Analytics
title: Gráficos de dispersão 3D
topic: Data workbench
uuid: 5e23547c-dbb4-490c-94bc-0731deee612e
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Gráficos de dispersão 3D{#d-scatter-plots}

Um Gráfico de dispersão 3D faz o gráfico dos elementos de uma dimensão de dados (como Dias ou Site de referência) em uma grade tridimensional na qual os eixos x, y e z representam várias métricas.

Como o [Gráfico de dispersão 2D](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Scatter_Plots), essa visualização é útil ao tentar entender a relação entre grandes números de itens diferentes usando métricas diferentes.

**Para usar a visualização do Gráfico de dispersão 3D:**

1. Abra um novo espaço de trabalho.

   Depois de abrir um novo espaço de trabalho, talvez seja necessário clicar em **Adicionar** > Desbloquear **** temporariamente.
1. Clique com o botão direito do mouse e selecione **Visualização** > Gráfico de dispersão **3D**.

   Uma lista de menus **[!UICONTROL Dimensions]** será aberta.

1. Selecione uma dimensão para a consulta.

   O Gráfico de dispersão 3D abrirá as métricas padrão para essa dimensão.

   ![](assets/3D_main.png)

   A seleção do **[!UICONTROL Days]** menu exibe o seguinte Gráfico de dispersão 3D com essas métricas padrão nos seguintes eixos: **[!UICONTROL x=Visits]**, **[!UICONTROL y=Retention]** e **[!UICONTROL z=Visits]**.

1. Alterar métricas. Clique com o botão direito do mouse no rótulo da métrica no eixo x, y ou z e selecione **[!UICONTROL Change Metric]**. Em seguida, selecione uma métrica diferente para o eixo selecionado.

   ![](assets/3D_change.png)

   >[!IMPORTANT]
   >
   >
   >    
   >    
   >    * Arraste uma métrica para um dos três rótulos de eixo e solte-a para alterar o eixo selecionado para a métrica solta.
   >    * Arraste uma métrica para qualquer outro lugar na visualização e solte-a para alterar a métrica de raio desse eixo.
   >    * Arraste uma dimensão para qualquer lugar na visualização e solte-a para alterar a dimensão da visualização.


1. Altere a métrica Raio. Clique com o botão direito do mouse no título na parte superior da página (intitulado após a dimensão selecionada) e selecione **[!UICONTROL Change Radius Metric]**.

   A métrica de raio define o tamanho do ponto traçado com base na seleção da métrica. A posição relativa dos pontos não muda no gráfico de dispersão, mas os tamanhos de pontos plotados dentro da visualização aumentam com base no valor da métrica.

   ![](assets/3D_change_radius.png)

1. Empregue o **[!UICONTROL Orthographic Camera]**. Essa opção permite identificar os pontos traçados em relação à perspectiva real com base na métrica de raio para evitar a distorção tridimensional.

   Quando o Gráfico de dispersão 3D é exibido pela primeira vez, ele é exibido em uma projeção rotativa tridimensional, o que causa alguma distorção para pontos mais próximos da perspectiva, ou &quot;câmera&quot; virtual. (Os gráficos mais próximos à câmera aparecem muito maiores do que os pontos girando mais longe da câmera.)

   Para evitar essa distorção de perspectiva, você pode selecionar a **[!UICONTROL Orthographic Camera]** opção clicando com o botão direito do mouse no título e selecionando no menu. Isso permite que você represente os objetos tridimensionais em duas dimensões. Isso renderiza os pontos traçados como planos e exibe os pontos como relativos à métrica de raio, diminuindo os deslocamentos tridimensionais.

1. Selecione pontos do gráfico de dispersão.

   * **Para remover um ponto ou grupo de pontos**: Clique no ponto.
   * **Para adicionar outro ponto ou grupo de pontos à sua seleção**: **Ctrl** + **clique** em um ponto ou **Ctrl** + **arraste** através de vários pontos.

   * **Para remover um ponto ou grupo de pontos de sua seleção**: **Shift** + **clique** em um ponto ou **Shift** **+** arraste **** vários pontos.

<!-- <a id="section_9C30F9799F1440F09278327002E6B47A"></a> -->

