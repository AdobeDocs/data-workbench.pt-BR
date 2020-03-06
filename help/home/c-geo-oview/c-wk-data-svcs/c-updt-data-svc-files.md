---
description: Se você assinar qualquer um dos serviços de dados, deverá atualizar periodicamente os arquivos de serviço de dados fornecidos pela Adobe.
solution: Analytics
title: Atualização de arquivos do serviço de dados
topic: Data workbench
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Atualização de arquivos do serviço de dados{#updating-data-service-files}

Se você assinar qualquer um dos serviços de dados, deverá atualizar periodicamente os arquivos de serviço de dados fornecidos pela Adobe.

Para fazer isso, você deve ter acesso aos arquivos no servidor da análise de big data.

Para carregar [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] arquivos de dados, você deve concluir os procedimentos a seguir.

## Substituição do arquivo de dados {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. Na análise de big data, na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a [!DNL Servers Manager] área de trabalho.

1. Na [!DNL Servers Manager] janela, clique com o botão direito do mouse no ícone do servidor da análise de big data no qual você deseja carregar os arquivos e clique em **[!UICONTROL Server Files]**.

1. Na [!DNL Server Files Manager], clique com o botão direito do mouse na **[!UICONTROL Temp]** coluna para **[!UICONTROL Lookups\IP Geo-location]** ou **[!UICONTROL Lookups\IP Geo-intelligence]** e clique em **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Copie o arquivo de [!DNL .bin] dados fornecido pela Adobe para a janela Lookups\IP Geo-location ou Lookups\IP Geo-Intelligence folder.
1. Salve o arquivo na máquina do servidor da análise de big data clicando com o botão direito do mouse na [!DNL Temp] coluna do arquivo de dados e clicando em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

   Se você estiver executando um cluster, faça upload dos arquivos para o servidor de análise de big data mestre no cluster.

## Atualização da transformação IPLookup {#section-a8b99afe3eb04afabe88e15bd465f935}

1. No [!DNL Profile Manager], clique em **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]** e **[!UICONTROL Geography]**.

1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL IP Lookup.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção para este arquivo é exibida na [!DNL User] coluna.

1. Clique com o botão direito do mouse na nova marca de seleção e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Uma janela de configuração de transformação é exibida.

1. Na janela, clique em **[!UICONTROL Transformation]**, em seguida, clique em **[!UICONTROL Transformations]**.

1. Localize e clique em **[!UICONTROL IPLookup Quova]** ou **[!UICONTROL IPLookup Digital Envoy]**.

1. Para o parâmetro Arquivo, atualize o nome do arquivo para corresponder ao nome do novo arquivo de dados ( [!DNL .bin]) fornecido pela Adobe.
1. Salve o arquivo de configuração de transformação clicando com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela de configuração e clicando em **[!UICONTROL Save]**.

1. Salve o arquivo de configuração modificado em cada perfil que usa o serviço de dados clicando com o botão direito do mouse na marca de seleção ao lado [!DNL IP Lookup.cfg] da coluna [!DNL User] e clicando em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*. A retransformação dos dados começa após a sincronização do perfil do conjunto de dados.

   Para obter informações sobre a retransformação do conjunto de dados, consulte o capítulo Reprocessamento e retransformação do Guia *de Configuração do* Conjunto de Dados.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pela Adobe (incluindo o perfil [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] ), pois suas alterações são substituídas quando você instala atualizações nesses perfis.

Se você instalou o serviço de dados [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] para a versão 5.1 ou posterior, você concluiu a atualização do serviço de dados. No entanto, se você instalou o serviço de dados [!DNL IP Geo-intelligence] [!DNL IP Geo-location] e dados antes da versão 5.1, é necessário concluir os procedimentos adicionais a seguir.

## Substituição do arquivo de pesquisa {#section-ced1efa38a76419d812edd35423dbff7}

Você só deve concluir as etapas a seguir se tiver instalado o serviço de dados [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] dados antes da versão 5.1.

1. Na página [!DNL Server Files Manager], clique em **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** ou **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]** e, em seguida, clique em **[!UICONTROL Maps]** para exibir seu conteúdo.

1. Clique com o botão direito do mouse na **[!UICONTROL Temp]** coluna para **[!UICONTROL Maps]** e clique em **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Copie o novo [!DNL .txt] arquivo fornecido pela Adobe para a janela da pasta Maps.
1. Salve o arquivo na máquina do servidor da análise de big data clicando com o botão direito do mouse na marca de seleção na [!DNL Temp] coluna do [!DNL .txt] arquivo e clicando em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Se você estiver executando um cluster, faça upload dos arquivos para o servidor de análise de big data mestre no cluster.

## Atualização dos arquivos de camada {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>Você só deve concluir as etapas a seguir se tiver instalado o serviço de dados [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] dados antes da versão 5.1.

Complete estas etapas para cada arquivo de camada ( [!DNL .layer]) que faz referência ao arquivo de pesquisa [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] pesquisa ( [!DNL .txt]).

1. Na pasta Perfis\*nome do serviço de dados*\Maps no diretório de instalação do servidor da análise de big data, abra o [!DNL .layer] arquivo em um editor de texto, como o Bloco de notas.

1. No [!DNL Data Paths] vetor, atualize o nome do arquivo de [!DNL .txt] pesquisa para corresponder ao nome do novo [!DNL .txt] arquivo fornecido pela Adobe, como mostrado realçado na seguinte amostra de arquivo:

   ```
   Layer = ElementPointLayer:
     Data Paths = vector: 1 items
       0 = Path: Maps\\LookupFileName.txt
     Longitude Column = string: LongitudeColumnName
     Latitude Column = string: LatitudeColumnName
     Name Column = string: LocationColumnName
     Key Column = string: KeyColumnName
     Dimension = ref: wdata/model/dim/DimensionName
     Metric = ref: wdata/model/metric/MetricName
   ```

1. Salve o arquivo de camada atualizado.
1. Repita as Etapas 2 e 3 para cada [!DNL .layer] arquivo que fizer referência ao arquivo [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location][!DNL .txt] .

