---
description: Formatação de informações sobre o arquivo de camada do ponto de elemento.
title: Formato de arquivo de camada de ponto de elemento
uuid: a8b3d2f4-0ed2-480d-a2a6-75d43025a579
exl-id: 125796f6-a447-4f12-bcf2-3e669783cf1e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 5%

---

# Formato de arquivo de camada de ponto de elemento{#element-point-layer-file-format}

Formatação de informações sobre o arquivo de camada do ponto de elemento.

Cada arquivo de camada [!DNL .layer] de ponto de elemento que faz referência a um arquivo de pesquisa deve ser formatado usando o seguinte modelo:

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Lookup File Name.txt
  Longitude Column = string: Longitude Column Name
  Latitude Column = string: Latitude Column Name
  Name Column = string: Location Column Name
  Key Column = string: Key Column Name
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_B2BC5FE8C80E4680B9A565878192D75B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Caminhos de dados </td> 
   <td colname="col2"> Caminho para o arquivo de pesquisa contendo dados de latitude e longitude. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Coluna de longitude </td> 
   <td colname="col2"> O nome da coluna no arquivo de pesquisa que contém os dados de longitude. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Coluna Latitude </td> 
   <td colname="col2"> O nome da coluna no arquivo de pesquisa que contém os dados de latitude. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Coluna Nome </td> 
   <td colname="col2"> Opcional. O nome da coluna no arquivo de pesquisa que contém os nomes dos locais representados pelos dados de latitude e longitude. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Coluna-chave </td> 
   <td colname="col2"> <p>O nome da coluna no arquivo de pesquisa que contém os dados de chave comuns, que permite que o servidor do Data Workbench integre os dados no arquivo de pesquisa ao conjunto de dados. Esta deve ser a primeira coluna no arquivo de pesquisa. </p> <p>Cada linha nesta coluna é um elemento de uma dimensão. Essa dimensão deve ser definida no arquivo <span class="filepath"> Transformation.cfg</span> ou em um arquivo de inclusão do conjunto de dados de transformação e especificado no parâmetro Dimension desse arquivo. Para obter mais informações sobre arquivos de configuração de transformação, consulte o <i>Guia de Configuração do Conjunto de Dados</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensão </td> 
   <td colname="col2">O nome da dimensão (definido em um arquivo de configuração de transformação) que contém elementos que correspondem às linhas de dados na coluna <span class="wintitle"> Chave</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Métrica </td> 
   <td colname="col2"> O nome da métrica que é avaliada pela dimensão especificada no parâmetro Dimension. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Escala </td> 
   <td colname="col2"> Opcional. Valor usado para dimensionar os pontos na camada. O valor padrão é 100. Valores maiores tornam os pontos maiores e valores menores os tornam menores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cor do canal </td> 
   <td colname="col2"> Opcional. O vetor de cores RGB, que é expresso como (vermelho, verde, azul). Para cada cor no vetor, você pode inserir um valor de 0,0 a 1,0. Por exemplo, (1,0, 0,0, 0,0) é vermelho vivo e (0,5, 0,5, 0,5) é cinza. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modo de renderização </td> 
   <td colname="col2"> <p>Opcional. Valor inteiro que representa o modo de renderização a ser usado para a camada. Os três modos disponíveis são os seguintes: 
     <ul id="ul_CBB26B32505846A39FEB85E831E1C7AB"> 
      <li id="li_B31528A8858C4418ABCDFF0B4EFB25D7">Modo de renderização 1. O tamanho dos pontos é definido no espaço da tela (os pontos permanecem com um tamanho constante em relação à tela do computador). Os pontos são renderizados usando polígonos, de modo que não há limite máximo no tamanho do ponto. Este é o modo de renderização padrão. </li> 
      <li id="li_CA0C3E0DBF004ADBB4D7819C0BF192FC">Modo de renderização 2. O tamanho do ponto é definido no espaço mundial (os pontos permanecem em um tamanho constante em relação ao globo). Os pontos são renderizados usando polígonos, de modo que não há limite máximo no tamanho do ponto. </li> 
      <li id="li_8F8729976DDB434D869E81D4381E2688">Modo de renderização 3. O tamanho do ponto é definido no espaço da tela. Os pontos são renderizados usando pontos suaves do OpenGL. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

O arquivo [!DNL Zip Points.layer] é formatado da seguinte maneira:

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Zip Points.txt
  Longitude Column = string: LONGITUDE
  Latitude Column = string: LATITUDE
  Name Column = string: NAME
  Key Column = string: ZIP_CODE
  Dimension = ref: wdata/model/dim/Zipcode
  Metric = ref: wdata/model/metric/Sessions
```
