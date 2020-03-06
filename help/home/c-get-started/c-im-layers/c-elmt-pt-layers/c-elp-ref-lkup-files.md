---
description: Ao criar uma camada de ponto de elemento que faz referência a um arquivo de pesquisa para obter dados de latitude e longitude, o local do ponto é obtido recuperando cada elemento e sua latitude e longitude associadas do arquivo de pesquisa.
solution: Analytics
title: Definir camadas de ponto de elemento que fazem referência a arquivos de pesquisa
topic: Data workbench
uuid: 32c8de7a-4316-4f91-9810-7f584bc7fb0b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definir camadas de ponto de elemento que fazem referência a arquivos de pesquisa{#define-element-point-layers-referencing-lookup-files}

Ao criar uma camada de ponto de elemento que faz referência a um arquivo de pesquisa para obter dados de latitude e longitude, o local do ponto é obtido recuperando cada elemento e sua latitude e longitude associadas do arquivo de pesquisa.

>[!NOTE]
>
>Em vez de usar um arquivo de pesquisa, você pode usar a funcionalidade Pontos dinâmicos, que incorpora a latitude e a longitude de um local no nome de cada elemento de uma dimensão. Consulte [Definindo Camadas de Ponto de Elemento Usando Pontos](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#concept-51adc5e1df8a48e7bd7a582967e4c512)Dinâmicos.

Para definir uma camada de ponto de elemento que referencie um arquivo de pesquisa, você deve criar ou já ter disponível o seguinte:

* **Uma dimensão** definida no arquivo [!DNL Transformation.cfg file] ou em um [!DNL transformation dataset include] arquivo. Para obter informações sobre arquivos de configuração de transformação, consulte o Guia *de Configuração de* Conjunto de Dados.

* **Um arquivo** de pesquisa contendo os dados usados para plotar cada ponto de dados. Esse arquivo deve conter pelo menos três colunas de dados para cada ponto de dados: a chave, a longitude e a latitude. Para obter mais informações sobre o formato necessário do arquivo de pesquisa, consulte Formato [de Arquivo de Camada de Ponto](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2)de Elemento.

* **Um arquivo** de camada que especifica o local do arquivo de pesquisa e identifica a dimensão e métrica relacionadas, bem como os nomes das colunas chave, longitude e latitude no arquivo de pesquisa. Para obter mais informações sobre o formato necessário do arquivo de camada, consulte Formato [de Arquivo de Camada de Ponto](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2)de Elemento.

   >[!NOTE]
   >
   >O [!DNL Zip Points.layer] arquivo, fornecido com o [!DNL Geography] perfil, é uma camada de ponto de elemento que identifica o [!DNL Zipcode.dim] arquivo, o [!DNL Sessions.metric] arquivo, o arquivo de [!DNL Zip Points.txt] pesquisa e os nomes das colunas chave, longitude, latitude e nome no arquivo de pesquisa.

## Formato de arquivo de pesquisa do ponto de elemento {#section-0bc8c652c1bd40eb84078f2af71a5c06}

O arquivo de pesquisa de camada de ponto de elemento deve conter pelo menos as três colunas a seguir:

* **[!DNL Key]coluna:**Essa coluna deve conter dados de chave comuns, o que permite que o servidor do Análise de big data conecte os dados no arquivo de pesquisa aos dados no conjunto de dados. A[!DNL key]coluna deve ser a primeira coluna no arquivo de pesquisa. Cada linha nesta coluna identifica um elemento da dimensão.

* **[!DNL Longitude]coluna:**Essa coluna deve conter a longitude de cada ponto de dados na[!DNL Key]coluna.

* **[!DNL Latitude]coluna:**Essa coluna deve conter a latitude para cada ponto de dados na[!DNL Key]coluna.

* **[!DNL Name]coluna (opcional):**Se você quiser especificar um nome a ser exibido no mapa para cada ponto de dados, é possível incluir uma[!DNL Name]coluna no arquivo de pesquisa.

Cada linha no arquivo de [!DNL Zip Points.txt] pesquisa contém um CEP na primeira coluna, seguido da longitude, latitude e nome da cidade associado.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

## Formato de arquivo de camada do ponto de elemento {#section-52d7e92be8354d979af9e7a2210b76f2}

Cada arquivo de camada de ponto de elemento [!DNL .layer] que faz referência a um arquivo de pesquisa deve ser formatado usando o seguinte modelo:

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

<table id="table_7287F8869DD04886BE1477CBB11EB796"> 
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
   <td colname="col1"> Coluna Longitude </td> 
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
   <td colname="col1"> Coluna Chave </td> 
   <td colname="col2"> <p>O nome da coluna no arquivo de pesquisa que contém os dados de chave comuns, que permite que o servidor do Análise de big data integre os dados no arquivo de pesquisa ao conjunto de dados. Essa deve ser a primeira coluna no arquivo de pesquisa. </p> <p>Cada linha nesta coluna é um elemento de uma dimensão. Essa dimensão deve ser definida no arquivo <span class="filepath"> Transformation.cfg</span> ou um conjunto de dados de <span class="wintitle"> transformação incluir</span> o arquivo e especificada no parâmetro Dimension desse arquivo. Para obter mais informações sobre arquivos de configuração de transformação, consulte o Guia <i>de Configuração de</i>Conjunto de Dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensão </td> 
   <td colname="col2">O nome da dimensão (definido em um arquivo de configuração de transformação) que contém elementos que correspondem às linhas de dados na coluna <span class="wintitle"> Chave</span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Métrica </td> 
   <td colname="col2"> O nome da métrica que é avaliada sobre a dimensão especificada no parâmetro Dimensão. </td> 
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
     <ul id="ul_F15E43B3BFE54CDD8026837027E25819"> 
      <li id="li_5405D939540E4D0FA7828D2623D72C44">Modo de renderização 1. O tamanho dos pontos é definido no espaço da tela (os pontos permanecem em um tamanho constante em relação à tela do computador). Os pontos são renderizados usando polígonos, portanto, não há limite máximo no tamanho do ponto. Esse é o modo de renderização padrão. </li> 
      <li id="li_61C5AA926777449E8804C7BCE9E46F9B">Modo de renderização 2. O tamanho do ponto é definido no espaço mundial (os pontos permanecem em um tamanho constante em relação ao globo). Os pontos são renderizados usando polígonos, portanto, não há limite máximo no tamanho do ponto. </li> 
      <li id="li_C00527F959354D3BB7422EFFE1FB5135">Modo de renderização 3. O tamanho do ponto é definido no espaço da tela. Os pontos são renderizados usando pontos suaves do OpenGL. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

O [!DNL Zip Points.layer] arquivo é formatado da seguinte forma:

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

