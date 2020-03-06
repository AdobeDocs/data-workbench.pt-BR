---
description: A pontuação de propensão permite que você defina os clientes com base na possibilidade de uma conversão ou conclusão bem-sucedida de um evento especificado. Permite maximizar o impacto potencial dos esforços antes de executar um processo ou direcionar uma campanha.
solution: Analytics
title: Pontuação de propensão
topic: Data workbench
uuid: 4f7163f5-6fe4-4f87-9e27-71ec8b4717af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Pontuação de propensão{#propensity-scoring}

A pontuação de propensão permite que você defina os clientes com base na possibilidade de uma conversão ou conclusão bem-sucedida de um evento especificado. Permite maximizar o impacto potencial dos esforços antes de executar um processo ou direcionar uma campanha.

## O valor da Pontuação de propensão {#section-c51ece66effc42de9b754f0f46027c1b}

A pontuação de propensão permite que você realize a descoberta de dados para identificar comportamentos ou padrões ocultos que existem nos dados. Especificamente, a pontuação de propensão ajuda a identificar clusters de clientes semelhantes que usam meios mais objetivos e centralizados, em vez de filtragem ou segmentação simples. Além disso, a pontuação de propensão permite que você configure recursos preditivos para identificar comportamentos de clientes importantes para a sua empresa.

Depois de identificar o público-alvo de grande importância, você pode engajá-los para atingir o efeito principal. Por exemplo, se você for Empresa a Empresa, poderá ter clientes potenciais de vendas que lhe permitem pontuar os clientes potenciais e identificar sua probabilidade de conversão offline. Devido ao custo de cada lead, a criação de um incentivo para identificar possíveis clientes com a maior probabilidade de conversão de uma venda é a maneira mais eficaz e econômica de focar nos seus recursos.

A pontuação de propensão fornece a capacidade de identificar os fatores mais preditivos de uma classificação específica, ou de identificar a probabilidade da ocorrência de um evento, mas também pode ser aplicada para responder às seguintes questões: O cliente fará conversões? O cliente responderá a um email? O cliente fará outras compras? A pontuação de propensão permite que você responda a essas perguntas e identifique visitantes que tenham uma inclinação a ações que podem ser configuradas e classificadas.

Além disso, você pode usar filtros para definir um subconjunto de visitantes a serem pontuados usando o recurso opcional **[!UICONTROL Training Filter]** . Se nenhum filtro for aplicado, todos os visitantes serão direcionados para a pontuação.

## Recursos da Visualização de Pontuação de propensão {#section-28413bc7d33b42c59cecb427c1c5a3fa}

Para abrir a Visualização de pontuação de propensão, clique em **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

![](assets/propensity_visualization_GO.png)

A Visualização da Pontuação de propensão inclui estes recursos acessíveis em sua barra de ferramentas:

| Recurso da barra de ferramentas | Descrição |
|---|---|
| Ir | Clique para executar o processo de pontuação após configurar os parâmetros. |
| Reset | Limpe todas as configurações na visualização. |
| Load | Carrega um ScoreDim criado anteriormente que permite alterar e/ou recriar o modelo de pontuação. |
| Salvar | Salve a visualização de pontuação de propensão como um arquivo Dim para ser acessado e aberto, conforme necessário. |
| Enviar | Enviar tarefa de pontuação para processamento no servidor. |
| Opções | Defina o Filtro de treinamento para limitar o subconjunto de visitantes. O filtro padrão é **[!UICONTROL Train on Everyone]**, mas você pode alterá-lo fazendo seleções de espaço de trabalho ou criando um filtro usando o **[!UICONTROL Filter Editor]**. |
| Definir meta | Defina a variável dependente. |
| Métrica | Adicionar métricas como variáveis independentes. |
| Elementos | Arraste elementos de Dimensão usando as teclas `<Ctrl>` + `<Alt>` das tabelas de Dimensão. |

**Consulte também**:

* Os gráficos [Ganho e Levantamento](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a). Essas exibições podem ser abertas de um modelo de pontuação completo ou de [!DNL Add Visualization> Predictive Analytics > Scoring.]
* O Visualizador [de modelos](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-d4fdf4b335c04b0ea07e70ab9a7ce9dd). Essas exibições podem ser abertas de um modelo de pontuação completo ou de [!DNL Add Visualization> Predictive Analytics > Scoring.]
* O recurso Descrição [de filtro](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-complex-filter.md#concept-f9c55e54837f4b5995a00bc950ce5dff) complexo.

## Usando a visualização de Pontuação de propensão {#section-63ced03fa2eb44f2b8a98d61a6c88122}

* **Defina um ou mais filtros para definir a população do visitante para a pontuação**. Essa opção opcional **[!UICONTROL Training Filter]** permite direcionar os visitantes com base nos critérios selecionados. Se nenhum filtro de treinamento for aplicado, todos os visitantes serão direcionados para a pontuação. Se o Filtro de treinamento estiver definido, o resultado da pontuação será significativo para a população de visitantes definida, embora cada visitante ainda receba uma pontuação.
* **Identifique os visitantes** positivos. Para definir a variável dependente para especificar um filtro de destino identificando os visitantes positivos que correspondem ao resultado desejado. Isso pode ser tão simples quanto Receita > $10, ou um filtro muito mais complexo.
* **O filtro Target não pode ser igual ao filtro** Treinamento. Logicamente, o Filtro de meta deve ser uma adição ao Filtro de treinamento, resultando em um subconjunto positivo da população de visitantes a ser pontuado.
* **Selecione variáveis de interesse (variáveis independentes) como entradas para o algoritmo** de Pontuação de propensão. Podem ser Métricas ou elementos individuais de uma Dimensão. A Pontuação de propensão iniciará o pré-processamento, assim como no [Agrupamento](../../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d)de visitantes. O sistema começa a capturar uma determinada quantidade de amostras que corresponde à definição do filtro de treinamento definido anteriormente (se houver). Atualmente, o tamanho da amostra é definido como 10% da população de pontuação (definida pelo filtro de treinamento), com um mínimo de 20 mil e máximo de 100 mil, e está vinculado ao tamanho da população de pontuação.

* Uma Dimensão de pontuação tem elementos que variam de 0% a 100% que determinam a probabilidade dos visitantes corresponderem à variável do Target.

