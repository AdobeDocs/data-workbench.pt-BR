---
description: Uma camada de imagem do terreno exibe imagens do terreno da Terra.
solution: Analytics
title: Camadas de imagem do terreno
topic: Data workbench
uuid: 17968293-1ad2-4040-a174-d33f418af9b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Camadas de imagem do terreno{#terrain-image-layers}

Uma camada de imagem do terreno exibe imagens do terreno da Terra.

[!DNL Terrain image layers] são armazenados no [!DNL Geography] perfil em um formato personalizado. Essas camadas de imagem podem ser geradas pela Adobe, ou o servidor da Análise de big data pode transformar sua imagem de terreno fornecida pelo usuário em camadas de terreno adequadas para uso na visualização do globo.

>[!NOTE]
>
>Para trabalhar com [!DNL terrain image layers], você deve instalar o [!DNL Terrain Images.cfg] arquivo fornecido pela Adobe.

Para definir uma camada de imagem de terreno, é necessário ter o seguinte:

* **Um ou mais arquivos** de imagem do terreno contendo as imagens a serem exibidas no globo.
* **Um[!DNL Terrain Images.cfg]arquivo** que especifica os arquivos de imagem do terreno a serem usados para as camadas. O [!DNL Terrain Images.cfg] arquivo permite que você adicione uma ou mais fontes para criar um [!DNL terrain image layer]. O formato do arquivo de imagem do terreno determina o tipo de origem que você deve adicionar. A tabela a seguir fornece descrições das fontes de camada de imagem de terreno disponíveis, incluindo os formatos de arquivo de imagem de terreno suportados:

<table id="table_CFDF5E61FCCD40B29A9D35FFA42F68D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Bitmap bruto não projetado </p> </td> 
   <td colname="col2"> <p>Cria camadas <span class="wintitle"> de imagem de</span> terreno a partir de arquivos RGB sem cabeçalho de 24 bits que são alinhados à latitude e longitude (não projetados), onde norte é o topo da imagem e leste é o lado direito. </p> <p>Formato(s) de imagem suportado(s): RAW </p> <p> <p>Observação: Esta fonte requer informação de projeção. Para obter informações sobre formatos de projeção, consulte <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Especificação de informações de projeção para imagens</a>de terreno. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imagem geral, não projetada </p> </td> 
   <td colname="col2"> <p>Cria camadas <span class="wintitle"> de imagem de</span> terreno a partir de formatos de imagem de 24 bits, alinhados à latitude (não projetados), onde o norte é o topo da imagem e o leste é o direito. </p> <p>Formato(s) de imagem suportado(s): BMP, JPG, PNG, TIFF </p> <p> <p>Observação: Esta fonte requer informação de projeção. Para obter informações sobre formatos de projeção, consulte <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Especificação de informações de projeção para imagens</a>de terreno. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imagem com projeção incorporada </p> </td> 
   <td colname="col2"> <p>Cria camadas <span class="wintitle"> de imagem do</span> terreno a partir de formatos de imagem que incorporam dados geodésicos no arquivo de imagem. As informações de projeção são extraídas da imagem. </p> <p>Formato(s) de imagem suportado(s): Erdas (IMG), GeoTIFF </p> <p> <p>Observação: Normalmente, esta fonte não exige informações de projeção, mas suporta a adição dessas informações, se necessário. Para obter informações sobre formatos de projeção, consulte <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Especificação de informações de projeção para imagens</a>de terreno. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Definição de uma camada de imagem do terreno**

1. Na Análise de big data, na guia **[!UICONTROL Admin]** > **[!UICONTROL Dataset and Profile]** , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a [!DNL Servers Manager] área de trabalho.
1. Na [!DNL Servers Manager] janela, clique com o botão direito do mouse no ícone do servidor do Análise de big data desejado e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para exibir o conteúdo. O [!DNL Terrain Images.cfg] arquivo está localizado dentro deste diretório.
1. Clique com o botão direito do mouse na marca de seleção na coluna de nome do servidor para [!DNL Terrain Images.cfg]e clique em **[!UICONTROL Make Local]**. Uma marca de seleção é exibida na [!DNL Temp] coluna para [!DNL Terrain Images.cfg].
1. Clique com o botão direito do mouse na marca de seleção recém-criada na **[!UICONTROL Temp]** coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. A [!DNL Terrain Images.cfg] janela é exibida.
1. Na [!DNL Terrain Images] janela, clique **[!UICONTROL component]** para exibir seu conteúdo.
1. Clique com o botão direito do mouse em **[!UICONTROL Sources]** > **[!UICONTROL Add new]** e escolha um dos seguintes tipos de origem:

   * **[!UICONTROL Raw unprojected bitmap]**. (Depois de adicionado, esse tipo de origem é identificado como RawTerrainSource na [!DNL Terrain Images] janela.)

   * **[!UICONTROL General image, unprojected]**. (Depois de adicionado, esse tipo de origem é rotulado [!DNL GDALTerrainSource] na [!DNL Terrain Images] janela.)

   * **[!UICONTROL Image with embedded projection]**. (Depois de adicionado, esse tipo de origem é rotulado [!DNL GDALTerrainSource] na [!DNL Terrain Images] janela.)

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
   <td colname="col2"> <p>Opcional para todas as fontes. Especifica a correção gama a ser aplicada à imagem de origem. Isso pode ser desejável devido ao fato de a Análise de big data normalmente ser executada com uma configuração gama alta. O valor padrão é 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Altura </p> </td> 
   <td colname="col2"> <p>Necessário para imagens de bitmap não projetadas. A altura da imagem de origem em pixels. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Informações da projeção </p> </td> 
   <td colname="col2"> <p>Necessário para imagens de bitmap não projetadas e imagens gerais não projetadas, mas compatível com imagens com projeção incorporada. A análise de big data suporta projeções de latitude e de longitude e projeções de Mercador Transversal (TM) para camadas de imagem do terreno. O formato de projeção padrão é a projeção de latitude e longitude (LatLonProjection). </p> <p>Para obter informações sobre formatos de projeção, consulte <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Especificação de informações de projeção para imagens</a>de terreno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imagem de origem </p> </td> 
   <td colname="col2"> <p>Obrigatório para todas as fontes. O nome do arquivo de imagem de origem. Pode ser um nome de arquivo ou um padrão curinga. O uso de um padrão pode ser útil se, por exemplo, imagens da mesma região em datas diferentes forem carregadas, sem nenhuma alteração nos metadados associados. Portanto, um padrão como <span class="filepath"> Tysons Corner *.raw</span> criaria camadas do <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span>e assim por diante, à medida que novas imagens são adicionadas, sem nenhuma configuração adicional necessária se os parâmetros para os arquivos forem idênticos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qualidade de compactação de blocos </p> </td> 
   <td colname="col2"> <p>Opcional para todas as fontes. Para compactação JPEG, um número inteiro de 0 a 100 que especifica como equilibrar o tamanho e a qualidade da imagem. (O valor padrão é zero.) Um número mais alto resulta em melhor qualidade de imagem, mas produz imagens maiores e tempos de download mais longos para os usuários do Análise de big data. </p> <p> <p>Observação:  A compactação de imagens abaixo de 70 pode resultar na degradação da imagem. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Compressor de mosaicos </p> </td> 
   <td colname="col2"> <p>Opcional para todas as fontes. Especifica qual método de compactação é usado para gravar arquivos de saída. Os únicos métodos atualmente suportados são RAWRGB (o padrão, resultando em nenhuma compactação) e JPEG. Use a compactação JPEG para reduzir o tamanho das camadas que são transmitidas durante a sincronização do perfil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Largura </p> </td> 
   <td colname="col2"> <p>Necessário para imagens de bitmap não projetadas. A largura da imagem de origem em pixels. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Edite os parâmetros Local da imagem de origem, Armazenamento temporário de imagem e Gravar camadas em usando a tabela a seguir como guia. Esses parâmetros se aplicam a todas as fontes de imagem do terreno definidas na [!DNL Sources] seção desse arquivo.

<table id="table_103F02C54ED94C6C922450F5B2781CAE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Local da imagem de origem </p> </td> 
   <td colname="col2"> <p>Obrigatório. O diretório que é verificado para que as imagens se traduzam em camadas de terreno. Se não for um caminho absoluto, ele será interpretado em relação ao diretório de instalação do servidor da Análise de big data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Armazenamento temporário de imagem </p> </td> 
   <td colname="col2"> <p>Opcional. O nome de um diretório que é usado para armazenamento de arquivos temporários usados na tradução de imagens de origem para camadas de terreno. Se não for um caminho absoluto, ele será interpretado em relação ao diretório de instalação do servidor da Análise de big data. O local padrão é o diretório <span class="wintitle"> Temp</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gravar camadas em </p> </td> 
   <td colname="col2"> <p>Obrigatório. O diretório no qual as camadas de terreno são geradas. Normalmente, esse é o subdiretório Mapas de um diretório de perfil, para que a visualização em Globo possa encontrar as camadas. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Salve o arquivo clicando com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clicando em **[!UICONTROL Save]**.
1. Para salvar um arquivo atualizado no computador servidor do Análise de big data, no [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção [!DNL Terrain Images.cfg] da [!DNL Temp] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

