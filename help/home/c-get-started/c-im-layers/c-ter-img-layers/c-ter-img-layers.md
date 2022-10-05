---
description: Uma camada de imagem do terreno exibe imagens do terreno da Terra.
title: Camadas de imagem do terreno
uuid: 17968293-1ad2-4040-a174-d33f418af9b7
exl-id: 754211a7-0b1f-4353-86f8-9c634d70cd83
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 2%

---

# Camadas de imagem do terreno{#terrain-image-layers}

{{eol}}

Uma camada de imagem do terreno exibe imagens do terreno da Terra.

[!DNL Terrain image layers] são armazenadas no [!DNL Geography] em um formato personalizado. Essas camadas de imagem podem ser geradas pelo Adobe ou o servidor do Data Workbench pode transformar as imagens do terreno fornecidas pelo usuário em camadas do terreno adequadas para uso na visualização do globo.

>[!NOTE]
>
>Para trabalhar com [!DNL terrain image layers], instale o [!DNL Terrain Images.cfg] arquivo fornecido pelo Adobe.

Para definir uma camada de imagem do terreno, você deve ter o seguinte:

* **Um ou mais arquivos de imagem do terreno** contendo as imagens a serem exibidas em todo o mundo.
* **A [!DNL Terrain Images.cfg] arquivo** que especifica os arquivos de imagem do terreno a serem usados para a(s) camada(s). O [!DNL Terrain Images.cfg] permite adicionar uma ou mais fontes para criar um [!DNL terrain image layer]. O formato do arquivo de imagem do terreno determina o tipo de fonte que deve ser adicionada. A tabela a seguir fornece descrições das fontes de camada de imagem do terreno disponíveis, incluindo os formatos de arquivo de imagem do terreno suportados:

<table id="table_CFDF5E61FCCD40B29A9D35FFA42F68D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Mapa de bits bruto não projetado </p> </td> 
   <td colname="col2"> <p>Cria <span class="wintitle"> camadas de imagem do terreno</span> a partir de arquivos de RGB sem cabeçalho de 24 bits que são alinhados por latitude (não projetados), onde norte é o topo da imagem e leste é o lado direito. </p> <p>Formato(s) de imagem suportado(s): BRUTO </p> <p> <p>Observação: Esta fonte requer informações de projeção. Para obter informações sobre formatos de projeção, consulte <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Especificar informações de projeção para imagens do terreno</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imagem geral, não projetada </p> </td> 
   <td colname="col2"> <p>Cria <span class="wintitle"> camadas de imagem do terreno</span> a partir de formatos de imagem de 24 bits, alinhados por latitude (não projetados), onde norte é o topo da imagem e leste é o lado direito. </p> <p>Formato(s) de imagem suportado(s): BMP, JPG, PNG, TIFF </p> <p> <p>Observação: Esta fonte requer informações de projeção. Para obter informações sobre formatos de projeção, consulte <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Especificar informações de projeção para imagens do terreno</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imagem com projeção incorporada </p> </td> 
   <td colname="col2"> <p>Cria <span class="wintitle"> camadas de imagem do terreno</span> nos formatos de imagem que incorporam dados geodésicos no arquivo de imagem. As informações de projeção são extraídas da imagem. </p> <p>Formato(s) de imagem suportado(s): Erdas (IMG), GeoTIFF </p> <p> <p>Observação: Esta fonte geralmente não requer informações de projeção, mas suporta a adição dessas informações, se necessário. Para obter informações sobre formatos de projeção, consulte <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Especificar informações de projeção para imagens do terreno</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Definição de uma camada de imagem do terreno**

1. Na Data Workbench, no **[!UICONTROL Admin]** > **[!UICONTROL Dataset and Profile]** clique no botão **[!UICONTROL Servers Manager]** miniatura para abrir a [!DNL Servers Manager] espaço de trabalho.
1. No [!DNL Servers Manager] , clique com o botão direito do mouse no ícone do servidor do Data Workbench desejado e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para visualizar seu conteúdo. O [!DNL Terrain Images.cfg] O arquivo está localizado dentro desse diretório.
1. Clique com o botão direito do mouse na marca de seleção na coluna de nome do servidor para [!DNL Terrain Images.cfg], depois clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece no [!DNL Temp] coluna para [!DNL Terrain Images.cfg].
1. Clique com o botão direito do mouse na marca de seleção recém-criada na **[!UICONTROL Temp]** e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. O [!DNL Terrain Images.cfg] será exibida.
1. No [!DNL Terrain Images] , clique em **[!UICONTROL component]** para visualizar seu conteúdo.
1. Clique com o botão direito do mouse **[!UICONTROL Sources]** > **[!UICONTROL Add new]** e escolha um dos seguintes tipos de origem:

   * **[!UICONTROL Raw unprojected bitmap]**. (Depois de adicionado, esse tipo de fonte é rotulado como RawTerrainSource no [!DNL Terrain Images] janela.)

   * **[!UICONTROL General image, unprojected]**. (Depois de adicionado, esse tipo de origem é rotulado [!DNL GDALTerrainSource] no [!DNL Terrain Images] janela.)

   * **[!UICONTROL Image with embedded projection]**. (Depois de adicionado, esse tipo de origem é rotulado [!DNL GDALTerrainSource] no [!DNL Terrain Images] janela.)

