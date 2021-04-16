---
description: Uma visualização de análise guiada fornece dicas para análise adicional com base nas seleções feitas em um espaço de trabalho.
title: Análise guiada
uuid: 01ed8207-3a14-45ac-8a1d-4e17ac39bb94
exl-id: c19b52b6-52db-455e-adde-8b2400aae006
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---

# Análise guiada{#guided-analysis}

Uma visualização de análise guiada fornece dicas para análise adicional com base nas seleções feitas em um espaço de trabalho.

Essa visualização ajuda a identificar quais dimensões podem fornecer mais informações, ou seja, aquelas que estão mais fortemente correlacionadas com suas seleções. A visualização da análise guiada no aplicativo Adobe exibe as dimensões relevantes para o conjunto de dados, como na seguinte [!DNL Site] visualização guiada da análise.

![](assets/vis_GuidedAnalysis.png)

>[!NOTE]
>
>Se um nome de dimensão for exibido em vermelho, ele não será definido no conjunto de dados.

Quando você faz uma seleção em um espaço de trabalho, a visualização da análise guiada exibe marcas de seleção à esquerda e pontos à direita das dimensões para mostrar quais fornecem as informações mais relevantes:

* **Marcos de seleção** identificam as dimensões cujos valores diferem do referencial de uma maneira estatisticamente significativa (ou seja, a diferença entre a seleção e o referencial não é devida a acaso).
* **** Os pontos indicam o grau em que a seleção difere do referencial. O primeiro ponto representa a estatística U e o segundo representa a estatística V. Consulte [Entendendo as Medidas Estatísticas](../../../../home/c-get-started/c-analysis-vis/c-guided-analysis/c-stat-measures.md#concept-ba2c7f417f384dc0a3438fcb6e268708). Quanto mais claro e maior for o valor dos pontos, maior será a diferença e mais relevantes serão as informações da dimensão com base na sua seleção (ou seja, pontos maiores, mais claros, representarão informações mais úteis).
