---
description: Ao criar uma camada de vetor que faz referência a um arquivo de valores separados por tabulação (.tsv), os dados de vetor são obtidos recuperando instruções de desenho, bem como dados de longitude e latitude do arquivo .tsv.
solution: Analytics
title: Camadas de vetor que fazem referência a arquivos de valores separados por tabulação
topic: Data workbench
uuid: 42607b34-e9f2-420a-ba5a-05562598b480
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Camadas de vetor que fazem referência a arquivos de valores separados por tabulação{#vector-layers-referencing-tab-separated-values-files}

Ao criar uma camada de vetor que faz referência a um arquivo de valores separados por tabulação (.tsv), os dados de vetor são obtidos recuperando instruções de desenho, bem como dados de longitude e latitude do arquivo .tsv.

Para definir uma camada de vetor que faz referência a um [!DNL .tsv] arquivo, é necessário ter o seguinte:

* **Um[!DNL .tsv]arquivo** que contém os dados usados para desenhar os vetores no globo, incluindo dados de longitude e latitude. Para obter mais informações sobre o formato necessário do [!DNL .tsv] arquivo, consulte Formato [](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-a29012c9ff4444ac8a6d41c68482828e)de arquivo Vetor TSV.

* **Um arquivo** de camada que especifica o local do [!DNL .tsv] arquivo. Para obter mais informações sobre o formato necessário do arquivo de camada, consulte Formato [de arquivo de camada de](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-c430923f341f4c93852e9f24b61e82bf)vetor.

## Formato de arquivo Vetor TSV {#section-a29012c9ff4444ac8a6d41c68482828e}

O [!DNL .tsv] arquivo deve conter as seguintes três colunas separadas por tabulação:

* **[!DNL Begin]:**Essa coluna deve indicar se uma nova linha deve ser iniciada. Os valores nesta coluna podem ser 0 (não iniciar uma nova linha) ou 1 (iniciar uma nova linha).
* **[!DNL Longitude]:**Essa coluna deve conter valores de longitude.
* **[!DNL Latitude]:**Essa coluna deve conter valores de latitude.

>[!NOTE]
>
>Quaisquer colunas adicionais são ignoradas.

A seguir, há um arquivo de amostra [!DNL .tsv] que contém dados para uma camada de vetor:

![](assets/tsv_vectorlayer.png)

## Formato de arquivo de camada vetorial {#section-c430923f341f4c93852e9f24b61e82bf}

Cada arquivo de camada de vetor que faz referência a [!DNL .tsv] arquivos deve ser formatado usando o seguinte modelo:

```
Layer = VectorLayer:
  TSV Files = vector: n items
    0 = string: Maps\\File Name.tsv
    1 = string: Maps\\File Name.tsv
    . . .
    n-1 = string: Maps\\File Name.tsv
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

<table id="table_152F73536AB9403AB43854B81D6A9A15"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Arquivos TSV </td> 
   <td colname="col2"> <p>Caminhos para os arquivos <span class="filepath"> .tsv</span> que contêm os dados vetoriais. </p> <p>Exemplo: <span class="filepath"> Mapas\\USVectorData.tsv</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cor do canal </td> 
   <td colname="col2"> O vetor de cor RGB, que é expresso como (vermelho, verde, azul). Para cada cor no vetor, você pode inserir um valor de 0,0 a 1,0. Por exemplo, (1.0, 0.0, 0.0) é vermelho vivo e (0.5, 0.5, 0.5, 0.5) é cinza. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alfa </td> 
   <td colname="col2"> Controla a transparência dos vetores exibidos no globo. O intervalo é de 0 a 1, sendo 0 o mais transparente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Largura </td> 
   <td colname="col2"> Opcional. Define a largura dos dados em pixels. O intervalo recomendado é de 1 a 4. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fator de erro </td> 
   <td colname="col2"> Controla a precisão com que os vetores são desenhados. Para valores maiores, os vetores são desenhados de forma menos precisa, mas mais rápida. O valor padrão é 5. </td> 
  </tr> 
 </tbody> 
</table>

