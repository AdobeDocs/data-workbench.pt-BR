---
description: Na análise de big data, uma camada de imagem do terreno exibe imagens do terreno da Terra.
solution: Analytics
title: Trabalhar com camadas de imagem de terreno
topic: Data workbench
uuid: 2f23a2c8-f551-4b84-bd87-5d7053910ab3
translation-type: tm+mt
source-git-commit: 948c6dd04819e939b45745db573a53c8be51ce37

---


# Trabalhar com camadas de imagem de terreno{#working-with-terrain-image-layers}

Na análise de big data, uma camada de imagem do terreno exibe imagens do terreno da Terra.

As camadas de imagem de terreno são armazenadas no [!DNL Geography] perfil, em um formato personalizado. Essas camadas de imagem podem ser geradas pela Adobe, ou o servidor de análise de big data pode transformar sua imagem de terreno fornecida pelo usuário em camadas de terreno adequadas para uso na visualização do globo.

>[!NOTE]
>
>Para trabalhar com camadas de imagem do terreno, é necessário instalar o [!DNL Terrain Images.cfg] arquivo fornecido pela Adobe. Para obter instruções de instalação, consulte [Instalação da geografia](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md)da análise de big data.

Para definir uma camada de imagem de terreno, é necessário ter o seguinte:

* **Um ou mais arquivos** de imagem do terreno contendo as imagens a serem exibidas no globo.
* **Um arquivo Terrain Images.cfg** que especifica os arquivos de imagem do terreno a serem usados para as camadas. O [!DNL Terrain Images.cfg] arquivo permite que você adicione uma ou mais fontes para criar uma camada de imagem de terreno. O formato do arquivo de imagem do terreno determina o tipo de origem que você deve adicionar. A tabela a seguir fornece descrições das fontes de camada de imagem de terreno disponíveis, incluindo os formatos de arquivo de imagem de terreno suportados:

<table id="table_BF8D5933BFBE45039BD164C258D3B450"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Bitmap bruto não projetado </td> 
   <td colname="col2"> <p>Cria camadas de imagem do terreno a partir de arquivos RGB sem cabeçalho de 24 bits que são alinhados à latitude (não projetados), onde o norte é o topo da imagem, e o leste é o direito. </p> <p>Formato(s) de imagem suportado(s): RAW </p> <p> <p>Observação: Esta fonte requer informação de projeção. Para obter informações sobre formatos de projeção, consulte <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Especificação de informações de projeção para imagens</a>de terreno. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Imagem geral, não projetada </td> 
   <td colname="col2"> <p>Cria camadas de imagem do terreno a partir de formatos de imagem de 24 bits, alinhados com latitude e longitude (não projetados), onde o norte é o topo da imagem e o leste é o direito. </p> <p>Formato(s) de imagem suportado(s): BMP, JPG, PNG, TIFF </p> <p> <p>Observação: Esta fonte requer informação de projeção. Para obter informações sobre formatos de projeção, consulte <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Especificação de informações de projeção para imagens</a>de terreno. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Imagem com projeção incorporada </td> 
   <td colname="col2"> <p>Cria camadas de imagem do terreno a partir de formatos de imagem que incorporam dados geodésicos no arquivo de imagem. As informações de projeção são extraídas da imagem. </p> <p>Formato(s) de imagem suportado(s): Erdas (IMG), GeoTIFF </p> <p> <p>Observação: Normalmente, esta fonte não exige informações de projeção, mas suporta a adição dessas informações, se necessário. Para obter informações sobre formatos de projeção, consulte <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Especificação de informações de projeção para imagens</a>de terreno. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Definição de uma camada de imagem do terreno**

1. Na análise de big data, na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a [!DNL Servers Manager] área de trabalho.

1. Na [!DNL Servers Manager] janela, clique com o botão direito do mouse no ícone do servidor de análise de big data desejado e clique em **[!UICONTROL Server Files]**.

1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para exibir o conteúdo. O [!DNL Terrain Images.cfg] arquivo está localizado dentro deste diretório.

1. Clique com o botão direito do mouse na marca de seleção na coluna de nome do servidor para [!DNL Terrain Images.cfg]e clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece na [!DNL Temp] coluna para [!DNL Terrain Images.cfg.]

1. Clique com o botão direito do mouse na marca de seleção recém-criada na [!DNL Temp] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. A [!DNL Terrain Images.cfg]janela é exibida.

1. Na [!DNL Terrain Images] janela, clique **[!UICONTROL component]** para exibir seu conteúdo.

