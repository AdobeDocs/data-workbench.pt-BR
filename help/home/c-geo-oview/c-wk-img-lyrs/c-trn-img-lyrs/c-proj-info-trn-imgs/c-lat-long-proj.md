---
description: O formato de projeção de latitude e longitude (LatLonProjection) no arquivo Terrain Images.cfg é definido por quatro parâmetros para latitude e longitude.
title: Projeções de latitude e longitude
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
exl-id: 67ebc7a8-3046-4524-b3a0-0b6da2f235fc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 2%

---

# Projeções de latitude e longitude{#latitude-longitude-projections}

O formato de projeção de latitude e longitude (LatLonProjection) no arquivo Terrain Images.cfg é definido por quatro parâmetros para latitude e longitude.

Para especificar uma LatLonProjection para imagens não projetadas (bitmaps brutos não projetados e imagens gerais, não projetadas), você pode inserir configurações para LatLonProjection dentro da janela [!DNL Terrain Images.cfg] no Data Workbench. Consulte [Para especificar uma LatLonProjection para imagens não projetadas](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a).

Para especificar um LatLonProjection para imagens com informações de projeção incorporadas, você deve abrir o arquivo [!DNL Terrain Images.cfg] em um editor de texto como o Notepad, definir o parâmetro Projection Info como &quot;LatLonProjection&quot; e adicionar configurações para LatLonProjection. Consulte [Para especificar uma LatLonProjection para imagens dentro de informações de projeção incorporadas...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [Especificação de LatLonProjection para imagens não projetadas](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [Para especificar uma LatLonProjection para imagens dentro das informações de projeção incorporadas..](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## Especificação de LatLonProjection para imagens não projetadas {#section-26554eefe645481faba68396fa13756a}

1. Abra o arquivo [!DNL Terrain Images.cfg] no Data Workbench e adicione uma fonte de camada de imagem do terreno conforme descrito em [Para definir uma camada de imagem do terreno](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

1. Edite os parâmetros de Informações de projeção usando a tabela de parâmetros a seguir como guia:

   | Parâmetro | Descrição |
   |---|---|
   | Lat0 | A latitude da borda superior da imagem, em graus, onde 90 é o Polo Norte e -90 é o Polo Sul. |
   | Lat1 | A latitude da borda inferior da imagem. |
   | Lon0 | A longitude da borda esquerda da imagem, em graus, onde os números positivos são leste e os números negativos são longitudes ocidentais. |
   | Lon1 | A longitude da borda direita da imagem. |

1. Salve o arquivo clicando com o botão direito do mouse em **[!UICONTROL (modified)]** na parte superior da janela e clicando em **[!UICONTROL Save]**.

1. Para salvar as alterações feitas localmente na máquina do servidor do Data Workbench, no [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção [!DNL Terrain Images.cfg] na coluna [!DNL Temp] e depois clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

## Especificação de LatLonProjection para imagens dentro de informações de projeção incorporadas {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para visualizar seu conteúdo. O arquivo [!DNL Terrain Images.cfg] está localizado dentro desse diretório.

1. Clique com o botão direito do mouse na marca de seleção na coluna nome do servidor para [!DNL Terrain Images.cfg] e depois clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece na coluna [!DNL Temp] para [!DNL Terrain Images.cfg].

1. Clique com o botão direito do mouse na marca de seleção recém-criada na coluna [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O arquivo [!DNL Terrain Images.cfg] aparece em uma janela Bloco de notas.

1. Edite os parâmetros de Informações de projeção usando o seguinte fragmento de arquivo de amostra como guia. Certifique-se de especificar o tipo de projeção, como destacado abaixo. Para obter descrições dos parâmetros, consulte a tabela LatLonProjection Parameters no procedimento anterior.

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```
