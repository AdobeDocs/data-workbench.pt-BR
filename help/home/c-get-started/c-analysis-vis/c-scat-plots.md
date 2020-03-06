---
description: Os gráficos de gráficos de dispersão indicam os elementos de uma dimensão de dados (como Página ou Cidade) em uma grade na qual os eixos x e y representam métricas diferentes.
solution: Analytics
title: Gráficos de dispersão 2D
topic: Data workbench
uuid: 73c23d22-3c3a-4535-b66b-0e3508bd904c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Gráficos de dispersão 2D{#d-scatter-plots}

Os gráficos de gráficos de dispersão indicam os elementos de uma dimensão de dados (como Página ou Cidade) em uma grade na qual os eixos x e y representam métricas diferentes.

Os gráficos de dispersão podem ser úteis ao tentar entender a relação entre grandes números de itens diferentes, por duas métricas diferentes. No exemplo a seguir, o gráfico de dispersão mostra cada cidade pelo número de visitantes e a respectiva taxa de retenção.

![](assets/vis_ScatterPlot_City.png)

O gráfico de dispersão permite que você veja rapidamente os exceções. Salt Lake City, por exemplo, tem uma taxa de retenção superior à média por visitante.

Os gráficos de dispersão também podem ser usados para mostrar a consistência dos dados. No exemplo a seguir, o gráfico de dispersão mostra o número de visitantes com sessões de uma duração específica.

![](assets/vis_ScatterPlot_SessionDuration.png)

O tamanho de cada ponto no gráfico de dispersão é determinado pela métrica de raio. A métrica de raio padrão é diferente para cada aplicativo da Adobe. Por exemplo, em [!DNL Site], a métrica de raio se baseia em Sessões por padrão. Você pode alterar a métrica de raio para que os pontos em seus gráficos de dispersão representem qualquer métrica disponível. Para obter etapas para fazer isso, consulte [Alterar métricas](../../../home/c-get-started/c-analysis-vis/c-scat-plots.md#section-fd80576d583c430cb469daf12e39aa2a) de raio A cor dos pontos se baseia na legenda de cor que está aberta no espaço de trabalho. Para obter mais informações sobre legendas de cores, consulte Legendas [de](../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358)cores.

## Selecionar pontos {#section-4b4d45f39b884d54bb7407b3b2f4ea50}

**Para selecionar um único ponto**

* Clique no ponto.

**Para adicionar outro ponto ou grupo de pontos à sua seleção**

* Pressione Ctrl e clique em um ponto ou pressione Ctrl e arraste em vários pontos.

**Para remover um ponto ou grupo de pontos de sua seleção**

* Pressione Shift e clique em um ponto ou pressione Shift e arraste em vários pontos.

## Alteração de dimensões {#section-796cd962ef3f476caa89d99083782ed1}

* Clique com o botão direito do mouse no rótulo da dimensão na parte superior do gráfico e clique em **[!UICONTROL Change Dimension]** > *&lt;**[!UICONTROL dimension name]**>*.

## Alterar métricas {#section-44b8be9215cd4039b1eeb98ae1b31445}

**Alteração da métrica mostrada no eixo x ou y de um gráfico de dispersão**

* Clique com o botão direito do mouse no rótulo da métrica que deseja alterar e clique em **[!UICONTROL Change Metric]** > *&lt;**[!UICONTROL metric name]**>*.

## Alteração das métricas de raio {#section-fd80576d583c430cb469daf12e39aa2a}

**Alteração da métrica de raio de um gráfico de dispersão**

Clique com o botão direito do mouse no rótulo da dimensão na parte superior do gráfico e clique em **[!UICONTROL Change Radius Metric]** > *&lt;**[!UICONTROL metric name]**>*.

![](assets/mnu_ScatterPlot_Change.png)

