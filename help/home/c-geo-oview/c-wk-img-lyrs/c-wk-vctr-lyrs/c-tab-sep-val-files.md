---
description: Ao criar uma camada de vetor que faz referência a um arquivo de valores separados por tabulação (.tsv), os dados de vetor são obtidos recuperando instruções de desenho, bem como dados de longitude e latitude do arquivo .tsv.
title: Camadas de vetor que fazem referência a arquivos de valores separados por tabulação
uuid: 42607b34-e9f2-420a-ba5a-05562598b480
exl-id: be16ba73-4a98-472b-98f1-1b32e671b763,7b0b0286-072b-4b31-b6ec-ced322da5236
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 6%

---

# Camadas de vetor que fazem referência a arquivos de valores separados por tabulação{#vector-layers-referencing-tab-separated-values-files}

Ao criar uma camada de vetor que faz referência a um arquivo de valores separados por tabulação (.tsv), os dados de vetor são obtidos recuperando instruções de desenho, bem como dados de longitude e latitude do arquivo .tsv.

Para definir uma camada de vetor que faça referência a arquivos [!DNL .tsv], você deve ter o seguinte:

* **Um  [!DNL .tsv]** arquivo que contém os dados usados para desenhar os vetores no globo, incluindo dados de longitude e latitude. Para obter mais informações sobre o formato necessário do arquivo [!DNL .tsv], consulte [Vetor TSV File Format](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-a29012c9ff4444ac8a6d41c68482828e).

* **Um** arquivo de camada que especifica o local do  [!DNL .tsv] arquivo. Para obter mais informações sobre o formato necessário do arquivo de camada, consulte [Formato de arquivo de camada de vetor](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-c430923f341f4c93852e9f24b61e82bf).

## Formato de arquivo TSV vetorial {#section-a29012c9ff4444ac8a6d41c68482828e}

O arquivo [!DNL .tsv] deve conter as três colunas separadas por tabulação a seguir:

* **[!DNL Begin]:** essa coluna deve indicar se uma nova linha deve ser iniciada. Os valores desta coluna podem ser 0 (não inicie uma nova linha) ou 1 (comece uma nova linha).
* **[!DNL Longitude]:** essa coluna deve conter valores de longitude.
* **[!DNL Latitude]:** essa coluna deve conter valores de latitude.

>[!NOTE]
>
>Quaisquer colunas adicionais são ignoradas.

A seguir, um exemplo de arquivo [!DNL .tsv] que contém dados para uma camada de vetor:

![](assets/tsv_vectorlayer.png)

## Formato de arquivo de camada de vetor {#section-c430923f341f4c93852e9f24b61e82bf}

Cada arquivo de camada de vetor que faz referência a arquivos [!DNL .tsv] deve ser formatado usando o seguinte modelo:

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
   <td colname="col2"> <p>Caminhos para o(s) arquivo(s) <span class="filepath"> .tsv</span> contendo os dados vetoriais. </p> <p>Exemplo: <span class="filepath"> Mapas\\USVectorData.tsv</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cor do canal </td> 
   <td colname="col2"> O vetor de cores RGB, que é expresso como (vermelho, verde, azul). Para cada cor no vetor, você pode inserir um valor de 0,0 a 1,0. Por exemplo, (1,0, 0,0, 0,0) é vermelho vivo e (0,5, 0,5, 0,5) é cinza. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alfa </td> 
   <td colname="col2"> Controla a transparência dos vetores mostrados no globo. O intervalo é de 0 a 1, sendo 0 o mais transparente. </td> 
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
