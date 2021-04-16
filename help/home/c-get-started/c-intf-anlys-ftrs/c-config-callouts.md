---
description: As chamadas de retorno chamam a atenção para um elemento de dimensão específico ao criar uma nova visualização com uma seleção virtual de um elemento de dimensão específico em uma visualização.
title: Configurar uma chamada
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
exl-id: 509163b2-0bd1-47b4-8612-aac460a501cc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 1%

---

# Configurar uma chamada{#configure-a-callout}

As chamadas de retorno chamam a atenção para um elemento de dimensão específico ao criar uma nova visualização com uma seleção virtual de um elemento de dimensão específico em uma visualização.

Você pode adicionar ou editar chamadas configurando os arquivos de chamada armazenados em uma pasta de instalação Profiles\*nome do perfil*\Context\Callout folder of the [!DNL Server] . As chamadas de retorno que chamam a atenção para uma métrica específica em uma visualização da planilha são chamadas de chamadas de métricas. Os arquivos de chamada de métrica são armazenados em Profiles\*nome do perfil*\Context\Metric Callout folder.

Para obter instruções para adicionar uma chamada ou chamada de métrica a uma visualização, consulte [Adicionar chamadas de retorno a um espaço de trabalho](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0).

**Para criar um novo tipo de chamada**

1. Em qualquer espaço de trabalho, crie uma visualização contendo os dados que você deseja que apareçam no novo tipo de chamada. Por exemplo, se você quiser que sua chamada seja uma tabela, crie uma visualização de tabela mostrando a métrica e a dimensão desejadas.
1. Clique com o botão direito do mouse na borda superior da janela de chamada e clique em **[!UICONTROL Save]**.
1. Na janela [!DNL Save], clique em ![](assets/btn_folder_up.png), clique duas vezes em **[!UICONTROL Context]** e clique duas vezes em **[!UICONTROL Callout]**. No campo [!DNL File Name], digite um nome para o arquivo e clique em **[!UICONTROL Save]**. O arquivo de chamada é salvo no User\*nome do perfil de trabalho*\Context\Callout folder.

   >[!NOTE]
   >
   >Ao dar um nome para a sua chamada , escolha um nome descritivo que reflita o tipo de visualização e a métrica e dimensão que ela mostra. Por exemplo, se você quiser criar uma chamada a partir de uma visualização de tabela mostrando a métrica Sessões na dimensão Dia , é possível nomear a chamada &quot;Sessões por tabela do dia&quot;.

1. (Opcional) Para disponibilizar essa alteração para todos os usuários do perfil de trabalho:

   1. No [!DNL Profile Manager], clique em **[!UICONTROL Context]** e em **[!UICONTROL Callout]**. Esta pasta contém todos os arquivos de visualização ( [!DNL .vw]) que definem os tipos de chamada de saída existentes.

   1. Clique com o botão direito do mouse na marca de seleção ao lado do nome do arquivo da nova chamada na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.

**Para alterar uma chamada para uma chamada de métrica**

1. No [!DNL Profile Manager], clique em **[!UICONTROL Context]** e em **[!UICONTROL Callout]**. Esta pasta contém todos os arquivos de visualização ( [!DNL .vw]) que definem os tipos de chamada de saída existentes.

1. Clique com o botão direito do mouse na marca de seleção ao lado do nome do arquivo do tipo de chamada que você deseja alterar e clique em **[!UICONTROL Make Local]**. Após o download do arquivo para o computador local, uma marca de seleção aparece na coluna [!DNL User].

1. Clique com o botão direito do mouse na marca de seleção ao lado do nome do arquivo na coluna [!DNL User] e clique em **[!UICONTROL Open]** > **[!UICONTROL In Notepad]**.

1. Localize a entrada [!DNL metric_y = ref:] no arquivo de chamada e substitua o valor existente pela palavra Métrica. O texto destacado no seguinte fragmento de arquivo mostra onde você insere essa palavra.

   ```
   window = simpleBorderWindow: 
     client = graph: 
       bars = bool: true
       dim_x = ref: wdata/model/dim/dimension name
       lines = bool: false
       metrics = vector: 1 items
         0 = gr_metric: 
           metric_y = ref: Metric
           yaxis = axisLegend: 
             max_value = double: maximum y-value
             min_value = double: minimum y-value
             zoom_max = double: maximum y-zoom
             zoom_min = double: minimum y-zoom
   . . . 
   ```

1. Clique em **[!UICONTROL File]** > **[!UICONTROL Save As]**. Na janela **[!UICONTROL Save As]**, clique uma vez e, em seguida, clique duas vezes em **[!UICONTROL Metric Callout]**. No campo [!DNL File Name], digite um nome para o arquivo e clique em **[!UICONTROL Save]**. O arquivo de chamada de métrica é salvo no User\*nome do perfil de trabalho*\Context\Metric Callout folder.

1. (Opcional) Para disponibilizar essa chamada de métrica para todos os usuários do perfil de trabalho, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção ao lado do nome do arquivo na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.
