---
description: Os gráficos de radar fornecem foco rápido nas áreas que mais precisam de atenção, fornecendo uma visualização de um conjunto de métricas e como elas se relacionam ou diferem.
title: Visualização de radar
uuid: 39d67743-b6c1-46f1-99fd-7c71dfe07932
exl-id: 5385d903-422b-4936-bbb3-0d5ee4d286de
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 1%

---

# Visualização de radar{#radar-visualization}

Os gráficos de radar fornecem foco rápido nas áreas que mais precisam de atenção, fornecendo uma visualização de um conjunto de métricas e como elas se relacionam ou diferem.

Muitas vezes, você precisa de mais de uma métrica para entender e avaliar observações selecionadas em um espaço de trabalho.

Essa visualização é útil para comparações ou benchmarks entre as seleções de tabela. Por exemplo, você pode adicionar uma tabela de espaço de trabalho que lista lojas e, em seguida, adicionar uma visualização de radar com métricas como Receita, Visitantes e Exibições de página. (Como mostrado na tela no procedimento a seguir.) Conforme você faz seleções de lojas na tabela, o gráfico de radar muda, identificando pontos fracos ou pontos fortes nas métricas da loja selecionada.

Cada radial de um gráfico de radar é uma métrica e são necessárias no mínimo três métricas. Os dados da métrica são representados em relação a uma métrica ancorada. A métrica ancorada e o parâmetro Escala para âncora para cada métrica determinam o dimensionamento das métricas em relação aos benchmarks.

**Para criar uma visualização de radar**

1. Clique com o botão direito do mouse no Workspace e depois clique em **[!UICONTROL Visualization]** > **[!UICONTROL Radar]**.

   ![](assets/client-rad.png)

1. Para adicionar métricas, clique com o botão direito do mouse na visualização e selecione **[!UICONTROL Add Metric]**.
1. Para ancorar uma métrica no gráfico, clique com o botão direito do mouse em uma métrica e escolha a seguinte opção:

   **Âncora para essa métrica:** usa essa métrica como o referencial para o qual outras métricas são desenhadas. É possível ancorar uma métrica de cada vez. Cada métrica no gráfico é filtrada pela seleção do espaço de trabalho ativo ou por nenhum filtro. A relação de referência entre esses dois valores é representada no eixo entre o centro do gráfico e o nome da métrica no radar. Zero é traçado no centro.

1. Para dimensionar uma métrica com a métrica ancorada, clique com o botão direito do mouse na métrica e escolha a seguinte opção:

   **Escala com âncora:** quando ativada, o eixo desta métrica é dimensionado de forma que a proporção do referencial para a métrica de âncora selecionada seja representada no círculo, com zero no centro. Quando não selecionado, o círculo representa uma taxa de referência de 1. Normalmente, você ativa Escala com Âncora para métricas contáveis, como Visitantes ou Exibições de página, e a desativa para métricas de proporção, como Conversão, Duração média da sessão ou Exibições de página por sessão.
