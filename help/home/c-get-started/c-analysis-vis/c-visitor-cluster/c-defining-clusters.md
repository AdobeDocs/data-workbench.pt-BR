---
description: Selecione variáveis de entrada, o número de clusters e um público-alvo (se desejado) para definir clusters em seu conjunto de dados.
title: Criar clusters
uuid: f8462445-b7d2-48ae-aed7-2a3abc491cfb
exl-id: 60bc75bf-2f89-455b-8be9-aa20bb837752
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 1%

---

# Criar clusters{#building-clusters}

Selecione variáveis de entrada, o número de clusters e um público-alvo (se desejado) para definir clusters em seu conjunto de dados.

**Criar clusters**

1. Abra o **[!UICONTROL Cluster Builder]**.

   Clique em **Visualização** > **Análise preditiva** > **Clustering** > **Cluster Builder**.

   ![](assets/cluster-builder-step1.png)

1. Selecione as variáveis de entrada.

   * Adicione métricas à lista **[!UICONTROL Input Variables]** selecionando no menu **[!UICONTROL Metric]** na barra de ferramentas.

      ![](assets/cluster_metric_select.png)

   * Adicione elementos de dimensão à lista **[!UICONTROL Input Variables]** arrastando-os de uma tabela do Dimension.

      Pressione **[!UICONTROL Ctrl + Alt]** e arraste os elementos de dimensão selecionados para a lista **[!UICONTROL Input Variables]** ou para a caixa **[!UICONTROL Element]** na barra de ferramentas.

      ![](assets/cluster_dim_select.png)
   Por padrão, o clustering é executado em todo o conjunto de dados. Você pode ver todas as variáveis de entrada no painel esquerdo **[!UICONTROL Preprocessing]**.
1. Use o menu **[!UICONTROL Options]** para selecionar o número desejado de clusters.

   ![](assets/build_cluster_2.png)

1. Se você deseja agrupar um subconjunto de Visitantes em seu conjunto de dados, é possível definir um Filtro de população.

   ![](assets/build_cluster_3.png)

   Comece definindo o subconjunto desejado usando seleções no Workspace ou usando o **[!UICONTROL Filter Editor]**. Depois de selecionar o subconjunto desejado, defina o Público alvo no menu **[!UICONTROL Options]** . É recomendável que você dê um nome de identificação ao grupo alvo.

   O menu **[!UICONTROL Options]** também tem configurações para controlar o número máximo de passagens e o limite aceitável para convergência central.

1. Depois que as entradas e opções tiverem sido configuradas, clique no botão **Ir** para executar o clustering localmente ou pressione **[!UICONTROL Submit]** para enviar a tarefa para o Servidor Preditivo do Analytics. Os envios para o servidor salvarão a dimensão resultante no conjunto de dados quando a convergência for concluída.

   Ao executar localmente, você verá o Construtor de Cluster mover-se por quatro estágios de clustering de cópia, pois ele define os centros inteligentes com base nas entradas.

   Quando os centros dos clusters deixarem de alterar mais do que o limite de convergência especificado, o Dimension de Cluster é convergente e o Construtor de Cluster exibe informações adicionais sobre a relevância de uma entrada para cada cluster.

1. Personalize os clusters.

   Clicar com o botão direito do mouse na barra de cores da estatística abre um menu de contexto que permite personalizar os limites de relevância e, no caso das distribuições de elementos de dimensão, escolher qual teste será exibido.

   ![](assets/build_cluster_7.png)

   As entradas de métrica fornecem um teste t para cada cluster, enquanto as entradas de elemento de dimensão fornecem três testes de distribuição (Qui ao quadrado, uma estatística U de entropia e a estatística V de Cramer) para cada cluster.

   >[!NOTE]
   >
   >Se você adicionar ou remover entradas durante a convergência, o processo será pausado até pressionar **Go** novamente.

   Depois de criar grupos, você pode abrir o seletor de cores para atribuir cores a diferentes resultados de distribuição.

   ![](assets/build_cluster_5.png)

1. Com o Cluster Dimension converged, é possível adicionar métricas à tabela e fazer seleções normalmente. Você também pode clicar com o botão direito do mouse nos nomes do elemento (Cluster 1, Cluster 2, etc.) para abrir o menu de contexto para renomeá-los para algo mais significativo.

   ![](assets/build_cluster_6.png)

1. Se quiser usar essa dimensão de cluster em outras visualizações, poderá **[!UICONTROL Save]** localmente ou **[!UICONTROL Submit]** no servidor.

Se você quiser executar a convergência novamente ou ver a relevância das entradas, o Construtor de Cluster também poderá carregar as dimensões do cluster existente.

>[!TIP]
>
>Quando selecionado, **[!UICONTROL Reset]** liberará completamente todas as variáveis de entrada e fornecerá uma visualização em branco do construtor de cluster para definir novos clusters.
