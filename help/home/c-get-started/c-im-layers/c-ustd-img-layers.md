---
description: Informações conceituais sobre camadas de imagem.
title: Sobre camadas de imagem
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
exl-id: c6d30747-70d2-4489-ad64-fd131e76a7a2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 5%

---

# Sobre camadas de imagem{#about-imagery-layers}

Informações conceituais sobre camadas de imagem.

## Tipos de camadas de imagem {#section-891cbf61e8334690bd203a2bb9761b25}

Você pode exibir os seguintes tipos de camadas de imagem no Data Workbench:

* **[!UICONTROL Terrain image layer]:** Esse tipo de camada exibe imagens do terreno da Terra, sobre as quais dados geográficos podem ser exibidos. A visualização de globo no é um exemplo de uma camada de imagem do terreno. Consulte [Trabalhar com camadas de imagem do terreno](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).

* **[!UICONTROL Element point layer]:** esse tipo de camada exibe um ponto no globo para cada elemento de uma dimensão. Consulte [Trabalhar com camadas de ponto de elemento](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd).

* **[!UICONTROL Vector layer]:** esse tipo de camada exibe dados vetoriais (arte de linha) no globo. Consulte [Trabalhar com camadas de vetor](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9).

* **[!UICONTROL Presentation layer]** Anote e esclareça as visualizações usando uma sobreposição da apresentação. Adicione chamadas de texto, setas, imagens e codificação por cores para destacar e esclarecer seus dados e, então, compartilhar com outras pessoas.

Na Data Workbench, é possível selecionar qual dessas camadas deseja exibir para uma tarefa de análise específica.

## Camadas de perfil geográfico {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

O perfil [!DNL Geography] fornece um conjunto de camadas de imagem padrão, que são armazenadas no diretório Profiles\Geography\Maps folder within the Data Workbench server installation directory:

* **[!UICONTROL Blue Marble 2km]:** essa camada de imagem do terreno cria um mapa-3-D do mundo, que é o que é exibido quando você adiciona a visualização do globo a um espaço de trabalho. Quando essa camada não está selecionada, o globo não é visível, mas as outras camadas ainda são exibidas. O arquivo [!DNL Blue Marble 2km.layer] faz referência ao arquivo [!DNL Blue Marble 2km.tsi].

* **[!UICONTROL Zip Points]:** essa camada de ponto de elemento permite mapear locais no conjunto de dados usando um CEP dos Estados Unidos. O arquivo de pesquisa [!DNL Zip Points.txt] (fornecido pelo Adobe) contém uma lista de todos os códigos postais dos Estados Unidos e a latitude e longitude de cada código postal. O arquivo [!DNL Zip Points.layer] faz referência ao arquivo [!DNL Zip Points.txt] e [!DNL Zipcode.dim] e contém os parâmetros de configuração necessários para exibir os locais no globo. Cada elemento da dimensão CEP ( [!DNL Zipcode.dim]) que você define em seu conjunto de dados é mapeado no mundo usando a latitude e a longitude listadas para esse CEP no arquivo de pesquisa [!DNL Zip Points.txt].

   Para obter informações sobre como definir dimensões, consulte o *Guia de Configuração de Conjunto de Dados*.

* **[!UICONTROL Boundaries]:** Essa camada vetorial fornece os principais limites políticos mundiais, como países, bem como os limites de características físicas naturais da Terra, como lagos e ilhas. O arquivo [!DNL Boundaries.layer] faz referência a um ou mais dos arquivos [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec] e [!DNL world boundaries.vec].

* **[!UICONTROL IP Coordinates]:** essa camada de ponto de elemento usa pontos dinâmicos para permitir que você mapeie locais em seu conjunto de dados usando endereços IP. O arquivo [!DNL IP Coordinates.layer] faz referência à dimensão Coordenadas ( [!DNL Coordinates.dim]) e especifica a métrica Visitantes como a métrica a ser usada para determinar o tamanho dos pontos no globo para cada coordenada.

Seu perfil [!UICONTROL NL Geography] ou outros perfis em sua instalação podem conter camadas de imagem adicionais fornecidas pelo Adobe ou criadas por sua empresa.

## Criar uma nova camada {#section-b5313773316c4e0fa748f7376a8e7f0b}

Você pode criar novas camadas de imagem copiando o tipo apropriado de arquivo de camada incluído no perfil [!DNL Geography] em qualquer pasta Perfis\*nome do perfil*\Mapas e, em seguida, renomeando e editando o arquivo conforme apropriado. Todas as novas camadas devem atender aos seguintes requisitos:

* O arquivo [!DNL .layer] deve seguir o formato de um dos tipos de camada compatíveis.
* O arquivo [!DNL .layer] deve fazer referência aos arquivos de pesquisa e dimensão apropriados, se necessário.
* O arquivo de pesquisa referenciado também deve ser armazenado no diretório de instalação do servidor do Data Workbench e seu caminho deve ser especificado com precisão no arquivo [!DNL .layer].

Para obter mais informações sobre o formato e os parâmetros de cada tipo de arquivo de camada e seus arquivos associados, consulte a seção neste capítulo para o tipo de camada apropriado.
