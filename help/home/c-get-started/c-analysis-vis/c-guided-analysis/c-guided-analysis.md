---
description: Uma visualização de análise guiada fornece dicas para análise adicional com base nas seleções feitas em um espaço de trabalho.
solution: Analytics
title: Análise guiada
topic: Data workbench
uuid: 01ed8207-3a14-45ac-8a1d-4e17ac39bb94
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Análise guiada{#guided-analysis}

Uma visualização de análise guiada fornece dicas para análise adicional com base nas seleções feitas em um espaço de trabalho.

Esta visualização ajuda a identificar quais dimensões podem fornecer mais informações, ou seja, aquelas que estão mais fortemente correlacionadas com suas seleções. A visualização da análise guiada em seu aplicativo Adobe exibe as dimensões relevantes para seu conjunto de dados, como na seguinte visualização da análise [!DNL Site] guiada.

![](assets/vis_GuidedAnalysis.png)

>[!NOTE]
>
>Se um nome de dimensão for exibido em vermelho, ele não será definido no conjunto de dados.

Quando você faz uma seleção dentro de um espaço de trabalho, a visualização da análise guiada exibe marcas de seleção à esquerda e pontos à direita das dimensões para mostrar quais fornecem as informações mais relevantes:

* **As marcas** de seleção identificam as dimensões cujos valores diferem do benchmark de uma forma estatisticamente significativa (ou seja, a diferença entre a seleção e o benchmark não é devida a acaso aleatório).
* **Os pontos** indicam o grau em que a seleção difere do benchmark. O primeiro ponto representa a estatística U, e o segundo ponto representa a estatística V. Ver [Compreensão das Medidas](../../../../home/c-get-started/c-analysis-vis/c-guided-analysis/c-stat-measures.md#concept-ba2c7f417f384dc0a3438fcb6e268708)Estatísticas. Quanto mais claros e maiores forem os pontos, maior será a diferença e mais relevantes serão as informações para a dimensão com base na sua seleção (ou seja, pontos maiores, mais brilhantes representam informações mais úteis).

