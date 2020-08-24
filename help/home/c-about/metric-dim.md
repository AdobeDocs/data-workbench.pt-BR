---
description: Crie Dimension definidos pelos atributos de métrica (Dims de métrica) usando um assistente passo a passo. Em seguida, teste, pré-visualização e salve o novo Esmaecimento de métrica na lista de Dimension.
title: Assistente de atenuação de métrica
uuid: 411b2e28-0958-43bb-a853-7de7b3063818
translation-type: tm+mt
source-git-commit: 35e6e9280ab36e8b39e89039b791199d1de54e03
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 2%

---


# Assistente de atenuação de métrica{#metric-dim-wizard}

Crie Dimension definidos pelos atributos de métrica (Dims de métrica) usando um assistente passo a passo. Em seguida, teste, pré-visualização e salve o novo Esmaecimento de métrica na lista de Dimension.

Um Esmaecimento de métrica converte uma métrica em uma nova dimensão. Por exemplo, um Esmaecimento de métrica com base em uma métrica de Visualizações de página e nível de Visitante exibirá elementos de dimensão com base no total de Visualizações de página para cada Visitante. Ela permite estender uma métrica definida no momento com base em elementos de dimensão para criar e salvar como uma nova dimensão.

## Step 1: Select Dimension and Metric {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. Abra o Assistente de atenuação de métrica.

   Em um espaço de trabalho, clique com o botão direito do mouse e selecione **[!UICONTROL Tools]** > **[!UICONTROL Create Metric Dim]**.

1. Nomeie o Esmaecimento da métrica.

   Como padrão, o campo Nome será preenchido automaticamente com base nas seleções Nível e Métrica.

1. Selecione um Nível de Dimension.

   O nível de dimensão é a dimensão pai que contém todos os valores de elementos constituintes para filtrar a entrada e definir um tipo de dimensão.

   Os níveis de Dimension incluem:

   * Clickthrough
   * Ocorrência
   * Produto
   * Visita
   * Visitante.

1. Selecione uma métrica.

   Selecione uma métrica pré-criada para estender e salvar como uma métrica reduzida.

   ![](assets/6_4_workstation_metricdim_metric.png)

1. (opcional) Criar uma fórmula de métrica.

   Clique na caixa para inserir uma fórmula de métrica personalizada. O valor de Pré-visualização calculado aparecerá validando a expressão.

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   Você pode adicionar sua própria expressão [de](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html) métrica ou recortar e colar de outro editor de métricas ou visualização. Erros de sintaxe, erros de fórmula, filtros indefinidos e outros erros são relatados no assistente.

1. Clique em **[!UICONTROL Next]**.

## Etapa 2: Formatar e definir grupos {#section-5bddf3cd306545d7806a501637f80f77}

1. Selecione um formato para a nova métrica escurecer.

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   O formato define como a métrica será apresentada quando aberta em uma visualização. Esses formatos são padrões [](http://www.cplusplus.com/reference/cstdio/printf/)printf selecionados, definidos abaixo:

   ```
   %[flags][width][.precision][length][specifier]
   % 0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   No **[!UICONTROL Preview]** campo, um valor será exibido com base na métrica e no formato selecionados.

1. Adicionar expressão de contagem de balde.

   É possível definir um tamanho de métrica com vários intervalos ou cestos. Isso retorna subconjuntos de elementos com base no tamanho, como [0-4], [5-10],...). Os elementos do Nível de Dimension estão relacionados aos elementos cujo intervalo contém o valor da métrica. Consulte a descrição da expressão bucket em [Sintaxe para Dimension Expressão](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html).

1. Clique **[!UICONTROL Preview]** para abrir a tabela de valores de Métrica de Esmaecimento antes de salvar.

   ![](assets/6_4_workstation_metricdim_preview.png)

   A tabela detalha os valores de métrica por tamanho de métrica.

1. Clique **[!UICONTROL Show in Dimension Menu]** para adicionar a dimensão recém-criada à guia **Dimension** no **Finder**.

1. Clique em **[!UICONTROL Next]**.

## Etapa 3: Concluir e salvar {#section-d9043235b18a425f9de0db668d4b1683}

1. Selecione para iniciar o Editor de borda de métrica, a visualização de gráfico ou a tabela depois de salvar.

   | Campo | Descrição |
   |---|---|
   | **[!UICONTROL Launch Metric Dim Editor]** | Abra o Editor de atenuação de métrica. |
   | **[!UICONTROL Launch Graph]** | Inicie um gráfico PNG da tabela. |
   | **[!UICONTROL Launch Table]** | Inicie uma tabela no espaço de trabalho com valores em colunas listando valores da nova métrica em comparação com os valores da métrica selecionada. |

1. Clique em **[!UICONTROL Finish]** e salve.

   Uma caixa de diálogo para salvar será aberta permitindo que você salve o arquivo. As opções selecionadas para valores de visualização serão abertas no espaço de trabalho.

