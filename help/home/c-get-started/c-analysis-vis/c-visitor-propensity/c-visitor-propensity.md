---
description: A pontuação de propensão permite definir clientes com base na possibilidade de uma conversão bem-sucedida ou a conclusão de um evento especificado. Ela permite maximizar o impacto potencial dos esforços antes de executar um processo ou direcionar uma campanha.
title: Pontuação de propensão
uuid: 4f7163f5-6fe4-4f87-9e27-71ec8b4717af
exl-id: 832a1e6c-8eeb-4dcc-97e8-9570e1a6eb4f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 24%

---

# Pontuação de propensão{#propensity-scoring}

A pontuação de propensão permite definir clientes com base na possibilidade de uma conversão bem-sucedida ou a conclusão de um evento especificado. Ela permite maximizar o impacto potencial dos esforços antes de executar um processo ou direcionar uma campanha.

## O valor da Classificação de propensão {#section-c51ece66effc42de9b754f0f46027c1b}

A pontuação de propensão permite executar a descoberta de dados para identificar comportamentos ou padrões ocultos existentes nos dados. Especificamente, a pontuação de propensão ajuda a identificar clusters de clientes semelhantes que usam meios mais objetivos e centralizados, em vez de filtragem ou segmentação simples. Além disso, a classificação de propensão permite que você configure recursos preditivos para identificar comportamentos de clientes importantes para a sua empresa.

Depois de identificar o público-alvo de grande importância, você pode engajá-los para atingir o efeito principal. Por exemplo, se você é de empresa de negócios, pode ter leads de vendas que permitem sua classificação e a identificação da probabilidade de conversão offline. Devido ao custo de cada lead, a criação de um incentivo para identificar possíveis clientes com a maior probabilidade de conversão de uma venda é a maneira mais eficaz e econômica de focar nos seus recursos.

A classificação de propensão fornece a capacidade de identificar os fatores mais preditivos de uma classificação específica, ou de identificar a probabilidade da ocorrência de um evento, mas também pode ser aplicada para responder às seguintes questões: O cliente fará a conversão? O cliente responderá a um email? O cliente fará uma nova compra? A classificação de propensão permite que você responda a essas perguntas e identifique visitantes que tenham uma inclinação a ações que podem ser configuradas e classificadas.

Além disso, você pode usar filtros para definir um subconjunto de visitantes a serem classificados usando o recurso opcional **[!UICONTROL Training Filter]**. Se nenhum filtro for aplicado, todos os visitantes serão direcionados para a pontuação.

## Recursos da visualização de pontuação de propensão {#section-28413bc7d33b42c59cecb427c1c5a3fa}

Para abrir a Visualização de pontuação de propensão, clique em **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

![](assets/propensity_visualization_GO.png)

A Visualização de pontuação de propensão inclui esses recursos acessíveis em sua barra de ferramentas:

| Recurso da barra de ferramentas | Descrição |
|---|---|
| Ir | Clique em para executar o processo de pontuação após configurar os parâmetros. |
| Redefinir | Limpar todas as configurações na visualização. |
| Load | Carrega um ScoreDim criado anteriormente que permite alterar e/ou recriar o modelo de pontuação. |
| Salvar | Salve a visualização Pontuação de propensão como um arquivo Dim para ser acessado e aberto conforme necessário. |
| Submit | Envie uma tarefa de pontuação para processamento no servidor. |
| Opções | Defina o Filtro de treinamento para limitar o subconjunto de visitantes. O filtro padrão é **[!UICONTROL Train on Everyone]**, mas você pode alterá-lo fazendo seleções de espaço de trabalho ou criando um filtro usando **[!UICONTROL Filter Editor]**. |
| Definir Target | Defina a variável dependente. |
| Métrica | Adicionar métricas como variáveis independentes. |
| Elementos | Arraste elementos Dimension usando as teclas `<Ctrl>` + `<Alt>` das tabelas de Dimension. |

**Consulte também**:

* Os gráficos [Ganho e Aumento](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a). Essas exibições podem ser abertas em um modelo de pontuação completo ou em [!DNL Add Visualization> Predictive Analytics > Scoring.]
* O [Visualizador de Modelo](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-d4fdf4b335c04b0ea07e70ab9a7ce9dd). Essas exibições podem ser abertas em um modelo de pontuação completo ou em [!DNL Add Visualization> Predictive Analytics > Scoring.]
* O recurso [Descrição de filtro complexo](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-complex-filter.md#concept-f9c55e54837f4b5995a00bc950ce5dff).

## Usar a visualização de Pontuação de propensão {#section-63ced03fa2eb44f2b8a98d61a6c88122}

* **Defina um ou mais filtros para definir a população de visitantes para pontuação**. Essa opção **[!UICONTROL Training Filter]** permite direcionar os visitantes com base nos critérios selecionados. Se nenhum filtro de treinamento for aplicado, todos os visitantes serão direcionados para a pontuação. Se o Filtro de treinamento estiver definido, o resultado da pontuação será significativo para a população de visitantes definida, embora cada visitante ainda tenha uma pontuação.
* **Identifique os visitantes** positivos. Para definir a variável dependente para especificar um filtro de direcionamento identificando os visitantes positivos que correspondem ao resultado desejado. Isso pode ser tão simples quanto Receita > US$ 10 ou um filtro muito mais complexo.
* **O filtro Target não pode ser o mesmo que o filtro** Treinamento. Logicamente, o Filtro de direcionamento deve ser uma adição ao Filtro de treinamento, resultando em um subconjunto positivo da população do visitante a ser pontuada.
* **Selecione variáveis de interesse (variáveis independentes) como entradas do algoritmo** de Pontuação de propensão . Essas podem ser métricas ou elementos individuais de um Dimension. A Pontuação de propensão começará o pré-processamento como em [Cluster do visitante](../../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d). O sistema começa a capturar uma certa quantidade de amostras que correspondem à definição do filtro de treinamento definido anteriormente (se houver). Atualmente, o tamanho da amostra é definido como 10% da população de pontuação (definida por filtro de treinamento), com no mínimo 20.000 e no máximo 100.000, e está vinculado ao tamanho da população de pontuação.

* Uma Dimension de Pontuação tem elementos que variam de 0% a 100% que determina a probabilidade dos visitantes corresponderem à variável do Target.
