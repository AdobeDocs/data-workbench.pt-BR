---
description: Os gráficos de dispersão gráfico os elementos de uma dimensão de dados (como Página ou Cidade) em uma grade na qual os eixos x e y representam métricas diferentes.
title: Gráficos de dispersão 2D
uuid: 73c23d22-3c3a-4535-b66b-0e3508bd904c
exl-id: 340f8c18-ce47-4f3a-aba4-3d6124505313
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 1%

---

# Gráficos de dispersão 2D{#d-scatter-plots}

Os gráficos de dispersão gráfico os elementos de uma dimensão de dados (como Página ou Cidade) em uma grade na qual os eixos x e y representam métricas diferentes.

Gráficos de dispersão podem ser úteis ao tentar entender a relação entre um grande número de itens diferentes, por duas métricas diferentes. No exemplo a seguir, o gráfico de dispersão mostra cada cidade pelo número de visitantes e a respectiva taxa de retenção.

![](assets/vis_ScatterPlot_City.png)

O gráfico de dispersão permite que você veja rapidamente os outliers. Salt Lake City, por exemplo, tem uma taxa de retenção superior à média por visitante.

Os gráficos de dispersão também podem ser usados para mostrar a consistência dos dados. No exemplo a seguir, o gráfico de dispersão mostra o número de visitantes com sessões de um determinado comprimento.

![](assets/vis_ScatterPlot_SessionDuration.png)

O tamanho de cada ponto no gráfico de dispersão é determinado pela métrica de raio. A métrica de raio padrão é diferente para cada aplicativo de Adobe. Por exemplo, em [!DNL Site], a métrica de raio é baseada em Sessões por padrão. Você pode alterar a métrica de raio para que os pontos nos gráficos de dispersão representem qualquer métrica disponível. Para obter etapas para fazer isso, consulte [Alteração das métricas do Raio](../../../home/c-get-started/c-analysis-vis/c-scat-plots.md#section-fd80576d583c430cb469daf12e39aa2a) A cor dos pontos é baseada na legenda de cores aberta no espaço de trabalho. Para obter mais informações sobre legendas de cores, consulte [Legendas de cores](../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).

## Selecionar pontos {#section-4b4d45f39b884d54bb7407b3b2f4ea50}

**Para selecionar um único ponto**

* Clique no ponto.

**Para adicionar outro ponto ou grupo de pontos à sua seleção**

* Ctrl+clique em um ponto ou Ctrl+arraste em vários pontos.

**Para remover um ponto ou grupo de pontos de sua seleção**

* Clique com a tecla Shift pressionada em um ponto ou arraste com a tecla Shift pressionada em vários pontos.

## Alteração de dimensões {#section-796cd962ef3f476caa89d99083782ed1}

* Clique com o botão direito do mouse no rótulo da dimensão na parte superior do gráfico e clique em **[!UICONTROL Change Dimension]** > *&lt;**[!UICONTROL dimension name]**>*.

## Alterar métricas {#section-44b8be9215cd4039b1eeb98ae1b31445}

**Alteração da métrica mostrada no eixo x ou y de um gráfico de dispersão**

* Clique com o botão direito do mouse no rótulo da métrica que deseja alterar e clique em **[!UICONTROL Change Metric]** > *&lt;**[!UICONTROL metric name]**>*.

## Alterar métricas de raio {#section-fd80576d583c430cb469daf12e39aa2a}

**Alteração da métrica de raio de um gráfico de dispersão**

Clique com o botão direito do mouse no rótulo da dimensão na parte superior do gráfico e clique em **[!UICONTROL Change Radius Metric]** > *&lt;**[!UICONTROL metric name]**>*.

![](assets/mnu_ScatterPlot_Change.png)
