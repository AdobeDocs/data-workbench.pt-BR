---
description: O Data Workbench suporta projeções de latitude e longitude e projeções de Universal Transverse Mercator (UTM) para todas as fontes de camada de imagem do terreno.
title: Especificar informações de projeção para imagens do terreno
uuid: cc1e1e35-6b23-4121-a9f5-489001cb2ef8
exl-id: 2638c5d4-164d-411b-8464-0a3af81b6537
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 3%

---

# Especificar informações de projeção para imagens do terreno{#specify-projection-information-for-terrain-images}

O Data Workbench suporta projeções de latitude e longitude e projeções de Universal Transverse Mercator (UTM) para todas as fontes de camada de imagem do terreno.

As informações de projeção são necessárias para bitmaps brutos não projetados e imagens gerais, não projetadas. Você pode especificar informações de projeção para imagens com informações de projeção incorporadas, embora isso geralmente não seja necessário, pois os parâmetros da projeção são determinados automaticamente a partir de dados geodésicos incorporados na própria imagem. As seções a seguir fornecem detalhes sobre como especificar esses formatos de projeção no arquivo [!DNL Terrain Images.cfg].

## Projeções de latitude e longitude {#section-6e335357ec28462ba39c565e0a5986c7}

O formato de projeção de latitude e longitude (LatLonProjection) no arquivo [!DNL Terrain Images.cfg] é definido por quatro parâmetros para latitude e longitude.

Para especificar um LatLonProjection para imagens não projetadas (bitmaps brutos não projetados e imagens gerais, não projetadas), você pode inserir configurações para LatLonProjection dentro da janela [!DNL Terrain Images.cfg] no Data Workbench.

Para especificar um LatLonProjection para imagens com informações de projeção incorporadas, você deve abrir o arquivo [!DNL Terrain Images.cfg] em um editor de texto como o Notepad, definir o parâmetro Informações de projeção como LatLonProjection e adicionar configurações para [!DNL LatLonProjection].

**Especificação de LatLonProjection para imagens não projetadas**

1. Abra o arquivo [!DNL Terrain Images.cfg] no Data Workbench e adicione uma fonte de camada de imagem do terreno conforme descrito em [Para definir uma camada de imagem do terreno](../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).
1. Edite os parâmetros de Informações de projeção usando a tabela de parâmetros a seguir como guia:

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
   <td colname="col2"> <p>A longitude da borda esquerda da imagem, em graus, onde os números positivos são leste e os números negativos são longitudes ocidentais. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon1 </p> </td> 
   <td colname="col2"> <p>A longitude da borda direita da imagem. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Salve o arquivo clicando com o botão direito do mouse em **[!UICONTROL (modified)]** na parte superior da janela e clicando em **[!UICONTROL Save]**.
1. Para salvar as alterações feitas localmente no computador do servidor do Data Workbench, no [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção [!DNL Terrain Images.cfg] na coluna [!DNL Temp] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

**Especificação de LatLonProjection para imagens em informações de projeção incorporadas**

No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para visualizar seu conteúdo. O arquivo [!DNL Terrain Images.cfg] está localizado dentro desse diretório.

Clique com o botão direito do mouse na marca de seleção na coluna nome do servidor para [!DNL Terrain Images.cfg] e depois clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece na coluna [!DNL Temp] para [!DNL Terrain Images.cfg].

Clique com o botão direito do mouse na marca de seleção recém-criada na coluna [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O arquivo [!DNL Terrain Images.cfg] aparece em uma janela Bloco de notas.

Edite os parâmetros de Informações de projeção usando o seguinte fragmento de arquivo de amostra como guia. Certifique-se de especificar o tipo de projeção, como destacado abaixo. Para obter descrições dos parâmetros, consulte a tabela LatLonProjection Parameters no procedimento anterior.

```
Projection Info = LatLonProjection:
  Lat0 = double: 90
  Lat1 = double: -90
  Lon0 = double: -180
  Lon1 = double: 180
```

## Projeções Universais Transversas de Mercator {#section-606df0ed1c2d4a6bac3ff0fa2cfb3e82}

A projeção Universal Transverse Mercator (UTM) é definida por oito parâmetros. Ao especificar uma projeção universal transversa de Mercator para uma camada de imagem do terreno, seus arquivos de imagem do terreno devem ser alinhados com false (projetado) norte, em direção à parte superior da imagem, e false, para leste, à direita da imagem.

Para especificar uma projeção UTM para qualquer fonte de imagem do terreno, você deve abrir o arquivo [!DNL Terrain Images.cfg] em um editor de texto, como o Notepad, definir o parâmetro Informações da projeção como &quot;TransverseMercatorProjection&quot; e adicionar configurações para a projeção UTM.

**Especificar uma projeção universal transversa de Mercator**

1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para visualizar seu conteúdo. O arquivo [!DNL Terrain Images.cfg] está localizado dentro desse diretório.
1. Clique com o botão direito do mouse na marca de seleção na coluna nome do servidor para [!DNL Terrain Images.cfg] e depois clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece na coluna [!DNL Temp] para [!DNL Terrain Images.cfg.]
1. Clique com o botão direito do mouse na marca de seleção recém-criada na coluna [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O arquivo [!DNL Terrain Images.cfg] aparece em uma janela Bloco de notas.
1. Edite os parâmetros de Informações de projeção usando o fragmento de arquivo de amostra a seguir e a tabela de parâmetros como guias. Certifique-se de especificar o tipo de projeção, como destacado abaixo.

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
   <td colname="col1"> <p>Elipsoide Nivelamento Inverso, Eixo Semimajante Ellipsoide </p> </td> 
   <td colname="col2"> <p>Os parâmetros do elipsoid usado para a projeção. O eixo semimajor é especificado em metros. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False </p> </td> 
   <td colname="col2"> <p>A falsa conversão do meridiano central da projeção, em metros. Para o UTM, são sempre 500.000. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Falsa Nórdica </p> </td> 
   <td colname="col2"> <p>O falso nada do equador na projeção, em metros. Para UTM, é 0 para zonas do hemisfério norte e 10.000 para zonas do hemisfério sul. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Coordenadas do Canto Noroeste, Coordenadas do Canto Sudeste </p> </td> 
   <td colname="col2"> <p>As coordenadas (em metros projetados) dos cantos superior esquerdo e inferior direito da imagem. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prime Meridian </p> </td> 
   <td colname="col2"> <p>A longitude do meridiano central da projeção, especificada em graus a leste de Greenwich. Podem ser utilizados números negativos para especificar graus ocidentais. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fator de Escala </p> </td> 
   <td colname="col2"> <p>A relação entre o raio do cilindro de projeção e o eixo semimajante do elipsoide. Para projeções de Mercator Universal Transverse (UTM), é sempre 0,9996. </p> </td> 
  </tr> 
 </tbody> 
</table>
