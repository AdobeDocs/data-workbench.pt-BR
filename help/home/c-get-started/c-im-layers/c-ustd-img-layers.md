---
description: Informações conceituais sobre camadas de imagens.
solution: Analytics
title: Sobre camadas de imagens
topic: Data workbench
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Sobre camadas de imagens{#about-imagery-layers}

Informações conceituais sobre camadas de imagens.

## Tipos de camadas de imagem {#section-891cbf61e8334690bd203a2bb9761b25}

Você pode exibir os seguintes tipos de camadas de imagem na Análise de big data:

* **[!UICONTROL Terrain image layer]:**Esse tipo de camada exibe imagens do terreno da Terra, sobre as quais dados geográficos podem ser exibidos. A visualização do globo em é um exemplo de uma camada de imagem do terreno. Consulte[Trabalhar com Camadas](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f)de Imagem de Terreno.

* **[!UICONTROL Element point layer]:**Esse tipo de camada exibe um ponto no globo para cada elemento de uma dimensão. Consulte[Trabalhar com camadas](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd)de ponto de elemento.

* **[!UICONTROL Vector layer]:**Esse tipo de camada exibe dados vetoriais (arte em linha) no globo. Consulte[Trabalhar com camadas](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9)de vetor.

* **[!UICONTROL Presentation layer]** Anote e esclareça as visualizações usando uma sobreposição da apresentação. Adicione chamadas de texto, setas, imagens e codificação por cores para destacar e esclarecer seus dados e, então, compartilhar com outras pessoas.

Na Análise de big data, você pode selecionar qual dessas camadas deseja exibir para uma tarefa de análise específica.

## Camadas de perfil geográfico {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

O [!DNL Geography] perfil fornece um conjunto de camadas de imagem padrão, que são armazenadas em Profiles\Geography\Maps folder within the Data Workbench server installation directory:

* **[!UICONTROL Blue Marble 2km]:**Essa camada de imagem do terreno cria um mapa do mundo em 3-D, que é o que é exibido quando você adiciona a visualização do globo a um espaço de trabalho. Quando essa camada não está selecionada, o globo não é visível, mas as outras camadas ainda são exibidas. O[!DNL Blue Marble 2km.layer]arquivo faz referência ao[!DNL Blue Marble 2km.tsi]arquivo.

* **[!UICONTROL Zip Points]:**Essa camada de ponto de elemento permite mapear locais em seu conjunto de dados usando um Código ZIP dos Estados Unidos. O arquivo de[!DNL Zip Points.txt]pesquisa (fornecido pela Adobe) contém uma lista de todos os códigos ZIP dos Estados Unidos e a latitude e longitude de cada código ZIP. O[!DNL Zip Points.layer]arquivo faz referência ao[!DNL Zip Points.txt]arquivo e ao[!DNL Zipcode.dim]arquivo e contém os parâmetros de configuração necessários para exibir os locais no globo. Cada elemento da dimensão CEP ([!DNL Zipcode.dim]) que você define em seu conjunto de dados é mapeado no globo usando a latitude e a longitude listadas para esse CEP no arquivo de[!DNL Zip Points.txt]pesquisa.

   Para obter informações sobre como definir dimensões, consulte o Guia *de Configuração de* Conjunto de Dados.

* **[!UICONTROL Boundaries]:**Essa camada vetorial fornece os principais limites políticos mundiais, como países, assim como os limites das características físicas naturais da Terra, como lagos e ilhas. O[!DNL Boundaries.layer]arquivo faz referência a um ou mais dos arquivos[!DNL mwcoast.vec],[!DNL mwisland.vec],[!DNL mwlake.vec],[!DNL mwnation.vec],[!DNL mwriver.vec],[!DNL mwstate.vec],[!DNL US states.vec]e[!DNL world boundaries.vec].

* **[!UICONTROL IP Coordinates]:**Essa camada de ponto de elemento usa pontos dinâmicos para permitir que você mapeie locais em seu conjunto de dados usando endereços IP. O[!DNL IP Coordinates.layer]arquivo faz referência à dimensão Coordenadas ([!DNL Coordinates.dim]) e especifica a métrica Visitantes como a métrica a ser usada para determinar o tamanho dos pontos no globo para cada coordenada.

Seu perfil [!UICONTROLNL geográfico] ou outros perfis em sua instalação podem conter camadas de imagens adicionais fornecidas pela Adobe ou criadas por sua empresa.

## Create a new layer {#section-b5313773316c4e0fa748f7376a8e7f0b}

Você pode criar novas camadas de imagem copiando o tipo apropriado de arquivo de camada incluído no [!DNL Geography] perfil em qualquer pasta Perfis\*nome do perfil*\Mapas e, em seguida, renomeando e editando o arquivo conforme apropriado. Todas as novas camadas devem atender aos seguintes requisitos:

* O [!DNL .layer] arquivo deve seguir o formato de um dos tipos de camada suportados.
* O [!DNL .layer] arquivo deve fazer referência aos arquivos de pesquisa e dimensão apropriados, se necessário.
* O arquivo de pesquisa referenciado também deve ser armazenado dentro do diretório de instalação do servidor do Análise de big data e seu caminho deve ser especificado com precisão no [!DNL .layer] arquivo.

Para obter mais informações sobre o formato e os parâmetros para cada tipo de arquivo de camada e seus arquivos associados, consulte a seção neste capítulo para o tipo de camada apropriado.
