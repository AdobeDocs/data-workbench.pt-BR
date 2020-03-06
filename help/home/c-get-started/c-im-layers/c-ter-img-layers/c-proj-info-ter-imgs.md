---
description: A análise de big data suporta projeções de latitude e de longitude e projeções Universal Transverse Mercator (UTM) para todas as fontes de camada de imagem do terreno.
solution: Analytics
title: Especificar informações de projeção para imagens de terreno
topic: Data workbench
uuid: cc1e1e35-6b23-4121-a9f5-489001cb2ef8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Especificar informações de projeção para imagens de terreno{#specify-projection-information-for-terrain-images}

A análise de big data suporta projeções de latitude e de longitude e projeções Universal Transverse Mercator (UTM) para todas as fontes de camada de imagem do terreno.

As informações de projeção são necessárias para bitmaps brutos não projetados e imagens gerais, não projetadas. Você pode especificar informações de projeção para imagens com informações de projeção incorporadas, embora geralmente não sejam necessárias, pois os parâmetros da projeção são determinados automaticamente a partir de dados geodésicos incorporados à própria imagem. As seções a seguir fornecem detalhes sobre como especificar esses formatos de projeção no [!DNL Terrain Images.cfg] arquivo.

## Projeções de latitude Latitude {#section-6e335357ec28462ba39c565e0a5986c7}

O formato de projeção de latitude e longitude (LatLonProjection) no [!DNL Terrain Images.cfg] arquivo é definido por quatro parâmetros para latitude e longitude.

Para especificar uma LatLonProjection para imagens não projetadas (bitmaps brutos não projetados e imagens gerais, não projetadas), você pode inserir configurações para LatLonProjection dentro da janela na Análise de big data. [!DNL Terrain Images.cfg]

Para especificar um LatLonProjection para imagens com informações de projeção incorporadas, você deve abrir o [!DNL Terrain Images.cfg] arquivo em um editor de texto como o Notepad, definir o parâmetro Informações de projeção como LatLonProjection e adicionar configurações para o [!DNL LatLonProjection].

**Especificação de uma LatLonProjection para imagens não projetadas**

1. Abra o [!DNL Terrain Images.cfg] arquivo no Análise de big data e adicione uma fonte de camada de imagem de terreno conforme descrito em [Para definir uma camada](../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f)de imagem de terreno.
1. Edite os parâmetros de Informações de projeção usando a seguinte tabela de parâmetros como guia:

<table id="table_32F6EADB2DA34592ABD6FFAC9E00BB27"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Lat0 </p> </td> 
   <td colname="col2"> <p>A latitude da borda superior da imagem, em graus, onde 90 é o Polo Norte e -90 é o Polo Sul. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lat1 </p> </td> 
   <td colname="col2"> <p>A latitude da borda inferior da imagem. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon0 </p> </td> 
   <td colname="col2"> <p>A longitude da borda esquerda da imagem, em graus, onde os números positivos são orientais e os números negativos são longitudes ocidentais. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon1 </p> </td> 
   <td colname="col2"> <p>A longitude da borda direita da imagem. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Salve o arquivo clicando com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clicando em **[!UICONTROL Save]**.
1. Para salvar as alterações feitas localmente no computador servidor do Análise de big data, no [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção para [!DNL Terrain Images.cfg] na [!DNL Temp] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

**Especificação de uma LatLonProjection para imagens em informações de projeção incorporadas**

No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para exibir o conteúdo. O [!DNL Terrain Images.cfg] arquivo está localizado dentro deste diretório.

Clique com o botão direito do mouse na marca de seleção na coluna de nome do servidor para [!DNL Terrain Images.cfg]e clique em **[!UICONTROL Make Local]**. Uma marca de seleção é exibida na [!DNL Temp] coluna para [!DNL Terrain Images.cfg].

Clique com o botão direito do mouse na marca de seleção recém-criada na [!DNL Temp] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O [!DNL Terrain Images.cfg] arquivo é exibido em uma janela do Bloco de notas.

Edite os parâmetros de Informações de projeção usando o seguinte fragmento de arquivo de amostra como guia. Certifique-se de especificar o tipo de projeção, conforme realçado abaixo. Para obter descrições dos parâmetros, consulte a tabela LatLonProjection Parameters no procedimento anterior.

```
Projection Info = LatLonProjection:
  Lat0 = double: 90
  Lat1 = double: -90
  Lon0 = double: -180
  Lon1 = double: 180
```

## Projeções Universais de Mercador Transversal {#section-606df0ed1c2d4a6bac3ff0fa2cfb3e82}

A projeção do Universal Transverse Mercator (UTM) é definida por oito parâmetros. Ao especificar uma projeção Universal Transverse Mercator para uma camada de imagem do terreno, seus arquivos de imagem do terreno devem ser alinhados com falso (projetado) norte em direção à parte superior da imagem e falso leste à direita da imagem.

Para especificar uma projeção de UTM para qualquer fonte de imagem de terreno, abra o [!DNL Terrain Images.cfg] arquivo em um editor de texto como o Notepad, defina o parâmetro Informações de projeção como &quot;TransverseMercatorProjection&quot; e adicione configurações para a projeção de UTM.

**Especificação de uma projeção Mercator Universal Transversal**

1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para exibir o conteúdo. O [!DNL Terrain Images.cfg] arquivo está localizado dentro deste diretório.
1. Clique com o botão direito do mouse na marca de seleção na coluna de nome do servidor para [!DNL Terrain Images.cfg]e clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece na [!DNL Temp] coluna para [!DNL Terrain Images.cfg.]
1. Clique com o botão direito do mouse na marca de seleção recém-criada na [!DNL Temp] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O [!DNL Terrain Images.cfg] arquivo é exibido em uma janela do Bloco de notas.
1. Edite os parâmetros de Informações de projeção usando a seguinte tabela de parâmetros e fragmentos de arquivo de amostra como guias. Certifique-se de especificar o tipo de projeção, conforme realçado abaixo.

   ```
   Projection Info = TransverseMercatorProjection:
     Ellipsoid Inverse Flattening = double: 294.9786982139006
     Ellipsoid Semimajor Axis = double: 6378206.4000000004
     False Easting = double: 500000
     False Northing = double: 0
     Northwest Corner Coordinates = v3d: (550339, 5.42059e+006, 0)
     Prime Meridian = double: -123
     Scale Factor = double: 0.9996
     Southeast Corner Coordinates = v3d: (555099, 5.41356e+006, 0)
   ```

<table id="table_71AEEAE808B9436B9846987A54D5D1D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nivelamento Inverso Elipsoide, Eixo Semimajante Elipsoide </p> </td> 
   <td colname="col2"> <p>Os parâmetros do elipsoide utilizados para a projeção. O eixo semimajar é especificado em metros. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Falsa emulação </p> </td> 
   <td colname="col2"> <p>A falsa leitura do meridiano central da projeção, em metros. Para a UTM, são sempre 500.000. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Falso Norte </p> </td> 
   <td colname="col2"> <p>O falso norte do equador na projeção, em metros. Para a UTM, é 0 para as zonas do hemisfério Norte e 10 mil para as zonas do hemisfério Sul. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Coordenadas do Canto Noroeste, Coordenadas do Canto Sudeste </p> </td> 
   <td colname="col2"> <p>As coordenadas (em metros projetados) dos cantos superior esquerdo e inferior direito da imagem. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prime Meridiano </p> </td> 
   <td colname="col2"> <p>A longitude do meridiano central da projeção, especificada em graus a leste de Greenwich. Números negativos podem ser usados para especificar graus oeste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fator de escala </p> </td> 
   <td colname="col2"> <p>A relação entre o raio do cilindro de projeção e o eixo do semimajador do elipsoide. Para projeções do Universal Transverse Mercator (UTM), é sempre 0,9996. </p> </td> 
  </tr> 
 </tbody> 
</table>

