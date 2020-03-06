---
description: Você pode usar planilhas para indicar que uma métrica atingiu um limite definido.
solution: Analytics
title: Criar um indicador de métrica
topic: Data workbench
uuid: da304004-ef45-4c89-8c91-dd5158172dd6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Criar um indicador de métrica{#create-a-metric-indicator}

Você pode usar planilhas para indicar que uma métrica atingiu um limite definido.

Além disso, você pode usar [!DNL Report] para gerar e distribuir automaticamente um relatório quando uma métrica atingir um limite definido dentro de um período de tempo especificado.

Para obter mais informações sobre [!DNL Report], consulte o Guia *de relatórios da Análise de* big data.

* [Indicador para cima ou para baixo](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)
* [Indicador de verificação](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)

**Para criar um indicador de métrica usando uma planilha**

1. Defina o conteúdo das células da planilha.

   1. Na Coluna A, digite o nome da métrica desejada (por exemplo, [!DNL Visitors]).
   1. Na Coluna B, digite o valor da métrica desejada (por exemplo, [!DNL =Visitors]).
   1. Na Coluna C, insira o limite inferior da métrica.
   1. Na Coluna D, insira o limite superior da métrica.
   1. Na coluna E, insira uma fórmula adequada. Para obter exemplos, consulte [Indicador](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba) para cima ou para baixo ou [Indicador](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)de verificação.
   1. Na célula da fórmula (Coluna E), clique com o botão direito do mouse e clique em **[!UICONTROL Format]** > **[!UICONTROL Indicator]**, em seguida, clique em uma das seguintes opções:

      * **[!UICONTROL None]**: Lista o cálculo exato em vez de um indicador.
      * **[!UICONTROL Check]**: Usa uma marca de seleção ou um X para indicar que o valor está acima ou abaixo do limite definido, dependendo da fórmula. Consulte [Verificar indicador](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090).
      * **[!UICONTROL Up or Down]**: Usa uma seta para cima ou para baixo para indicar se o valor está abaixo do limite baixo (seta para baixo), acima do limite alto (seta para cima) ou entre os limites baixo e alto (em branco). Consulte [Indicador](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)para cima ou para baixo.

1. Repita a Etapa 1 para outras métricas para as quais deseja criar indicadores.

A planilha resultante seria semelhante ao exemplo a seguir:

![](assets/vis_Worksheet_Alerts.png)

## Indicador para cima ou para baixo {#section-40d7a2c3df0d40d4a7bb1a7e856abcba}

Para a [!DNL Up] ou [!DNL Down indicator], use a seguinte fórmula:

[!DNL (metric value - low threshold)/(high threshold - low threshold)*2 - 1]

Por exemplo: [!DNL =(b2-c2)/(d2-c2)*2-1]

Três resultados são possíveis para cada métrica ao usar essa fórmula com o [!DNL Up] ou [!DNL Down indicator]:

* Se o valor da métrica estiver entre os limites baixo e alto, a fórmula avaliará para um número entre -1 e 1 (exclusivamente). A seta para cima ou para baixo não é exibida na planilha.
* Se o valor da métrica for menor ou igual ao limite inferior, a fórmula avaliará para um valor menor ou igual a -1. O indicador de métrica muda para uma seta para baixo.
* Se o valor da métrica for maior ou igual ao limite alto, a fórmula avaliará para um número maior ou igual a 1. O indicador de métrica muda para uma seta para cima.

A planilha a seguir ilustra o que a fórmula de exemplo [!DNL =(b2-c2)/(d2-c2)*2-1] exibiria:

![](assets/vis_Worksheet_Alerts_UpDown.png)

## Verificar indicador {#section-98c5298a74f34dcbaaf151549fcc7090}

Para o [!DNL Check indicator], use uma fórmula que indica se deseja ser notificado quando o valor da métrica estiver acima ou abaixo do limite especificado. Por exemplo:

* Se você quiser ser notificado quando o valor estiver abaixo do limite definido, use o seguinte formato:

   * [!DNL threshold - metric]

      Por exemplo: [!DNL =(c2-b2)]

* Se você quiser ser notificado quando o valor estiver acima do limite definido, use a seguinte fórmula:

   * [!DNL metric - threshold]

      Por exemplo: [!DNL =(b3-c3)]

Quando uma marca de seleção é exibida, a fórmula é avaliada como um número positivo. Quando um X é exibido, a fórmula é avaliada como um número negativo.

Há dois resultados possíveis para cada métrica ao usar o [!DNL Check indicator]:

* Se a fórmula indicar que é desejável manter o valor da métrica acima do limite, uma marca de seleção será exibida quando o valor da métrica for maior ou igual ao limite, e um X será exibido quando o valor for menor que o limite.
* Se a fórmula indicar que é desejável manter o valor da métrica abaixo do limite, uma marca de seleção será exibida quando o valor da métrica for menor ou igual ao limite, e um X será exibido quando o valor for maior que o limite.

A planilha a seguir ilustra quais fórmulas de exemplo [!DNL =(c2-b2)] e [!DNL =(b3-c3)] serão exibidas:

![](assets/vis_Worksheet_Alerts_Check.png)
