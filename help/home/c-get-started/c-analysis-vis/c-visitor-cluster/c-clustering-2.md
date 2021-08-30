---
description: O Construtor de Cluster agora inclui um algoritmo KMeans++ (somente o algoritmo KMeans era compatível anteriormente) que usa uma abordagem mais rápida para encontrar centros para um processo acelerado de geração de cluster.
title: Geração de cluster 2.0
uuid: 14462bd3-06d1-4622-a2d8-f96aadb357f3
exl-id: 6a779ddc-c8f1-4c55-9c17-1119fe1aa791
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Geração de cluster 2.0{#clustering}

O Construtor de Cluster agora inclui um algoritmo KMeans++ (somente o algoritmo KMeans era compatível anteriormente) que usa uma abordagem mais rápida para encontrar centros para um processo acelerado de geração de cluster.

## Algoritmos do KMeans {#section-92383a1be1d6402c95a25c902e90b850}

No [Construtor de Cluster](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/visitor-cluster/c-visitor-cluster.html?lang=en), agora você pode selecionar **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** para selecionar algoritmos ao definir clusters.

* **[!UICONTROL KMeans]**. Esse algoritmo usa o clustering de cópia para definir os centros do cluster.
* **[!UICONTROL KMeans++]**. Esse algoritmo acelera a criação de cluster ao executar em grandes conjuntos de dados.

<!-- <a id="section_8193A6D60C5540BB985085BE670B4544"></a> -->

O KMeans+ é uma implementação aprimorada do algoritmo de cluster KMeans, pois fornece uma melhor inicialização dos centros k iniciais. (O algoritmo KMeans original escolhe centros iniciais aleatoriamente.) KMeans++ seleciona o primeiro centro aleatoriamente. Os centros k-1 restantes serão escolhidos um por um com base na distância que um ponto de dados representa para o centro existente mais próximo. Os pontos de dados mais distantes têm mais chances de ser escolhidos como um novo centro do que os pontos de dados mais próximos. Depois que o centro inicial é escolhido, o procedimento é executado exatamente como o clustering original do KMeans.

O fluxo de trabalho para KMeans+ é exatamente o mesmo que o fluxo de trabalho para clustering KMeans, exceto que é necessário selecionar **Options** > **Algorithm** > **KMeans++** no construtor de cluster.

>[!NOTE]
>
>Cada DPU executa seu próprio procedimento KMeans++ em sua própria porção de dados. Se a DPU tiver memória disponível suficiente (a proporção é configurável no arquivo PAServer.cfg), os dados dessas variáveis envolvidas serão trazidos para a memória. A seleção central inicial k-1 e as iterações convergentes restantes acontecem na memória, o que é mais rápido que o cluster KMeans anterior.
