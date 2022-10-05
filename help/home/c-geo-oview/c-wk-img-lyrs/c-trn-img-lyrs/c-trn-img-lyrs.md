---
description: No Data Workbench, uma camada de imagem do terreno exibe imagens do terreno da Terra.
title: Trabalhar com camadas de imagem do terreno
uuid: 2f23a2c8-f551-4b84-bd87-5d7053910ab3
exl-id: 22026b41-4e12-4247-b019-461ae223bd07
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 2%

---

# Trabalhar com camadas de imagem do terreno{#working-with-terrain-image-layers}

{{eol}}

No Data Workbench, uma camada de imagem do terreno exibe imagens do terreno da Terra.

As camadas de imagem do terreno são armazenadas no [!DNL Geography] , em um formato personalizado. Essas camadas de imagem podem ser geradas pelo Adobe ou o servidor do Data Workbench pode transformar as imagens do terreno fornecidas pelo usuário em camadas do terreno adequadas para uso na visualização do globo.

>[!NOTE]
>
>Para trabalhar com camadas de imagem do terreno, você deve instalar o [!DNL Terrain Images.cfg] arquivo fornecido pelo Adobe. Para obter instruções de instalação, consulte [Instalar a geografia do Data Workbench](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md).

Para definir uma camada de imagem do terreno, você deve ter o seguinte:

* **Um ou mais arquivos de imagem do terreno** contendo as imagens a serem exibidas em todo o mundo.
* **Um Terrain Images.cfg** arquivo que especifica os arquivos de imagem do terreno a serem usados para a(s) camada(s). O [!DNL Terrain Images.cfg] permite adicionar uma ou mais fontes para criar uma camada de imagem do terreno. O formato do arquivo de imagem do terreno determina o tipo de fonte que deve ser adicionada. A tabela a seguir fornece descrições das fontes de camada de imagem do terreno disponíveis, incluindo os formatos de arquivo de imagem do terreno suportados:

<table id="table_BF8D5933BFBE45039BD164C258D3B450"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Mapa de bits bruto não projetado </td> 
   <td colname="col2"> <p>Cria camadas de imagem do terreno a partir de arquivos de RGB sem cabeçalho de 24 bits que são alinhados por latitude e longitude (não projetado), onde norte é o topo da imagem e leste é o lado direito. </p> <p>Formato(s) de imagem suportado(s): BRUTO </p> <p> <p>Observação: Esta fonte requer informações de projeção. Para obter informações sobre formatos de projeção, consulte <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Especificar informações de projeção para imagens do terreno</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Imagem geral, não projetada </td> 
   <td colname="col2"> <p>Cria camadas de imagem do terreno a partir de formatos de imagem de 24 bits, alinhados com latitude e longitude (não projetado), onde norte é o topo da imagem e leste é o lado direito. </p> <p>Formato(s) de imagem suportado(s): BMP, JPG, PNG, TIFF </p> <p> <p>Observação: Esta fonte requer informações de projeção. Para obter informações sobre formatos de projeção, consulte <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Especificar informações de projeção para imagens do terreno</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Imagem com projeção incorporada </td> 
   <td colname="col2"> <p>Cria camadas de imagem do terreno a partir de formatos de imagem que incorporam dados geodésicos no arquivo de imagem. As informações de projeção são extraídas da imagem. </p> <p>Formato(s) de imagem suportado(s): Erdas (IMG), GeoTIFF </p> <p> <p>Observação: Esta fonte geralmente não requer informações de projeção, mas suporta a adição dessas informações, se necessário. Para obter informações sobre formatos de projeção, consulte <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Especificar informações de projeção para imagens do terreno</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Definição de uma camada de imagem do terreno**

1. No Data Workbench, no [!DNL Admin] > [!DNL Dataset and Profile] clique no botão **[!UICONTROL Servers Manager]** miniatura para abrir a [!DNL Servers Manager] espaço de trabalho.

1. No [!DNL Servers Manager] , clique com o botão direito do mouse no ícone do servidor do Data Workbench desejado e clique em **[!UICONTROL Server Files]**.

1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para visualizar seu conteúdo. O [!DNL Terrain Images.cfg] O arquivo está localizado dentro desse diretório.

1. Clique com o botão direito do mouse na marca de seleção na coluna de nome do servidor para [!DNL Terrain Images.cfg], depois clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece no [!DNL Temp] coluna para [!DNL Terrain Images.cfg.]

