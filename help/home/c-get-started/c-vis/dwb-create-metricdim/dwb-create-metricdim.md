---
description: Use o assistente de atenuação de métrica para criar um novo Dimension de métrica.
title: Assistente de atenuação de métrica
uuid: 77b9bc8e-7625-4fef-9de4-f113f9b2debd
exl-id: 109fbefc-5608-493d-aec9-8337f21eaa70
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 3%

---

# Assistente de atenuação de métrica{#metric-dim-wizard}

{{eol}}

Use o assistente de atenuação de métrica para criar um novo Dimension de métrica.

Uma atenuação de métrica converte uma métrica em uma nova dimensão. Por exemplo, uma atenuação de métrica com base em uma métrica de Exibições de página e nível de Visitante exibirá elementos de dimensão com base no total de Exibições de página para cada Visitante. Ela permite estender uma métrica definida no momento com base em elementos de dimensão para criar e salvar como uma nova dimensão.

## Etapa 1: selecionar dimensão e métrica {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. **Abra o Assistente de atenuação de métrica**.

   Em um espaço de trabalho, clique com o botão direito do mouse e selecione **Ferramentas** > **Criar atenuação de métrica**.

1. **Nomeie a atenuação de métrica**.

   Como padrão, o campo Nome será preenchido automaticamente com base nas seleções Nível e Métrica .

1. **Selecione um Nível de Dimension.** O nível de dimensão é a dimensão principal que contém todos os valores de elemento constituintes para filtrar a entrada e definir um tipo de dimensão.

   Os níveis de Dimension incluem:

   * Click-through
   * Ocorrência
   * Produto
   * Visita
   * Visitante

1. **Selecionar uma métrica**.

   Selecione uma métrica pré-criada para estender e salvar como um tamanho de métrica.

   ![](assets/6_4_workstation_metricdim_metric.png)

1. (opcional) **Criar fórmula de métrica**.

   Clique na caixa para inserir uma fórmula de métrica personalizada. O valor de Preview calculado será exibido validando a expressão.

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   Você pode adicionar seu próprio [expressão de métrica](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html) ou recorte e cole de outro editor de métricas ou visualização. Erros de sintaxe, erros de fórmula, filtros indefinidos e outros erros são relatados no assistente.

1. Clique em **Avançar**.

## Etapa 2: formatar e definir buckets {#section-5bddf3cd306545d7806a501637f80f77}

É possível selecionar o formato da métrica e definir os valores de categorias para uma expressão de dimensão.

1. Selecione um **Formato** para a nova métrica escurecer.

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   O formato define como a métrica será apresentada quando aberta em uma visualização. Esses formatos são selecionados [padrões printf](https://www.cplusplus.com/reference/cstdio/printf/), definido abaixo:

   ```
   %[flags][width][.precision][length][specifier]
   %
   0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   No **Visualizar** , um valor será exibido com base na métrica e no formato selecionados.

1. Adicionar **Contagem de bucket** expressão.

   Você pode definir uma escala de métrica com vários intervalos ou compartimentos. Isso retorna subconjuntos de elementos com base no tamanho, como [0-4], [5-10],...). Os elementos do Nível de Dimension estão relacionados aos elementos cujo intervalo contém o valor da métrica. Consulte a descrição da expressão de bucket em [Sintaxe para expressões Dimension](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html).

1. Clique em **Visualizar** para abrir a tabela de valores de atenuação de métrica antes de salvar.

   ![](assets/6_4_workstation_metricdim_preview.png)

   A tabela detalha os valores de métrica por escuta de métrica.

1. Clique em **Mostrar no Menu Dimension** para adicionar a dimensão recém-criada à variável **Dimension** na guia no **Localizador**.
1. Clique em **Avançar**.

## Etapa 3: terminar e salvar {#section-d9043235b18a425f9de0db668d4b1683}

1. Selecione para iniciar o Editor de atenuação de métrica, a visualização de gráfico ou a tabela após salvar.

   | Campo | Descrição |
   |---|---|
   | Iniciar Editor de atenuação de métrica | Abra o Editor de atenuação de métrica. |
   | Gráfico de lançamento | Inicie um gráfico PNG da tabela. |
   | Iniciar tabela | Inicie uma tabela no espaço de trabalho com valores em colunas listando valores da nova métrica em comparação com os valores da métrica selecionada. |

1. Clique em **Concluir** e salve.

   Uma caixa de diálogo de salvamento será aberta permitindo que você salve o arquivo. As opções selecionadas para exibir valores serão abertas no espaço de trabalho.
