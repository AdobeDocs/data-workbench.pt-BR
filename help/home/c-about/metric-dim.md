---
description: Crie Dimension definidos por atributos de métrica (Dims de métrica) usando um assistente passo a passo. Em seguida, teste, visualize e salve a nova atenuação de métrica na sua lista de Dimension.
title: Assistente de atenuação de métrica
uuid: 411b2e28-0958-43bb-a853-7de7b3063818
exl-id: 4d283a00-409c-4d74-a558-40744caba71c
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 2%

---

# Assistente de atenuação de métrica{#metric-dim-wizard}

Crie Dimension definidos por atributos de métrica (Dims de métrica) usando um assistente passo a passo. Em seguida, teste, visualize e salve a nova atenuação de métrica na sua lista de Dimension.

Uma atenuação de métrica converte uma métrica em uma nova dimensão. Por exemplo, uma atenuação de métrica com base em uma métrica de Exibições de página e nível de Visitante exibirá elementos de dimensão com base no total de Exibições de página para cada Visitante. Ela permite estender uma métrica definida no momento com base em elementos de dimensão para criar e salvar como uma nova dimensão.

## Etapa 1: Selecionar Dimension e métrica {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. Abra o Assistente de atenuação de métrica.

   Em um espaço de trabalho, clique com o botão direito do mouse e selecione **[!UICONTROL Tools]** > **[!UICONTROL Create Metric Dim]**.

1. Nomeie a atenuação de métrica.

   Como padrão, o campo Nome será preenchido automaticamente com base nas seleções Nível e Métrica .

1. Selecione um Nível de Dimension.

   O nível de dimensão é a dimensão principal que contém todos os valores de elemento constituintes para filtrar a entrada e definir um tipo de dimensão.

   Os níveis de Dimension incluem:

   * Click-through
   * Ocorrência
   * Produto
   * Visita
   * Visitante

1. Selecione uma métrica.

   Selecione uma métrica pré-criada para estender e salvar como um tamanho de métrica.

   ![](assets/6_4_workstation_metricdim_metric.png)

1. (opcional) Criar uma fórmula de métrica.

   Clique na caixa para inserir uma fórmula de métrica personalizada. O valor de Preview calculado será exibido validando a expressão.

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   Você pode adicionar sua própria [expressão de métrica](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html) ou recortar e colar de outro editor de métricas ou visualização. Erros de sintaxe, erros de fórmula, filtros indefinidos e outros erros são relatados no assistente.

1. Clique em **[!UICONTROL Next]**.

## Etapa 2: Formatar e definir compartimentos {#section-5bddf3cd306545d7806a501637f80f77}

1. Selecione um formato para a nova métrica escurecer.

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   O formato define como a métrica será apresentada quando aberta em uma visualização. Esses formatos são selecionados [printf standards](https://www.cplusplus.com/reference/cstdio/printf/), definidos abaixo:

   ```
   %[flags][width][.precision][length][specifier]
   % 0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   No campo **[!UICONTROL Preview]**, um valor será exibido com base na métrica e no formato selecionados.

1. Adicionar expressão Contagem de Bucket.

   Você pode definir uma escala de métrica com vários intervalos ou compartimentos. Isso retorna subconjuntos de elementos com base no tamanho, como [0-4], [5-10],...). Os elementos do Nível de Dimension estão relacionados aos elementos cujo intervalo contém o valor da métrica. Consulte a descrição da expressão de bucket em [Sintaxe para expressões de Dimension](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html).

1. Clique em **[!UICONTROL Preview]** para abrir a tabela de valores de atenuação de métrica antes de salvar.

   ![](assets/6_4_workstation_metricdim_preview.png)

   A tabela detalha os valores de métrica por escuta de métrica.

1. Clique em **[!UICONTROL Show in Dimension Menu]** para adicionar a dimensão recém-criada à guia **Dimension** no **Localizador**.

1. Clique em **[!UICONTROL Next]**.

## Etapa 3: Concluir e salvar {#section-d9043235b18a425f9de0db668d4b1683}

1. Selecione para iniciar o Editor de atenuação de métrica, a visualização de gráfico ou a tabela após salvar.

   | Campo | Descrição |
   |---|---|
   | **[!UICONTROL Launch Metric Dim Editor]** | Abra o Editor de atenuação de métrica. |
   | **[!UICONTROL Launch Graph]** | Inicie um gráfico PNG da tabela. |
   | **[!UICONTROL Launch Table]** | Inicie uma tabela no espaço de trabalho com valores em colunas listando valores da nova métrica em comparação com os valores da métrica selecionada. |

1. Clique em **[!UICONTROL Finish]** e salve.

   Uma caixa de diálogo de salvamento será aberta permitindo que você salve o arquivo. As opções selecionadas para exibir valores serão abertas no espaço de trabalho.
