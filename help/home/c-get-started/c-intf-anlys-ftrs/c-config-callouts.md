---
description: Os convites chamam a atenção para um elemento de dimensão específico ao criar uma nova visualização com uma seleção virtual de um elemento de dimensão específico em uma visualização.
solution: Analytics
title: Configurar uma chamada
topic: Data workbench
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurar uma chamada{#configure-a-callout}

Os convites chamam a atenção para um elemento de dimensão específico ao criar uma nova visualização com uma seleção virtual de um elemento de dimensão específico em uma visualização.

Você pode adicionar ou editar chamadas configurando os arquivos de chamada armazenados em uma pasta de instalação Perfis\*nome do perfil*\Context\Callout folder of the [!DNL Server] . Os avisos que chamam a atenção para uma métrica específica em uma visualização de planilha são chamados de chamadas de métricas. Os arquivos de chamada de métrica são armazenados em Perfis\*nome do perfil*\Context\Metric Callout folder.

Para obter instruções para adicionar um texto explicativo ou uma chamada de métrica a uma visualização, consulte [Adicionar textos explicativos a um espaço de trabalho](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0).

**Para criar um novo tipo de chamada**

1. Em qualquer espaço de trabalho, crie uma visualização que contenha os dados que você deseja que apareçam no novo tipo de chamada. Por exemplo, se você quiser que seu texto explicativo seja uma tabela, crie uma visualização de tabela mostrando a métrica e a dimensão desejadas.
1. Clique com o botão direito do mouse na borda superior da janela de chamada e clique em **[!UICONTROL Save]**.
1. Na [!DNL Save] janela, clique em ![](assets/btn_folder_up.png), clique duas vezes **[!UICONTROL Context]** e clique duas vezes **[!UICONTROL Callout]**. No [!DNL File Name] campo, digite um nome para o arquivo e clique em **[!UICONTROL Save]**. O arquivo de chamada é salvo no nome do perfil de trabalho do usuário\*\Context\Callout folder.

   >[!NOTE]
   >
   >Ao nomear seu texto explicativo, escolha um nome descritivo que reflita o tipo de visualização e a métrica e dimensão que ele mostra. Por exemplo, se você quiser criar um texto explicativo a partir de uma visualização de tabela mostrando a métrica Sessões na dimensão Dia, poderá nomear o texto explicativo &quot;Sessões por Tabela de Dias&quot;.

1. (Opcional) Para disponibilizar essa alteração para todos os usuários do perfil de trabalho:

   1. In the [!DNL Profile Manager], click **[!UICONTROL Context]**, then click **[!UICONTROL Callout]**. Essa pasta contém todos os arquivos de visualização ( [!DNL .vw]) que definem os tipos de chamada existentes.

   1. Clique com o botão direito do mouse na marca de seleção ao lado do nome do arquivo da nova chamada na [!DNL User] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

**Para alterar um texto explicativo para um texto explicativo de métrica**

1. In the [!DNL Profile Manager], click **[!UICONTROL Context]**, then click **[!UICONTROL Callout]**. Essa pasta contém todos os arquivos de visualização ( [!DNL .vw]) que definem os tipos de chamada existentes.

1. Clique com o botão direito do mouse na marca de seleção ao lado do nome do arquivo do tipo de chamada que você deseja alterar e clique em **[!UICONTROL Make Local]**. Depois que o arquivo for baixado para o computador local, uma marca de seleção aparecerá na [!DNL User] coluna.

1. Clique com o botão direito do mouse na marca de seleção ao lado do nome do arquivo na [!DNL User] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL In Notepad]**.

1. Localize a [!DNL metric_y = ref:] entrada no arquivo de chamada e substitua o valor existente pela palavra Métrica. O texto realçado no seguinte fragmento de arquivo mostra onde você insere essa palavra.

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

1. Clique em **[!UICONTROL File]** > **[!UICONTROL Save As]**. Na **[!UICONTROL Save As]** janela, clique uma vez e clique duas vezes **[!UICONTROL Metric Callout]**. No [!DNL File Name] campo, digite um nome para o arquivo e clique em **[!UICONTROL Save]**. O arquivo de chamada de métrica é salvo no nome do perfil de trabalho do usuário\*\Context\Metric Callout folder.

1. (Opcional) Para disponibilizar esse texto de chamada de métrica para todos os usuários do perfil de trabalho, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção ao lado do nome do arquivo na [!DNL User] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