1. Clique com o botão direito do mouse na marca de seleção recém-criada na [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. O [!DNL Terrain Images.cfg]será exibida.

1. No [!DNL Terrain Images] , clique em **[!UICONTROL component]** para visualizar seu conteúdo.

1. Clique com o botão direito do mouse **[!UICONTROL Sources]** > **[!UICONTROL Add new]** e escolha um dos seguintes tipos de origem:

   * **[!UICONTROL Raw unprojected bitmap]**. (Depois de adicionado, esse tipo de fonte é rotulado como RawTerrainSource no [!DNL Terrain Images] janela.)

   * **[!UICONTROL General image, unprojected]**. (Depois de adicionado, esse tipo de fonte é rotulado como GDALTerrainSource na variável [!DNL Terrain Images] janela.)

   * **[!UICONTROL Image with embedded projection]**. (Depois de adicionado, esse tipo de fonte é rotulado como GDALTerrainSource na variável [!DNL Terrain Images] janela.)

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
   <td colname="col2"> Opcional para todas as fontes. Especifica a correção gama a ser aplicada à imagem de origem. Isso pode ser desejável porque o Data Workbench normalmente é executado com uma configuração gama alta. O valor padrão é 1. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Altura </td> 
   <td colname="col2"> Necessário para imagens de bitmap não projetadas. A altura da imagem de origem em pixels. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informações da projeção </td> 
   <td colname="col2"> <p>Necessário para imagens de bitmap não projetadas e imagens gerais não projetadas, mas compatível com imagens com projeção incorporada. Análise de big data<span class="wintitle"> Geografia</span> suporta projeções de latitude e longitude e projeções Transverse Mercator (TM) para camadas de imagem do terreno. O formato de projeção padrão é a projeção de latitude e longitude (LatLonProjection). </p> <p>Para obter informações sobre formatos de projeção, consulte <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Especificar informações de projeção para imagens do terreno</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Imagem de origem </td> 
   <td colname="col2">Necessário para todas as fontes. O nome do arquivo de imagem de origem. Pode ser um nome de arquivo ou um padrão curinga. O uso de um padrão pode ser útil se, por exemplo, imagens para a mesma região em datas diferentes forem carregadas, sem alteração nos metadados associados. Portanto, um padrão como "<span class="filepath"> Canto do Tysons *.raw</span>" criaria camadas a partir de <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span>e assim por diante, à medida que novas imagens são adicionadas, sem nenhuma configuração adicional necessária se os parâmetros dos arquivos forem idênticos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Qualidade de compactação de mosaico </td> 
   <td colname="col2"> <p>Opcional para todas as fontes. Para compactação JPEG, um número inteiro de 0 a 100 que especifica como equilibrar o tamanho e a qualidade da imagem. (O valor padrão é zero.) Um número maior resulta em melhor qualidade de imagem, mas produz imagens maiores e tempos de download mais longos para usuários do Data Workbench. </p> <p>Compactar imagens abaixo de 70 pode resultar em degradação da imagem. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compactador de mosaicos </td> 
   <td colname="col2"> Opcional para todas as fontes. Especifica qual método de compactação é usado para gravar arquivos de saída. Os únicos métodos atualmente compatíveis são RAWRGB (o padrão, resultando em nenhuma compactação) e JPEG. Use a compactação JPEG para reduzir o tamanho das camadas que são transmitidas durante a sincronização do perfil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Largura </td> 
   <td colname="col2"> Necessário para imagens de bitmap não projetadas. A largura da imagem de origem em pixels. </td> 
  </tr> 
 </tbody> 
</table>

1. Edite a localização da imagem de origem, o armazenamento temporário da imagem e as camadas de gravação em parâmetros usando a tabela a seguir como guia. Esses parâmetros se aplicam a todas as fontes de imagem do terreno definidas na seção Fontes desse arquivo.

   | Parâmetro | Descrição |
   |---|---|
   | Localização da Imagem de Origem | Obrigatório. O diretório que é verificado para que imagens sejam traduzidas em camadas de terreno. Se não for um caminho absoluto, ele será interpretado em relação ao diretório de instalação do servidor do Data Workbench. |
   | Armazenamento de imagem temporária | Opcional. O nome de um diretório que é usado para armazenamento de arquivos temporários usados na tradução de imagens de origem para camadas de terreno. Se não for um caminho absoluto, ele será interpretado em relação ao diretório de instalação do servidor do Data Workbench. O local padrão é o diretório Temp. |
   | Gravar camadas em | Obrigatório. O diretório para o qual as camadas de terreno são geradas. Normalmente, esse é o subdiretório Maps de um diretório de perfil, de modo que a variável [!DNL Globe] A visualização pode encontrar as camadas. |

1. Salve o arquivo clicando com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clicando em **[!UICONTROL Save]**.

1. Para salvar o arquivo atualizado na máquina do servidor do Data Workbench, na [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção de [!DNL Terrain Images.cfg] no [!DNL Temp] e, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
