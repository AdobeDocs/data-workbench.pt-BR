---
description: A projeção Universal Transverse Mercator (UTM) é definida por oito parâmetros.
title: Projeções Universais Transversas de Mercator
uuid: 55421412-5c68-4a4f-88d6-650d5999a77c
exl-id: 7d7610c3-14e7-474e-b792-ad413c86a2ef
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---

# Projeções Universais Transversas de Mercator{#universal-transverse-mercator-projections}

A projeção Universal Transverse Mercator (UTM) é definida por oito parâmetros.

Ao especificar uma projeção universal transversa de Mercator para uma camada de imagem do terreno, seus arquivos de imagem do terreno devem ser alinhados com false (projetado) norte, em direção à parte superior da imagem, e false, para leste, à direita da imagem.

Para especificar uma projeção UTM para qualquer fonte de imagem do terreno, você deve abrir o arquivo [!DNL Terrain Images.cfg] em um editor de texto, como o Notepad, definir o parâmetro Informações da projeção como &quot;TransverseMercatorProjection&quot; e adicionar configurações para a projeção UTM.

**Especificar uma projeção universal transversa de Mercator**

1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para visualizar seu conteúdo. O arquivo [!DNL Terrain Images.cfg] está localizado dentro desse diretório.

1. Clique com o botão direito do mouse na marca de seleção na coluna *server name* para [!DNL Terrain Images.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece na coluna [!DNL Temp] para [!DNL Terrain Images.cfg].

1. Clique com o botão direito do mouse na marca de seleção recém-criada na coluna [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O arquivo [!DNL Terrain Images.cfg]aparece em uma janela Bloco de notas.

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

| Parâmetro | Descrição |
|---|---|
| Elipsoide Nivelamento Inverso, Eixo Semimajante Ellipsoide | Os parâmetros do elipsoid usado para a projeção. O eixo semimajor é especificado em metros. |
| False | A falsa conversão do meridiano central da projeção, em metros. Para o UTM, são sempre 500.000. |
| Falsa Nórdica | O falso nada do equador na projeção, em metros. Para UTM, é 0 para zonas do hemisfério norte e 10.000 para zonas do hemisfério sul. |
| Coordenadas do Canto Noroeste, Coordenadas do Canto Sudeste | As coordenadas (em metros projetados) dos cantos superior esquerdo e inferior direito da imagem. |
| Prime Meridian | A longitude do meridiano central da projeção, especificada em graus a leste de Greenwich. Podem ser utilizados números negativos para especificar graus ocidentais. |
| Fator de Escala | A relação entre o raio do cilindro de projeção e o eixo semimajante do elipsoide. Para projeções de Mercator Universal Transverse (UTM), é sempre 0,9996. |
