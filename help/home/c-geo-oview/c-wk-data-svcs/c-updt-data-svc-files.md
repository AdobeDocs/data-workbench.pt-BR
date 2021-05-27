---
description: Se você assinar qualquer um dos serviços de dados, deve atualizar periodicamente os arquivos de serviço de dados fornecidos pelo Adobe.
title: Atualizar arquivos do serviço de dados
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
exl-id: bb92d40c-cc8d-4ecf-bd48-ed962fd5d73b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 1%

---

# Atualizar arquivos do serviço de dados{#updating-data-service-files}

Se você assinar qualquer um dos serviços de dados, deve atualizar periodicamente os arquivos de serviço de dados fornecidos pelo Adobe.

Para fazer isso, você deve ter acesso aos arquivos no servidor do Data Workbench.

Para carregar os arquivos de dados [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence], você deve concluir os seguintes procedimentos.

## Substituição do arquivo de dados {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. No Data Workbench, na guia [!DNL Admin] > [!DNL Dataset and Profile], clique na miniatura **[!UICONTROL Servers Manager]** para abrir o espaço de trabalho [!DNL Servers Manager].

1. Na janela [!DNL Servers Manager], clique com o botão direito do mouse no ícone do servidor do Data Workbench no qual deseja carregar os arquivos e clique em **[!UICONTROL Server Files]**.

1. No [!DNL Server Files Manager], clique com o botão direito do mouse na coluna **[!UICONTROL Temp]** para **[!UICONTROL Lookups\IP Geo-location]** ou **[!UICONTROL Lookups\IP Geo-intelligence]** e clique em **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]***.

1. Copie o arquivo de dados [!DNL .bin] fornecido pelo Adobe para a janela Lookups\IP Geo-location ou Lookups\IP Geo-intelligence folder .
1. Salve o arquivo na máquina do servidor do Data Workbench clicando com o botão direito do mouse na coluna [!DNL Temp] do arquivo de dados e clicando em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

   Se você estiver executando um cluster, faça upload dos arquivos para o servidor do Data Workbench principal no cluster.

## Atualizando a Transformação IPLookup {#section-a8b99afe3eb04afabe88e15bd465f935}

1. No [!DNL Profile Manager], clique em **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]** e **[!UICONTROL Geography]**.

1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL IP Lookup.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece na coluna [!DNL User].

1. Clique com o botão direito do mouse na nova marca de seleção e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Uma janela de configuração de transformação é exibida.

1. Na janela , clique em **[!UICONTROL Transformation]** e, em seguida, clique em **[!UICONTROL Transformations]**.

1. Localize e clique em **[!UICONTROL IPLookup Quova]** ou **[!UICONTROL IPLookup Digital Envoy]**.

1. Para o parâmetro File , atualize o nome do arquivo para corresponder ao nome do novo arquivo de dados ( [!DNL .bin]) fornecido pelo Adobe.
1. Salve o arquivo de configuração de transformação clicando com o botão direito do mouse em **[!UICONTROL (modified)]** na parte superior da janela de configuração e clicando em **[!UICONTROL Save]**.

1. Salve o arquivo de configuração modificado em cada perfil que usa o serviço de dados clicando com o botão direito do mouse na marca de seleção ao lado de [!DNL IP Lookup.cfg] na coluna [!DNL User] e clicando em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***. A retransformação dos dados começa após a sincronização do perfil do conjunto de dados.

   Para obter informações sobre a retransformação do conjunto de dados, consulte o capítulo Reprocessamento e retransformação do *Guia de Configuração do Conjunto de Dados*.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pelo Adobe (incluindo o perfil [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence]), pois as alterações são substituídas ao instalar atualizações nesses perfis.

Se você instalou o serviço de dados [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] para a versão 5.1 ou posterior, concluiu a atualização do serviço de dados. No entanto, se você instalou o serviço de dados [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] antes da versão 5.1, é necessário concluir os seguintes procedimentos adicionais.

## Substituição do arquivo de pesquisa {#section-ced1efa38a76419d812edd35423dbff7}

Você só deve concluir as etapas a seguir se tiver instalado o serviço de dados [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] antes da versão 5.1.

1. No [!DNL Server Files Manager], clique em **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** ou **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]** e, em seguida, clique em **[!UICONTROL Maps]** para visualizar o seu conteúdo.

1. Clique com o botão direito do mouse na coluna **[!UICONTROL Temp]** para **[!UICONTROL Maps]** e clique em **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]***.

1. Copie o novo arquivo [!DNL .txt] fornecido pelo Adobe para a janela Maps folder .
1. Salve o arquivo na máquina do servidor do Data Workbench clicando com o botão direito do mouse na marca de seleção na coluna [!DNL Temp] do arquivo [!DNL .txt] e clicando em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

>[!NOTE]
>
>Se você estiver executando um cluster, faça upload dos arquivos para o servidor do Data Workbench principal no cluster.

## Atualização dos arquivos de camada {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>Você só deve concluir as etapas a seguir se tiver instalado o serviço de dados [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] antes da versão 5.1.

Conclua essas etapas para cada arquivo de camada ( [!DNL .layer]) que faz referência ao arquivo de pesquisa [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] ( [!DNL .txt]).

1. Na pasta Profiles\*data service name*\Maps no diretório de instalação do servidor do Data Workbench, abra o arquivo [!DNL .layer] em um editor de texto como o Notepad.

1. No vetor [!DNL Data Paths], atualize o nome do arquivo de pesquisa [!DNL .txt] para corresponder ao nome do novo arquivo [!DNL .txt] fornecido pelo Adobe, conforme mostrado em destaque na seguinte amostra de arquivo:

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
1. Repita as Etapas 2 e 3 para cada arquivo [!DNL .layer] que faça referência ao arquivo [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] [!DNL .txt].
