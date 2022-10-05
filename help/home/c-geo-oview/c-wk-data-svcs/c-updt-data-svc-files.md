---
description: Se você assinar qualquer um dos serviços de dados, deve atualizar periodicamente os arquivos de serviço de dados fornecidos pelo Adobe.
title: Atualizar arquivos do serviço de dados
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
exl-id: bb92d40c-cc8d-4ecf-bd48-ed962fd5d73b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 1%

---

# Atualizar arquivos do serviço de dados{#updating-data-service-files}

{{eol}}

Se você assinar qualquer um dos serviços de dados, deve atualizar periodicamente os arquivos de serviço de dados fornecidos pelo Adobe.

Para fazer isso, você deve ter acesso aos arquivos no servidor do Data Workbench.

Para carregar [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] arquivos de dados, você deve concluir os seguintes procedimentos.

## Substituição do arquivo de dados {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. No Data Workbench, no [!DNL Admin] > [!DNL Dataset and Profile] clique no botão **[!UICONTROL Servers Manager]** miniatura para abrir a [!DNL Servers Manager] espaço de trabalho.

1. No [!DNL Servers Manager] clique com o botão direito do mouse no ícone do servidor do Data Workbench no qual deseja carregar os arquivos e clique em **[!UICONTROL Server Files]**.

1. No [!DNL Server Files Manager], clique com o botão direito do mouse no **[!UICONTROL Temp]** coluna para **[!UICONTROL Lookups\IP Geo-location]** ou **[!UICONTROL Lookups\IP Geo-intelligence]** e clique em **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Copie o [!DNL .bin] arquivo de dados fornecido pelo Adobe para a janela Lookups\IP Geo-location ou Lookups\IP Geo-intelligence folder .
1. Salve o arquivo na máquina do servidor do Data Workbench clicando com o botão direito do mouse no [!DNL Temp] para o arquivo de dados e clicando em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

   Se você estiver executando um cluster, faça upload dos arquivos para o servidor do Data Workbench principal no cluster.

## Atualizando a Transformação IPLookup {#section-a8b99afe3eb04afabe88e15bd465f935}

1. No [!DNL Profile Manager], clique em **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]** e **[!UICONTROL Geography]**.

1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL IP Lookup.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece no [!DNL User] coluna.

1. Clique com o botão direito do mouse na nova marca de seleção e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Uma janela de configuração de transformação é exibida.

1. Na janela , clique em **[!UICONTROL Transformation]**, depois clique em **[!UICONTROL Transformations]**.

1. Localize e clique em **[!UICONTROL IPLookup Quova]** ou **[!UICONTROL IPLookup Digital Envoy]**.

1. Para o parâmetro File , atualize o nome do arquivo para corresponder ao nome dos novos dados ( [!DNL .bin]) arquivo fornecido pelo Adobe.
1. Salve o arquivo de configuração de transformação clicando com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela de configuração e clicando em **[!UICONTROL Save]**.

1. Salve o arquivo de configuração modificado em cada perfil que usa o serviço de dados clicando com o botão direito do mouse na marca de seleção ao lado de [!DNL IP Lookup.cfg] no [!DNL User] e clicando em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*. A retransformação dos dados começa após a sincronização do perfil do conjunto de dados.

   Para obter informações sobre a retransformação do conjunto de dados, consulte o capítulo Reprocessamento e retransformação do *Guia de configuração do conjunto de dados*.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pelo Adobe (incluindo o [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] , conforme suas alterações são substituídas ao instalar atualizações nesses perfis.

Se você instalou o [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] serviço de dados da versão 5.1 ou posterior, você concluiu a atualização do serviço de dados. No entanto, se você instalou o [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] serviço de dados antes da versão 5.1, você deve concluir os seguintes procedimentos adicionais.

## Substituição do arquivo de pesquisa {#section-ced1efa38a76419d812edd35423dbff7}

Você só deve concluir as etapas a seguir se tiver instalado a variável [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] serviço de dados anterior à versão 5.1.

1. No [!DNL Server Files Manager], clique em **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** ou **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]**, depois clique em **[!UICONTROL Maps]** para visualizar seu conteúdo.

1. Clique com o botão direito do mouse no **[!UICONTROL Temp]** coluna para **[!UICONTROL Maps]** e clique em **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Copie o novo [!DNL .txt] arquivo fornecido pelo Adobe para a janela Maps folder .
1. Salve o arquivo na máquina do servidor do Data Workbench clicando com o botão direito do mouse na marca de seleção no [!DNL Temp] para a coluna [!DNL .txt] e clicando em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Se você estiver executando um cluster, faça upload dos arquivos para o servidor do Data Workbench principal no cluster.

## Atualizar os arquivos de camada {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>Você só deve concluir as etapas a seguir se tiver instalado a variável [!DNL IP Geo-intelligence] e [!DNL IP Geo-location] serviço de dados anterior à versão 5.1.

Complete essas etapas para cada camada ( [!DNL .layer]) que faz referência ao arquivo [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] pesquisa ( [!DNL .txt]).

1. Na pasta Profiles\*data service name*\Maps no diretório de instalação do servidor do Data Workbench, abra o [!DNL .layer] em um editor de texto, como o Bloco de notas.

1. No [!DNL Data Paths] , atualize o nome do [!DNL .txt] arquivo de pesquisa para corresponder ao nome do novo [!DNL .txt] arquivo fornecido pelo Adobe, conforme destacado na seguinte amostra de arquivo:

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
1. Repita as etapas 2 e 3 para cada [!DNL .layer] que faz referência ao [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] [!DNL .txt] arquivo.