1. Edite os parâmetros da origem conforme necessário usando o arquivo de amostra e a tabela de parâmetros a seguir como guias.

   ![](assets/cfg_TerrainImages_ALL.png)

<table id="table_345ACB4C48524516AADB731D87FC6792"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Gama </p> </td> 
   <td colname="col2"> <p>Opcional para todas as fontes. Especifica a correção gama a ser aplicada à imagem de origem. Isso pode ser desejável porque a Data Workbench normalmente funciona com uma configuração gama alta. O valor padrão é 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Altura </p> </td> 
   <td colname="col2"> <p>Necessário para imagens de bitmap não projetadas. A altura da imagem de origem em pixels. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Informações da projeção </p> </td> 
   <td colname="col2"> <p>Necessário para imagens de bitmap não projetadas e imagens gerais não projetadas, mas compatível com imagens com projeção incorporada. A Data Workbench suporta projeções de latitude e longitude e projeções Transverse Mercator (TM) para camadas de imagem do terreno. O formato de projeção padrão é a projeção de latitude e longitude (LatLonProjection). </p> <p>Para obter informações sobre formatos de projeção, consulte <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Especificar informações de projeção para imagens do terreno</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imagem de origem </p> </td> 
   <td colname="col2"> <p>Necessário para todas as fontes. O nome do arquivo de imagem de origem. Pode ser um nome de arquivo ou um padrão curinga. O uso de um padrão pode ser útil se, por exemplo, imagens para a mesma região em datas diferentes forem carregadas, sem alteração nos metadados associados. Portanto, um padrão como <span class="filepath"> Canto do Tysons *.raw</span> criaria camadas de <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span>e assim por diante, à medida que novas imagens são adicionadas, sem nenhuma configuração adicional necessária se os parâmetros dos arquivos forem idênticos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qualidade de compactação de mosaico </p> </td> 
   <td colname="col2"> <p>Opcional para todas as fontes. Para compactação JPEG, um número inteiro de 0 a 100 que especifica como equilibrar o tamanho e a qualidade da imagem. (O valor padrão é zero.) Um número maior resulta em melhor qualidade de imagem, mas produz imagens maiores e tempos de download mais longos para usuários do Data Workbench. </p> <p> <p>Observação: Compactar imagens abaixo de 70 pode resultar em degradação da imagem. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Compactador de mosaicos </p> </td> 
   <td colname="col2"> <p>Opcional para todas as fontes. Especifica qual método de compactação é usado para gravar arquivos de saída. Os únicos métodos atualmente compatíveis são RAWRGB (o padrão, resultando em nenhuma compactação) e JPEG. Use a compactação JPEG para reduzir o tamanho das camadas que são transmitidas durante a sincronização do perfil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Largura </p> </td> 
   <td colname="col2"> <p>Necessário para imagens de bitmap não projetadas. A largura da imagem de origem em pixels. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Edite a localização da imagem de origem, o armazenamento temporário da imagem e as camadas de gravação em parâmetros usando a tabela a seguir como guia. Esses parâmetros se aplicam a todas as fontes de imagem do terreno definidas na variável [!DNL Sources] deste arquivo.

<table id="table_103F02C54ED94C6C922450F5B2781CAE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Localização da Imagem de Origem </p> </td> 
   <td colname="col2"> <p>Obrigatório. O diretório que é verificado para que imagens sejam traduzidas em camadas de terreno. Se não for um caminho absoluto, ele será interpretado em relação ao diretório de instalação do servidor do Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Armazenamento de imagem temporária </p> </td> 
   <td colname="col2"> <p>Opcional. O nome de um diretório que é usado para armazenamento de arquivos temporários usados na tradução de imagens de origem para camadas de terreno. Se não for um caminho absoluto, ele será interpretado em relação ao diretório de instalação do servidor do Data Workbench. O local padrão é o <span class="wintitle"> Temp</span> diretório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gravar camadas em </p> </td> 
   <td colname="col2"> <p>Obrigatório. O diretório para o qual as camadas de terreno são geradas. Normalmente, esse é o subdiretório Maps de um diretório de perfil, para que a visualização Globe possa encontrar as camadas. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Salve o arquivo clicando com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clicando em **[!UICONTROL Save]**.
1. Para salvar um arquivo atualizado no computador do servidor do Data Workbench, no [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção de [!DNL Terrain Images.cfg] no [!DNL Temp] e, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
