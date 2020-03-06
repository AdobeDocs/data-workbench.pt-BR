---
description: Correlações estatísticas medem relações significativas para identificar oportunidades por meio de mineração avançada de dados.
solution: Analytics
title: Matriz de correlação
topic: Data workbench
uuid: 7f6bdb65-dc31-4e27-9870-4c9402ee6031
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Matriz de correlação{#correlation-matrix}

Correlações estatísticas medem relações significativas para identificar oportunidades por meio de mineração avançada de dados.

Utilizando o coeficiente [de correlação](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c)Pearsons, a Matriz de correlação fornece informações relevantes para identificar melhor as próximas etapas de uma campanha de marketing, aprimorar o design do site ou continuar a análise detalhada do cliente para obter outras dependências de correlação.

## Construção de uma matriz de correlação {#section-87ed12ccc1af4196a1b6534e621c4cbb}

A Matriz de correlação compara métricas sobre uma dimensão contável ou não contável. A matriz pode então ser modificada para realçar correlações na visualização por meio da seleção de cores ou para renderizá-la como um mapa de texto, mapa de calor ou ambos.

1. Abra uma Matriz de correlação.

   Clique com o botão direito do mouse em [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Correlation Matrix]. A tabela de dimensões será aberta.

   ![](assets/correlation_matrix_2.png)

   Selecione uma dimensão, como [!DNL Time] > [!DNL Day of the Week] , neste menu. A tabela de correlação será aberta com a dimensão identificada no canto da matriz e sua métrica associada colocada na linha e na coluna. Para a dimensão Dia da semana, **[!UICONTROL Visits]** é a métrica associada.

   ![](assets/correlation_matrix_1.png)

   A correlação é 1.000 porque você está comparando uma métrica com ela mesma (o que reflete uma correlação perfeita, mas inutilizável).

1. Altere uma das métricas.

   Clique com o botão direito do mouse e selecione **[!UICONTROL Change Metric]** para alterar uma métrica na linha ou na coluna. Isso configura uma correlação entre duas métricas de valor.

   Neste exemplo, altere a **[!UICONTROL Visits]** métrica na coluna para **[!UICONTROL Internal Searches]**. Clique com o botão direito do mouse e selecione [!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Internal Searches].

   ![](assets/correlation_matrix_change_metric.png)

1. Adicione mais métricas à Matriz de correlação.

   Clique com o botão direito do mouse em uma coluna ou linha de métrica. Por exemplo, no menu Métrica, adicione [!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Sign in Error].

   ![](assets/correlation_matrix_11.png)

   A nova métrica aparecerá em uma coluna com um número de correlação. É possível adicionar outras métricas, como **[!UICONTROL Email Signups]**, para criar a tabela.

   ![](assets/correlation_matrix_6.png)

   Ou adicione métricas a linhas para comparar métricas em colunas.

   ![](assets/correlation_matrix_add_metric.png)

1. (opcional) Restrinja uma métrica adicionando um elemento de dimensão.

   Clique com o botão direito do mouse na área de trabalho e selecione **[!UICONTROL Table]**. Na tabela de dimensão aberta, pressione Ctrl + Alt e arraste o elemento sobre uma métrica em uma coluna ou linha. O elemento aparecerá ao lado da métrica entre colchetes.

   Por exemplo, para a **[!UICONTROL Visits]** métrica, é possível restringi-la selecionando o **[!UICONTROL Country]** como **[!UICONTROL New Zealand]**.

   ![](assets/correlation_matrix_dim_element.png)

   Observe que ao selecionar um elemento de dimensão, a correlação muda em todas as métricas com base no elemento de dimensão selecionado. Somente a métrica Visita será restrita a &quot;Nova Zelândia&quot; quando a janela de dimensão for fechada.

   >[!NOTE]
   >
   >Se uma métrica for alterada com uma restrição de dimensão (clicando com o botão direito do mouse e selecionando **[!UICONTROL Change Metric]**), o elemento de dimensão que restringe a métrica será perdido. Será necessário adicionar o elemento de dimensão novamente.

1. Crie um Filtro [](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-binary-filter.md#concept-24e1daff43c540f69019f236976da31c) binário para restringir ainda mais a métrica. Clique com o botão direito do mouse na métrica na tabela e selecione Filtro binário no menu.

## Metas de Análise e Planejamento de Correlação {#section-cc322da60b7e417ba29e72b0afeb6f79}

A seguir estão os objetivos gerais para criar uma Matriz de correlação.

**Identifique a relação entre duas métricas em relação a uma dimensão** especificada. No exemplo, a matriz foi construída em torno da dimensão principal, Dia da semana, com as métricas Visita, Assinaturas por email e Erros de logon em comparação a Pesquisas internas, Login e Pesquisas exibidas.

**Desenvolva hipóteses para focar a análise**. Após executar uma análise de correlação, sua próxima etapa é procurar dependências e correlação das métricas. Por exemplo, entender que pesquisas internas tem um efeito em inscrições por email fornece um caminho para prever essa relação e modificar campanhas de marketing ou design de navegação do site.

**Identifique métricas para incluir algoritmos** de mineração de dados mais avançados. Na maioria dos casos, as métricas principais serão identificadas porque serão vistas afetando várias correlações. Agora você pode usar essas métricas principais e aplicá-las a análises adicionais de mineração de dados para obter uma visão mais profunda.

## Notas de recurso da matriz de correlação {#section-ef3626c665ea468a9ecdad624b4132f5}

**Filtrar e selecionar em elementos de dimensão em uma tabela compara como valores**. Por exemplo, usar a dimensão Dia da semana e clicar em um elemento dessa dimensão principal, como clicar em um dia específico na tabela de dimensão Dia da semana, renderiza uma correspondência de 1 a 100% que não fornece correlação utilizável. Como a dimensão raiz era Dia da semana, qualquer seleção na tabela de dimensão Dia da semana alterará a matriz para ser uma correlação um para um.

![](assets/correlation_matrix_10.png)

No entanto, a correlação 1 a 1 (quando uma única seleção é feita de todos os elementos) é somente nesse dia específico. Se você fizer várias seleções, isso não permanecerá necessariamente uma correlação de 1 a 1 e nem sempre resultará em uma correspondência de 100%, independentemente da seleção de 1 ou 1 ou mais dias da semana.

**As correlações estatísticas não são iguais ao Modelo** de dados correlacionados, a referência histórica dos produtos do Adobe Analytics. A correlação estatística na análise de big data é baseada no modelo [de Correlação](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c)Pearson.

**Exibir correlação em um gráfico de dispersão**. Clique com o botão direito do mouse no título de um Gráfico de dispersão e escolha [!DNL Display Correlation] no [!DNL Visualization] menu. O valor de Correlação será exibido na seção superior direita do Gráfico de dispersão.

>[!NOTE]
>
>A matriz Gráfico de dispersão e Pearsons exibirá &quot;Erro de cálculo&quot; se o aplicativo não conseguir executar o cálculo de correlação Pearsons. Isso geralmente ocorre devido a dados insuficientes, o que pode fazer com que a equação tente dividir por 0.
