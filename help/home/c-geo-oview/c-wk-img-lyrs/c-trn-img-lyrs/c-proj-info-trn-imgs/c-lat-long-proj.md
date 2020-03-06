---
description: O formato de projeção de latitude e longitude (LatLonProjection) no arquivo Terrain Images.cfg é definido por quatro parâmetros para latitude e longitude.
solution: Analytics
title: Projeções de latitude Latitude
topic: Data workbench
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Projeções de latitude Latitude{#latitude-longitude-projections}

O formato de projeção de latitude e longitude (LatLonProjection) no arquivo Terrain Images.cfg é definido por quatro parâmetros para latitude e longitude.

Para especificar uma LatLonProjection para imagens não projetadas (bitmaps brutos não projetados e imagens gerais, não projetadas), você pode inserir configurações para LatLonProjection dentro da janela na análise de big data. [!DNL Terrain Images.cfg] Consulte [Especificar uma LatLonProjection para imagens](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)não projetadas.

Para especificar um LatLonProjection para imagens com informações de projeção incorporadas, você deve abrir o [!DNL Terrain Images.cfg] arquivo em um editor de texto como o Notepad, definir o parâmetro Projection Info como &quot;LatLonProjection&quot; e adicionar configurações para o LatLonProjection. Consulte [Especificar uma LatLonProjection para imagens dentro das informações de projeção incorporadas...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [Para especificar uma LatLonProjection para imagens não projetadas](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [Para especificar uma LatLonProjection para imagens em informações de projeção incorporadas...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## Para especificar uma LatLonProjection para imagens não projetadas {#section-26554eefe645481faba68396fa13756a}

1. Abra o [!DNL Terrain Images.cfg] arquivo na análise de big data e adicione uma fonte de camada de imagem de terreno conforme descrito em [Para definir uma camada](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf)de imagem de terreno.

1. Edite os parâmetros de Informações de projeção usando a seguinte tabela de parâmetros como guia:

   | Parâmetro | Descrição |
   |---|---|
   | Lat0 | A latitude da borda superior da imagem, em graus, onde 90 é o Polo Norte e -90 é o Polo Sul. |
   | Lat1 | A latitude da borda inferior da imagem. |
   | Lon0 | A longitude da borda esquerda da imagem, em graus, onde os números positivos são orientais e os números negativos são longitudes ocidentais. |
   | Lon1 | A longitude da borda direita da imagem. |

1. Salve o arquivo clicando com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clicando em **[!UICONTROL Save]**.

1. Para salvar as alterações feitas localmente na máquina do servidor da análise de big data, no [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção para [!DNL Terrain Images.cfg] na [!DNL Temp] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Especificação de uma LatLonProjection para imagens em informações de projeção incorporadas {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para exibir o conteúdo. O [!DNL Terrain Images.cfg] arquivo está localizado dentro deste diretório.

1. Clique com o botão direito do mouse na marca de seleção na coluna de nome do servidor para [!DNL Terrain Images.cfg]e clique em **[!UICONTROL Make Local]**. Uma marca de seleção é exibida na [!DNL Temp] coluna para [!DNL Terrain Images.cfg].

1. Clique com o botão direito do mouse na marca de seleção recém-criada na [!DNL Temp] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O [!DNL Terrain Images.cfg] arquivo é exibido em uma janela do Bloco de notas.

1. Edite os parâmetros de Informações de projeção usando o seguinte fragmento de arquivo de amostra como guia. Certifique-se de especificar o tipo de projeção, conforme realçado abaixo. Para obter descrições dos parâmetros, consulte a tabela LatLonProjection Parameters no procedimento anterior.

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```

