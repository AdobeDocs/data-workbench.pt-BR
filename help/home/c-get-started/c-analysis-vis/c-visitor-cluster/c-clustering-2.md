---
description: O Construtor de cluster agora inclui um algoritmo KMeans++ (somente o algoritmo KMeans era suportado anteriormente) que usa uma abordagem mais rápida para encontrar centros para um processo acelerado de geração de cluster.
title: Geração de cluster 2.0
uuid: 14462bd3-06d1-4622-a2d8-f96aadb357f3
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Geração de cluster 2.0{#clustering}

O Construtor de cluster agora inclui um algoritmo KMeans++ (somente o algoritmo KMeans era suportado anteriormente) que usa uma abordagem mais rápida para encontrar centros para um processo acelerado de geração de cluster.

## Algoritmos do KMeans {#section-92383a1be1d6402c95a25c902e90b850}

No Construtor [de clusters](https://docs.adobe.com/help/en/data-workbench/using/client/analysis-visualizations/visitor-cluster/c-visitor-cluster.html), agora é possível selecionar **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** para selecionar algoritmos ao definir clusters.

* **[!UICONTROL KMeans]**. Esse algoritmo usa o clustering de cópia para definir os centros do cluster.
* **[!UICONTROL KMeans++]**. Esse algoritmo acelera a criação de clusters ao executar em grandes conjuntos de dados.

<!-- <a id="section_8193A6D60C5540BB985085BE670B4544"></a> -->

O KMeans++ é uma implementação aprimorada do algoritmo de agrupamento do KMeans, pois fornece uma melhor inicialização dos centros k iniciais. (O algoritmo KMeans original escolhe os centros iniciais aleatoriamente.) O KMeans++ seleciona o primeiro centro aleatoriamente. Os centros k-1 restantes serão escolhidos um por um com base na distância que um ponto de dados percorrer para o centro existente mais próximo. Os pontos de dados mais distantes têm mais chances de ser escolhidos como um novo centro do que os pontos de dados próximos. Depois que o centro inicial é escolhido, o procedimento é executado exatamente como o clustering KMeans original.

O fluxo de trabalho do KMeans++ é exatamente o mesmo que o fluxo de trabalho para clustering do KMeans, exceto que é necessário selecionar **Opções** > **Algoritmo** > **KMeans++** no construtor de cluster.

>[!NOTE]
>
>Cada DPU executa seu próprio procedimento KMeans++ em sua própria porção de dados. Se a DPU tiver memória disponível suficiente (a proporção é configurável no arquivo PAServer.cfg), os dados dessas variáveis envolvidas serão trazidos para a memória. A seleção inicial de k-1 e as iterações convergentes restantes acontecem na memória, o que é mais rápido do que o agrupamento anterior do KMeans.

