---
description: Você pode criar uma camada de vetor que faz referência a um ou mais arquivos de vetor (.vec), que contêm os dados que definem os vetores a serem desenhados no globo.
title: Definir camadas de vetor que fazem referência a arquivos vetoriais
uuid: fe6639fb-98fb-4246-9cc1-1a928df6ae0a
exl-id: d78fa7ea-e2a9-42b7-9071-5f72409c5b7a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 7%

---

# Definir camadas de vetor que fazem referência a arquivos vetoriais{#define-vector-layers-referencing-vector-files}

Você pode criar uma camada de vetor que faz referência a um ou mais arquivos de vetor (.vec), que contêm os dados que definem os vetores a serem desenhados no globo.

Para definir uma camada de vetor que faça referência a um ou mais arquivos [!DNL .vec], você deve ter o seguinte:

* **Um ou mais  [!DNL .vec]** arquivos que contêm os dados usados para desenhar os vetores no globo.

   >[!NOTE]
   >
   >Para obter arquivos [!DNL .vec] para usar com suas camadas de vetor, entre em contato com o Adobe.

* **Um** arquivo de camada que especifica o local dos  [!DNL .vec] arquivos. Para obter mais informações sobre o formato necessário do arquivo de camada, consulte [Formato de arquivo de camada de vetor](../../../../home/c-get-started/c-im-layers/c-vctr-layers/c-ref-vctr-files.md#section-83a0077cf0c8479b9e7b2939bc761af1).

   >[!NOTE]
   >
   >O arquivo [!DNL Boundaries.layer], fornecido com o perfil [!DNL Geography], é uma camada de vetor que faz referência aos arquivos [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec] e [!DNL mwisland.vec].

## Formato de arquivo de camada de vetor {#section-83a0077cf0c8479b9e7b2939bc761af1}

Cada arquivo de camada de vetor que faz referência a arquivos [!DNL .vec] deve ser formatado usando o seguinte modelo:

```
Layer = VectorLayer:
  Vec Files = vector: n items
    0 = string: Maps\\.vec file 1
    1 = string: Maps\\.vec file 2
    . . .
    n-1 = string: Maps\\.vec file n
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

| Parâmetro | Descrição |
|---|---|
| Arquivos Vec | Caminhos para o(s) arquivo(s) [!DNL .vec] contendo os dados vetoriais. |
| Cor do canal | O vetor de cores RGB, que é expresso como (vermelho, verde, azul). Para cada cor no vetor, você pode inserir um valor de 0,0 a 1,0. Por exemplo, (1,0, 0,0, 0,0) é vermelho vivo e (0,5, 0,5, 0,5) é cinza. |
| Alfa | Controla a transparência dos vetores mostrados no globo. O intervalo é de 0 a 1, sendo 0 o mais transparente. |
| Largura | Opcional. Define a largura dos dados em pixels. O intervalo recomendado é de 1 a 4. |
| Fator de erro | Controla a precisão com que os vetores são desenhados. Para valores maiores, os vetores são desenhados de forma menos precisa, mas mais rápida. O valor padrão é 5. |

O arquivo [!DNL Boundaries.layer] é formatado da seguinte maneira:

```
 Boundaries.layer file is formatted as follows:
Layer = VectorLayer:
  Vec Files = vector: 5 items
    0 = string: Maps\\mwnation.vec
    1 = string: Maps\\mwstate.vec
    2 = string: Maps\\mwcoast.vec
    3 = string: Maps\\mwlake.vec
    4 = string: Maps\\mwisland.vec
  Color = v3d: (.5,.5,1)
  Alpha = double: .5
  Error Factor = double: 4
```
