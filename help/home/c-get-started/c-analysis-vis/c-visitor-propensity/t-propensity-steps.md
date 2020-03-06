---
description: Siga estas etapas para usar a visualização Pontuação de propensão.
solution: Analytics
title: Configurando Pontuação de Propensão
topic: Data workbench
uuid: afc9aada-3bf9-4ce6-8c43-a955771065b4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurando Pontuação de Propensão{#setting-up-propensity-scoring}

Siga estas etapas para usar a visualização Pontuação de propensão.

1. Abra um novo espaço de trabalho e clique em **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

   ![](assets/propensity_visualization.png)

1. Defina **[!UICONTROL Target]** (a variável dependente).

   Defina a variável dependente selecionando:

* **Elementos** de dimensão: Clique com o botão direito do mouse na área de trabalho e selecione **[!UICONTROL Table]**. Em seguida, selecione os elementos de uma Dimensão como sua variável dependente.

   OU

* **[!UICONTROL Filter Editor]**. Clique em **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Filter Editor]** para abrir a visualização do Editor de filtro.

   ![](assets/propensity_visualization_filter_editor.png)

   Depois de selecionar um elemento de Dimensão ou Filtro como a variável dependente, clique em **[!UICONTROL Set Target]**, digite um nome para descrever a variável dependente. Em seguida, clique **[!UICONTROL OK]** (e verifique se a caixa de filtro está realçada) para definir o Target.

   ![](assets/propensity_visualization_setTarget.png)

   O nome que você dá ao destino é a variável dependente que aparecerá no painel esquerdo.
1. Adicione variáveis independentes.

   Adicione as variáveis independentes usando Métricas ou Elementos de dimensão.

   ![](assets/propensity_visualization_metrics.png)

* **Métricas**. Na barra de ferramentas Pontuação de propensão, selecione uma métrica no **[!UICONTROL Metrics]** menu.

* **Elementos** de dimensão: Clique com o botão direito do mouse na área de trabalho e selecione **[!UICONTROL Table]**. Selecione um ou mais elementos de Dimensão e arraste para a coluna esquerda abaixo **[!UICONTROL Independent Variables]** ou para a **[!UICONTROL Element]** caixa usando as teclas `<Ctrl>` + `<Alt>` .

1. Defina **[!UICONTROL Training Filter]**. Você pode definir o conjunto de visitantes que deseja marcar clicando em **[!UICONTROL Options]** > **[!UICONTROL Set Training Filter]** na barra de ferramentas Pontuação de propensão. Isso fornecerá um subconjunto de dados criado usando apenas os visitantes que você deseja marcar. Por exemplo, quem visitou no mês passado, visitantes que residem na Austrália ou visitantes que visualizaram produtos específicos.

   O filtro padrão é **[!UICONTROL Train on Everyone]**, mas é possível alterá-lo ao ativar **[!UICONTROL Dimension Elements]** uma tabela ou criar um filtro usando o **[!UICONTROL Filter Editor]**.

   Depois de selecionar um elemento de Dimensão ou criar um filtro e, enquanto estiver ativado, clique em **Opções** > **Definir filtro** de treinamento, insira um nome para descrever o filtro e clique em **[!UICONTROL OK]**.
1. Depois de identificar todas as suas entradas, pressione **[!UICONTROL Go]**.

   ![](assets/propensity_visualization_GO.png)

   O processo de pontuação começará transmitindo os dados várias vezes. Em seguida, exibirá os resultados como gráficos de barra sobre uma linha de porcentagem.
1. Salvar pontuação de propensão.

   A partir do 6.1, agora você tem uma opção ao usar a opção Salvar pontuação de propensão:

* Dimensão
* Dimensão e métrica

   Você pode terminar com dois arquivos salvos, tanto uma dimensão quanto uma métrica definida.

   >[!NOTE]
   >
   >Se você enviar a Pontuação de propensão para processamento, obterá apenas uma dimensão.

   A métrica derivada é a métrica de pontuação média associada.
1. Verifique a precisão.

   O sistema exibirá **[!UICONTROL Model Complete]** e gerará um modelo de pontuação quando o processo for concluído.

   Clicar com o botão direito do mouse em **[!UICONTROL Model Complete]** identificará a precisão do modelo de pontuação conforme definido pelo sistema. Valores que variam de 0% a 100% identificarão a probabilidade dos visitantes corresponderem à **[!UICONTROL Target]** variável.

   A Matriz de Confusão fornece quatro contagens pela combinação de Positivo Real (AP), Negativo Real (AN), Positivo Previsto (PP) e Negativo Previsto (PN). Estes números são obtidos através da aplicação do modelo de pontuação resultante aos dados de testes 20% retidos, dos quais sabemos a verdadeira resposta. Se a pontuação for maior que 50%, será previsto como um caso positivo (correspondente ao evento definido).

   ![](assets/propensity_lift_gain_1.png)

<table id="table_154BDD6D294C4ED1B8C15EC33B74B199"> 
 <tbody> 
  <tr> 
   <td colname="col1"><b> Precisão</b> </td> 
   <td colname="col2"> Indica a precisão do modelo ao identificar as previsões corretas sobre todas as previsões. <p>(TP + TN)/(TP + FP + TN + FN) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> Recusar</b> </td> 
   <td colname="col2"> Identifica a capacidade de identificar novamente o modelo de pontuação. <p><b>TP / (TP + FN)</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> Precisão</b> </td> 
   <td colname="col2">Identifica o nível de discrepância. <p>TP / (TP + FP) </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Abra um gráfico [de](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a)elevação ou ganho ou o [Visualizador](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-9f2593a8218140b7bd132a4c74e159f9)de modelo.

   Clique com o botão direito do mouse na visualização **Modelo completo** e selecione **[!UICONTROL Lift Chart]**, **[!UICONTROL Gain Chart]** ou **[!UICONTROL Model Viewer.]**
