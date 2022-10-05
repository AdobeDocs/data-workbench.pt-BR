---
description: Informações conceituais sobre camadas de imagem.
title: Sobre camadas de imagem
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
exl-id: c6d30747-70d2-4489-ad64-fd131e76a7a2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 5%

---

# Sobre camadas de imagem{#about-imagery-layers}

{{eol}}

Informações conceituais sobre camadas de imagem.

## Tipos de camadas de imagem {#section-891cbf61e8334690bd203a2bb9761b25}

Você pode exibir os seguintes tipos de camadas de imagem no Data Workbench:

* **[!UICONTROL Terrain image layer]:** Esse tipo de camada exibe imagens do terreno da Terra, sobre as quais podem ser exibidos dados geográficos. A visualização de globo no é um exemplo de uma camada de imagem do terreno. Consulte [Trabalhar com camadas de imagem do terreno](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).

* **[!UICONTROL Element point layer]:** Esse tipo de camada exibe um ponto no globo para cada elemento de uma dimensão. Consulte [Trabalhar com camadas de ponto de elemento](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd).

* **[!UICONTROL Vector layer]:** Esse tipo de camada exibe dados vetoriais (arte de linha) no globo. Consulte [Trabalhar com camadas de vetor](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9).

* **[!UICONTROL Presentation layer]** Anote e esclareça as visualizações usando uma sobreposição da apresentação. Adicione chamadas de texto, setas, imagens e codificação por cores para destacar e esclarecer seus dados e, então, compartilhar com outras pessoas.

Na Data Workbench, é possível selecionar qual dessas camadas deseja exibir para uma tarefa de análise específica.

## Camadas de perfil geográfico {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

O [!DNL Geography] O perfil fornece um conjunto de camadas de imagem padrão, que são armazenadas na pasta Perfis\Geografia\Maps no diretório de instalação do servidor do Data Workbench:

* **[!UICONTROL Blue Marble 2km]:** Essa camada de imagem do terreno cria um mapa-3-D do mundo, que é o que é exibido quando você adiciona a visualização do globo a um espaço de trabalho. Quando essa camada não está selecionada, o globo não é visível, mas as outras camadas ainda são exibidas. O [!DNL Blue Marble 2km.layer] O arquivo faz referência ao [!DNL Blue Marble 2km.tsi] arquivo.

* **[!UICONTROL Zip Points]:** Essa camada de ponto de elemento permite mapear locais em seu conjunto de dados usando um CEP dos Estados Unidos. O [!DNL Zip Points.txt] O arquivo de pesquisa (fornecido pelo Adobe) contém uma lista de todos os códigos postais dos Estados Unidos e a latitude e longitude de cada código postal. O [!DNL Zip Points.layer] O arquivo faz referência ao [!DNL Zip Points.txt] e o [!DNL Zipcode.dim] e contém os parâmetros de configuração necessários para exibir os locais no globo. Cada elemento da dimensão CEP ( [!DNL Zipcode.dim]) que você define no conjunto de dados é mapeado no mundo utilizando a latitude e a longitude listadas para esse CEP na [!DNL Zip Points.txt] arquivo de pesquisa.

   Para obter informações sobre como definir dimensões, consulte *Guia de configuração do conjunto de dados*.

* **[!UICONTROL Boundaries]:** Essa camada vetorial fornece os principais limites políticos mundiais, como países, além dos limites de características físicas naturais da Terra, como lagos e ilhas. O [!DNL Boundaries.layer] O arquivo faz referência a um ou mais dos [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec]e [!DNL world boundaries.vec] arquivos.

* **[!UICONTROL IP Coordinates]:** Essa camada de ponto de elemento usa pontos dinâmicos para permitir que você mapeie locais em seu conjunto de dados usando endereços IP. O [!DNL IP Coordinates.layer] arquivo faz referência à dimensão Coordenadas ( [!DNL Coordinates.dim]) e especifica a métrica Visitantes como a métrica a ser usada para determinar o tamanho dos pontos no mundo para cada coordenada.

Seu [!UICONTROL NL Geography] O perfil ou outros perfis na sua instalação podem conter camadas de imagem adicionais fornecidas pelo Adobe ou criadas pela sua empresa.

## Criar uma nova camada {#section-b5313773316c4e0fa748f7376a8e7f0b}

Você pode criar novas camadas de imagem copiando o tipo apropriado de arquivo de camada incluído na [!DNL Geography] perfil em qualquer pasta Perfis\*nome do perfil*\Mapas, renomeando e editando o arquivo conforme apropriado. Todas as novas camadas devem atender aos seguintes requisitos:

* O [!DNL .layer] deve seguir o formato de um dos tipos de camada compatíveis.
* O [!DNL .layer] O arquivo deve fazer referência aos arquivos de pesquisa e dimensão apropriados, se necessário.
* O arquivo de pesquisa referenciado também deve ser armazenado dentro do diretório de instalação do servidor do Data Workbench e seu caminho deve ser especificado com precisão no [!DNL .layer] arquivo.

Para obter mais informações sobre o formato e os parâmetros de cada tipo de arquivo de camada e seus arquivos associados, consulte a seção neste capítulo para o tipo de camada apropriado.
