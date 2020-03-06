---
description: Ao criar uma camada de ponto de elemento usando pontos dinâmicos, os dados de latitude e longitude são incorporados em cada elemento da dimensão.
solution: Analytics
title: Definir camadas de pontos de elemento usando pontos dinâmicos
topic: Data workbench
uuid: f4b41969-329a-4c33-a8db-8d85597fa577
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definir camadas de pontos de elemento usando pontos dinâmicos{#define-element-point-layers-using-dynamic-points}

Ao criar uma camada de ponto de elemento usando pontos dinâmicos, os dados de latitude e longitude são incorporados em cada elemento da dimensão.

Para definir uma camada de ponto de elemento usando pontos dinâmicos, você deve criar ou já ter disponível o seguinte:

* Uma dimensão, definida no [!DNL Transformation.cfg] arquivo ou em um [!DNL transformation dataset include] arquivo, na qual cada elemento contém a string &quot;latitude, longitude&quot; ou &quot;latitude, longitude, nome&quot;.

   Para obter etapas para criar uma dimensão, consulte o Guia *de Configuração de* Conjunto de Dados.

* Um arquivo de camada que especifica a dimensão relacionada.

Para obter mais informações sobre o formato necessário do arquivo de camada, consulte Formato [de Arquivo de Camada de Ponto](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#section-0645fbc761c14bb986f3d6f02df407a0)de Elemento.

>[!NOTE]
>
>Ao usar [!DNL Dynamic Points], é essencial garantir que a cardinalidade da dimensão especificada no arquivo de camada seja razoável. Se cada linha de um conjunto de dados tiver uma latitude e longitude diferentes, a dimensão será rapidamente preenchida e a maioria das linhas será incluída em um elemento Elementos pequenos. Como o elemento Elementos Pequenos não tem latitude e longitude, ele não aparece no globo.

## Formato de arquivo de camada do ponto de elemento {#section-0645fbc761c14bb986f3d6f02df407a0}

Cada arquivo de camada de ponto de elemento que usa pontos dinâmicos deve ser formatado usando o seguinte modelo:

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Dynamic Points = bool: true
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_8756BDCC49F447C0855BA64BC0078A0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimensão </td> 
   <td colname="col2"> <p>O nome da dimensão (definido em um arquivo de configuração de transformação), que deve conter elementos com a string "latitude, longitude" ou "latitude, longitude, nome", conforme mostrado nos seguintes exemplos: 
     <ul id="ul_CC12F05459C640F5AB3C295932B04F83"> 
      <li id="li_9023CFA04A0F407E9DF0E1A4D71BB18C">37.5181,-77.1903 </li> 
      <li id="li_F002AB3AB98049A4AF1588B51167C7FA">35.3317-77.8126,Em algum lugar </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Métrica </td> 
   <td colname="col2"> O nome da métrica que é avaliada sobre a dimensão especificada no parâmetro Dimensão. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pontos dinâmicos </td> 
   <td colname="col2"> Ativa Pontos dinâmicos. Definido como verdadeiro. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Escala </td> 
   <td colname="col2"> Opcional. Valor usado para dimensionar os pontos na camada. O valor padrão é 100. Valores maiores tornam os pontos maiores e valores menores os tornam menores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cor do canal </td> 
   <td colname="col2"> Opcional. O vetor de cor RGB, que é expresso como (vermelho, verde, azul). Para cada cor no vetor, você pode inserir um valor de 0,0 a 1,0. Por exemplo, (1.0, 0.0, 0.0) é vermelho vivo e (0.5, 0.5, 0.5, 0.5) é cinza. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modo de renderização </td> 
   <td colname="col2"> <p>Opcional. Valor inteiro que representa o modo de renderização a ser usado para a camada. Os três modos disponíveis são os seguintes: 
     <ul id="ul_C7A74B9B085741C8B7116E4F110DF830"> 
      <li id="li_75CC2BE35C594B6895F743A1967A2E07">Modo de renderização 1. O tamanho dos pontos é definido no espaço da tela (os pontos permanecem em um tamanho constante em relação à tela do computador). Os pontos são renderizados usando polígonos, portanto, não há limite máximo no tamanho do ponto. Esse é o modo de renderização padrão. </li> 
      <li id="li_5B19C5B0F59548E28DCE7F7CD319E210">Modo de renderização 2. O tamanho do ponto é definido no espaço mundial (os pontos permanecem em um tamanho constante em relação ao globo). Os pontos são renderizados usando polígonos, portanto, não há limite máximo no tamanho do ponto. </li> 
      <li id="li_DF0C9AEFE82642C9BD5AEA79770D2896">Modo de renderização 3. O tamanho do ponto é definido no espaço da tela. Os pontos são renderizados usando pontos suaves do OpenGL. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

O [!DNL IP Coordinates.layer] arquivo é formatado da seguinte forma:

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Coordinates
  Metric = ref: wdata/model/metric/Visitors
  Dynamic Points = bool: true
```

