---
description: Gráficos de radar fornecem foco rápido nas áreas que mais precisam de atenção, fornecendo uma visualização de um conjunto de métricas e como elas se relacionam ou diferem.
solution: Analytics
title: Visualização de radar
topic: Data workbench
uuid: 39d67743-b6c1-46f1-99fd-7c71dfe07932
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Visualização de radar{#radar-visualization}

Gráficos de radar fornecem foco rápido nas áreas que mais precisam de atenção, fornecendo uma visualização de um conjunto de métricas e como elas se relacionam ou diferem.

Muitas vezes, você precisa de mais de uma métrica para entender e avaliar as observações selecionadas em um espaço de trabalho.

Essa visualização é útil para comparações ou benchmarks entre as seleções de tabela. Por exemplo, você pode adicionar uma tabela de área de trabalho que lista lojas e adicionar uma visualização radar com métricas como Receita, Visitantes e Exibições de página. (Conforme mostrado na tela no procedimento a seguir.) À medida que você faz seleções de lojas na tabela, a área do gráfico de radar muda, identificando pontos fracos ou pontos fortes nas métricas da loja selecionada.

Cada radial de um gráfico de radar é uma métrica e são necessárias no mínimo três métricas. Os dados da métrica são representados em relação a uma métrica ancorada. A métrica ancorada e o parâmetro Escala para âncora para cada métrica determinam o dimensionamento das métricas em relação aos benchmarks.

**Para criar uma visualização radar**

1. Clique com o botão direito do mouse na Workspace e clique em **[!UICONTROL Visualization]** > **[!UICONTROL Radar]**.

   ![](assets/client-rad.png)

1. Para adicionar métricas, clique com o botão direito do mouse na visualização e selecione **[!UICONTROL Add Metric]**.
1. Para ancorar uma métrica ao gráfico, clique com o botão direito do mouse em uma métrica e escolha a seguinte opção:

   **Âncora para esta métrica:** Usa essa métrica como o benchmark para o qual outras métricas são desenhadas. É possível ancorar uma métrica por vez. Cada métrica no gráfico é filtrada pela seleção do espaço de trabalho ativo ou por nenhum filtro. A relação de referência entre esses dois valores é traçada no eixo entre o centro do gráfico e o nome da métrica no radar. Zero está representado no centro.

1. Para dimensionar uma métrica com a métrica ancorada, clique com o botão direito do mouse na métrica e escolha a seguinte opção:

   **Escala com âncora:** Quando ativada, o eixo dessa métrica é dimensionado de modo que a taxa de referência para a métrica de âncora selecionada seja plotada no círculo, com zero no centro. Quando não selecionado, o círculo representa uma taxa de referência de 1. Normalmente, você ativa Escala com Âncora para métricas contáveis, como Visitantes ou Exibições de página, e a desativa para métricas de proporção, como Conversão, Duração média da sessão ou Exibições de página por sessão.

