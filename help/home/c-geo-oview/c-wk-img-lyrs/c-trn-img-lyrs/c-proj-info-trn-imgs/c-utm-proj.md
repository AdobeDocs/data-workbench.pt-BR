---
description: A projeção do Universal Transverse Mercator (UTM) é definida por oito parâmetros.
solution: Analytics
title: Projeções Universais de Mercador Transversal
topic: Data workbench
uuid: 55421412-5c68-4a4f-88d6-650d5999a77c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Projeções Universais de Mercador Transversal{#universal-transverse-mercator-projections}

A projeção do Universal Transverse Mercator (UTM) é definida por oito parâmetros.

Ao especificar uma projeção Universal Transverse Mercator para uma camada de imagem do terreno, seus arquivos de imagem do terreno devem ser alinhados com falso (projetado) norte em direção à parte superior da imagem e falso leste à direita da imagem.

Para especificar uma projeção de UTM para qualquer fonte de imagem de terreno, abra o [!DNL Terrain Images.cfg] arquivo em um editor de texto como o Notepad, defina o parâmetro Informações de projeção como &quot;TransverseMercatorProjection&quot; e adicione configurações para a projeção de UTM.

**Especificação de uma projeção Mercator Universal Transversal**

1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para exibir o conteúdo. O [!DNL Terrain Images.cfg] arquivo está localizado dentro deste diretório.

1. Clique com o botão direito do mouse na marca de seleção na coluna de nome *do* servidor para [!DNL Terrain Images.cfg]e clique em **[!UICONTROL Make Local]**. Uma marca de seleção é exibida na [!DNL Temp] coluna para [!DNL Terrain Images.cfg].

1. Clique com o botão direito do mouse na marca de seleção recém-criada na [!DNL Temp] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O [!DNL Terrain Images.cfg]arquivo é exibido em uma janela do Bloco de notas.

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

| Parâmetro | Descrição |
|---|---|
| Nivelamento Inverso Elipsoide, Eixo Semimajante Elipsoide | Os parâmetros do elipsoide utilizados para a projeção. O eixo semimajar é especificado em metros. |
| Falsa emulação | A falsa leitura do meridiano central da projeção, em metros. Para a UTM, são sempre 500.000. |
| Falso Norte | O falso norte do equador na projeção, em metros. Para a UTM, é 0 para as zonas do hemisfério Norte e 10 mil para as zonas do hemisfério Sul. |
| Coordenadas do Canto Noroeste, Coordenadas do Canto Sudeste | As coordenadas (em metros projetados) dos cantos superior esquerdo e inferior direito da imagem. |
| Prime Meridiano | A longitude do meridiano central da projeção, especificada em graus a leste de Greenwich. Números negativos podem ser usados para especificar graus oeste. |
| Fator de escala | A relação entre o raio do cilindro de projeção e o eixo do semimajador do elipsoide. Para projeções do Universal Transverse Mercator (UTM), é sempre 0,9996. |

