---
description: O clustering do visitante permite aproveitar as características do cliente para categorizar dinamicamente os visitantes e gerar conjuntos de clusters com base em entradas de dados selecionadas, identificando grupos que têm interesses e comportamentos semelhantes para análise e direcionamento do cliente.
title: Cluster do visitante
uuid: 0c16aaa0-1d86-43a6-a7e2-b43b3ea80dc5
exl-id: 68c1845d-9c49-4ad9-adf3-c123d08cf758
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 2%

---

# Cluster do visitante{#visitor-clustering}

O clustering do visitante permite aproveitar as características do cliente para categorizar dinamicamente os visitantes e gerar conjuntos de clusters com base em entradas de dados selecionadas, identificando grupos que têm interesses e comportamentos semelhantes para análise e direcionamento do cliente.

**Processo de cluster**

O processo de clustering requer que você identifique métricas e elementos de dimensão a serem usados como entradas e permite que você escolha uma população de target específica para aplicar esses elementos para criar clusters especificados. Quando você executa o processo de cluster, o sistema usa a métrica e as entradas de dimensão para determinar os centros iniciais apropriados para o número especificado de clusters. Esses centros são então usados como ponto de partida para aplicar o algoritmo K-Means.

![](assets/K_algorithm.png)

* Os centros iniciais são escolhidos de forma inteligente por meio de um passe de Clustering da Canopy.
* Os clusters de dados são criados associando cada ponto de dados ao centro mais próximo.
* A média de cada um dos clusters K torna-se o novo centro.
* O algoritmo é repetido nas etapas 2 e 3 até que a convergência seja alcançada. Isso pode levar várias passagens.

O **[!UICONTROL Maximum Iterations]** no menu **[!UICONTROL Options]** permite que o analista especifique o número máximo de iterações a serem executadas pelo algoritmo de cluster. Definir essa opção pode resultar em uma conclusão mais rápida do processo de cluster com base no limite máximo de iterações em detrimento da convergência exata dos centros de cluster.

>[!NOTE]
>
>Depois que os clusters forem definidos, o Dimension Cluster poderá ser salvo para uso como qualquer outra dimensão. Ele também pode ser carregado no Cluster Explorer para examinar a separação de centros de cluster.

No Construtor de Cluster, você pode selecionar **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** para selecionar algoritmos ao definir clusters. Atualmente, há 3 algoritmos compatíveis:

* KMeans
* KSignifica`++`
* Maximização de expectativa

Há duas maneiras de executar o processo de cluster:

* Método 1 - Clique em **[!UICONTROL Go]** na janela de visualização do cluster.
* Método 2 - Clique em **[!UICONTROL Submit]** na janela de visualização do cluster, que envia diretamente o trabalho de cluster para o Servidor. Você pode acompanhar o progresso através da opção &quot;Status Detalhado para Consulta&quot;.

![](assets/dwb_visitorclustering.png)

O algoritmo tem as seguintes restrições:

1. Se você estiver usando o Método 1, poderá selecionar qualquer um dos algoritmos de cluster suportados.
1. Se estiver usando o Método 2, você pode selecionar kMeds ou kMeia++. A opção Maximização de expectativa não estará disponível.

>[!NOTE]
>
>No arquivo [!DNL DPU.cfg], o valor de &#39;Query, Memory Limit&#39; é definido como 500 MB por padrão. Esse valor deve ser aumentado ao executar vários trabalhos de cluster. Por exemplo, se você estiver executando 5 trabalhos de cluster em paralelo, aumente esse valor para 1 GB. Não há como cancelar o trabalho de cluster sem reiniciar o Servidor.

**Recomendações**

O número de iterações (número de vezes que os dados são digitalizados) e o limite de convergência que você configura afetam grosseiramente o desempenho do cluster. A tabela a seguir fornece uma diretriz mais ampla que você pode seguir:

| Número de clusters | Algoritmo | Iterações | Limite de Convergência | Normalização |
|---|---|---|---|---|
| 6 | KMeia | 25,50 | 1e-3 | Mín-Máx |
| 6 | KMeia | 25,50 | 1e-6 | Mín-Máx |
| 6 | KMeia++ | 50 | 1e-6 | Mín-Máx |