1. Clique com o botão direito do mouse em **[!UICONTROL Sources]** > **[!UICONTROL Add new]** e escolha um dos seguintes tipos de origem:

   * **[!UICONTROL Raw unprojected bitmap]**. (Depois de adicionado, esse tipo de origem é identificado como RawTerrainSource na [!DNL Terrain Images] janela.)

   * **[!UICONTROL General image, unprojected]**. (Depois de adicionado, esse tipo de origem é identificado como GDALTerrainSource na [!DNL Terrain Images] janela.)

   * **[!UICONTROL Image with embedded projection]**. (Depois de adicionado, esse tipo de origem é identificado como GDALTerrainSource na [!DNL Terrain Images] janela.)

1. Edite os parâmetros da origem conforme necessário usando o arquivo de amostra e a tabela de parâmetros a seguir como guias.

   ![](assets/cfg_TerrainImages_ALL.png)

<table id="table_83171CB58F8B4816BCCA9BFFD5ECD92A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Gama </td> 
   <td colname="col2"> Opcional para todas as fontes. Especifica a correção gama a ser aplicada à imagem de origem. Isso pode ser desejável porque a análise de big data normalmente funciona com uma configuração gama alta. O valor padrão é 1. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Altura </td> 
   <td colname="col2"> Necessário para imagens de bitmap não projetadas. A altura da imagem de origem em pixels. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informações da projeção </td> 
   <td colname="col2"> <p>Necessário para imagens de bitmap não projetadas e imagens gerais não projetadas, mas compatível com imagens com projeção incorporada. Análise<span class="wintitle"> de big data A geografia</span> suporta projeções de latitude e longitude e projeções de Transverse Mercator (TM) para camadas de imagem do terreno. O formato de projeção padrão é a projeção de latitude e longitude (LatLonProjection). </p> <p>Para obter informações sobre formatos de projeção, consulte <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Especificação de informações de projeção para imagens</a>de terreno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Imagem de origem </td> 
   <td colname="col2">Obrigatório para todas as fontes. O nome do arquivo de imagem de origem. Pode ser um nome de arquivo ou um padrão curinga. O uso de um padrão pode ser útil se, por exemplo, imagens da mesma região em datas diferentes forem carregadas, sem nenhuma alteração nos metadados associados. Portanto, um padrão como "<span class="filepath"> Tysons Corner *.raw</span>" criaria camadas do <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span>e assim por diante, à medida que novas imagens são adicionadas, sem nenhuma configuração adicional necessária se os parâmetros para os arquivos forem idênticos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Qualidade de compactação de blocos </td> 
   <td colname="col2"> <p>Opcional para todas as fontes. Para compactação JPEG, um número inteiro de 0 a 100 que especifica como equilibrar o tamanho e a qualidade da imagem. (O valor padrão é zero.) Um número mais alto resulta em melhor qualidade de imagem, mas produz imagens maiores e tempos de download mais longos para os usuários da análise de big data. </p> <p>A compactação de imagens abaixo de 70 pode resultar na degradação da imagem. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compressor de mosaicos </td> 
   <td colname="col2"> Opcional para todas as fontes. Especifica qual método de compactação é usado para gravar arquivos de saída. Os únicos métodos atualmente suportados são RAWRGB (o padrão, resultando em nenhuma compactação) e JPEG. Use a compactação JPEG para reduzir o tamanho das camadas que são transmitidas durante a sincronização do perfil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Largura </td> 
   <td colname="col2"> Necessário para imagens de bitmap não projetadas. A largura da imagem de origem em pixels. </td> 
  </tr> 
 </tbody> 
</table>

1. Edite os parâmetros Local da imagem de origem, Armazenamento temporário de imagem e Gravar camadas em usando a tabela a seguir como guia. Esses parâmetros se aplicam a todas as fontes de imagem de terreno definidas na seção Fontes desse arquivo.

   | Parâmetro | Descrição |
   |---|---|
   | Local da imagem de origem | Obrigatório. O diretório que é verificado para que as imagens se traduzam em camadas de terreno. Se não for um caminho absoluto, ele será interpretado em relação ao diretório de instalação do servidor da análise de big data. |
   | Armazenamento temporário de imagem | Opcional. O nome de um diretório que é usado para armazenamento de arquivos temporários usados na tradução de imagens de origem para camadas de terreno. Se não for um caminho absoluto, ele será interpretado em relação ao diretório de instalação do servidor da análise de big data. O local padrão é o diretório Temp. |
   | Gravar camadas em | Obrigatório. O diretório no qual as camadas de terreno são geradas. Normalmente, esse é o subdiretório Mapas de um diretório de perfil, para que a [!DNL Globe] visualização possa encontrar as camadas. |

1. Salve o arquivo clicando com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clicando em **[!UICONTROL Save]**.

1. Para salvar o arquivo atualizado na máquina do servidor da análise de big data, no [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção para [!DNL Terrain Images.cfg] na [!DNL Temp] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
