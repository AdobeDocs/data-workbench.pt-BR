---
description: As correlações estatísticas avaliam relacionamentos significativos para identificar oportunidades por meio de mineração de dados avançada.
title: Matriz de correlação
uuid: 7f6bdb65-dc31-4e27-9870-4c9402ee6031
exl-id: 79c23bb9-2b4b-4fe0-bfdb-52721fbbdf0c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 0%

---

# Matriz de correlação{#correlation-matrix}

{{eol}}

As correlações estatísticas avaliam relacionamentos significativos para identificar oportunidades por meio de mineração de dados avançada.

Empregando o [Coeficiente de correlação das pessoas](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c), a Matriz de correlação fornece informações relevantes para identificar melhor as próximas etapas de uma campanha de marketing, para melhorar o design do site ou para continuar a análise detalhada do cliente para dependências de correlação adicionais.

## Criar uma matriz de correlação {#section-87ed12ccc1af4196a1b6534e621c4cbb}

A Matriz de correlação compara métricas em uma dimensão contável ou não contável. A matriz pode então ser modificada para destacar as correlações na visualização por meio da escolha de cores ou para renderizá-la como um mapa de texto, mapa de calor ou ambos.

1. Abra uma Matriz de correlação.

   Clique com o botão direito do mouse em [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Correlation Matrix]. A tabela de dimensões será aberta.

   ![](assets/correlation_matrix_2.png)

   Selecione uma dimensão, como [!DNL Time] > [!DNL Day of the Week] desse menu. A tabela de correlação será aberta com a dimensão identificada no canto da matriz e sua métrica associada colocada na linha e na coluna. Para a dimensão Dia da semana , **[!UICONTROL Visits]** é a métrica associada.

   ![](assets/correlation_matrix_1.png)

   A correlação é 1.000 porque você está comparando uma métrica com ela mesma (o que reflete uma correlação perfeita, mas inutilizável).

1. Altere uma das métricas.

   Clique com o botão direito do mouse e selecione **[!UICONTROL Change Metric]** para alterar uma métrica na linha ou coluna. Isso configura uma correlação entre duas métricas de valor.

   Para este exemplo, altere a variável **[!UICONTROL Visits]** na coluna para **[!UICONTROL Internal Searches]**. Clique com o botão direito do mouse e selecione [!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Internal Searches].

   ![](assets/correlation_matrix_change_metric.png)

1. Adicione mais métricas à Matriz de correlação.

   Clique com o botão direito do mouse em uma coluna ou linha de métrica. Por exemplo, no menu Métrica , adicione [!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Sign in Error].

   ![](assets/correlation_matrix_11.png)

   A nova métrica aparecerá em uma coluna com um número de correlação. É possível adicionar outras métricas, como **[!UICONTROL Email Signups]**, para criar a tabela.

   ![](assets/correlation_matrix_6.png)

   Ou adicione métricas a linhas para comparar métricas em colunas.

   ![](assets/correlation_matrix_add_metric.png)

1. (opcional) Restrinja uma métrica adicionando um elemento de dimensão.

   Clique com o botão direito do mouse no espaço de trabalho e selecione **[!UICONTROL Table]**. Na tabela de dimensão aberta, pressione Ctrl + Alt e arraste o elemento sobre uma métrica em uma coluna ou linha. O elemento aparecerá ao lado da métrica entre parênteses.

   Por exemplo, para a variável **[!UICONTROL Visits]** , é possível restringi-la selecionando a variável **[!UICONTROL Country]** as **[!UICONTROL New Zealand]**.

   ![](assets/correlation_matrix_dim_element.png)

   Observe que ao selecionar um elemento de dimensão, a correlação muda em todas as métricas com base no elemento de dimensão selecionado. Somente a métrica Visita será restrita para &quot;Nova Zelândia&quot; após o fechamento da janela de dimensão.

   >[!NOTE]
   >
   >Se estiver alterando uma métrica com uma restrição de dimensão (clicando com o botão direito do mouse e selecionando **[!UICONTROL Change Metric]**), o elemento da dimensão que restringe a métrica será perdido. Você precisará adicionar o elemento da dimensão novamente.

1. Crie um [Filtro binário](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-binary-filter.md#concept-24e1daff43c540f69019f236976da31c) para restringir ainda mais a métrica. Clique com o botão direito do mouse na tabela e selecione Filtro binário no menu.

## Metas de análise e planejamento de correlação {#section-cc322da60b7e417ba29e72b0afeb6f79}

A seguir estão os objetivos gerais para criar uma Matriz de correlação.

**Identificar a relação entre duas métricas em relação a uma dimensão especificada**. No exemplo, a matriz foi criada em torno da dimensão principal, Dia da semana, com as métricas Visita, Assinaturas por email e Erros de logon em comparação aos eventos de métricas de Pesquisas internas, Logon e Pesquisa exibida.

**Desenvolver hipóteses para a análise de foco**. Após executar uma análise de correlação, o próximo passo é procurar dependências e correlação das métricas. Por exemplo, entender que pesquisas internas tem um efeito em inscrições por email fornece um caminho para prever essa relação e modificar campanhas de marketing ou design de navegação no site.

**Identificar métricas para incluir algoritmos de mineração de dados mais avançados**. Na maioria dos casos, as métricas principais serão identificadas porque serão vistas afetando várias correlações. Agora você pode usar essas métricas principais e aplicá-las à análise de mineração de dados adicional para obter um insight mais profundo.

## Notas de recursos da matriz de correlação {#section-ef3626c665ea468a9ecdad624b4132f5}

**Filtrar e selecionar em elementos de dimensão em uma tabela compara como valores**. Por exemplo, usar a dimensão Dia da semana e clicar em um elemento dessa dimensão principal, como clicar em um dia específico na tabela de dimensão Dia da semana, renderiza uma correspondência de 100% para 100% que não fornece correlação utilizável. Como a dimensão raiz era Dia da semana, qualquer seleção na tabela de dimensão Dia da semana alterará a matriz para ser uma correlação um para um.

![](assets/correlation_matrix_10.png)

No entanto, a correlação 1 a 1 (quando uma única seleção é feita de todos os elementos) é somente nesse dia específico. Se você fizer várias seleções, então, não necessariamente permanecerá uma correlação de 1 a 1 e nem sempre produzirá uma correspondência de 100% independentemente de selecionar 1 ou 1 ou mais dias da semana.

**Correlações estatísticas não são iguais ao Modelo de dados correlacionado**, a referência histórica dos produtos da Adobe Analytics. A correlação estatística no Data Workbench é baseada no [Modelo de Correlação Pearson](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c).

**Exibir correlação em um gráfico de dispersão**. Clique com o botão direito do mouse no título de um Gráfico de dispersão e escolha [!DNL Display Correlation] do [!DNL Visualization] menu. O valor de Correlação será exibido na seção superior direita do Gráfico de dispersão.

>[!NOTE]
>
>A matriz de Gráfico de Dispersão e Pearsons exibirá &quot;Erro de Cálculo&quot; se o aplicativo não conseguir executar o cálculo de correlação Pearsons. Isso geralmente ocorre devido a dados insuficientes, o que pode fazer com que a equação tente dividir por 0.
