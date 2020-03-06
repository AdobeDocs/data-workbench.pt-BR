---
description: Informações conceituais sobre as camadas de perfil Geografia, os tipos de camadas de imagem e a criação de novas camadas.
solution: Analytics
title: Como entender as camadas de imagens
topic: Data workbench
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Como entender as camadas de imagens{#understanding-imagery-layers}

Informações conceituais sobre as camadas de perfil Geografia, os tipos de camadas de imagem e a criação de novas camadas.

## Tipos de camadas de imagem {#section-ce25364651a04cd1b83f9ac7c231fa41}

A análise de big data [!DNL Geography] permite exibir os seguintes tipos de camadas de imagem na análise de big data:

* **Camada de imagem do terreno:** Esse tipo de camada exibe imagens do terreno da Terra, sobre as quais dados geográficos podem ser exibidos. A visualização do globo na análise de big data é um exemplo de uma camada de imagem do terreno. Consulte [Trabalhar com Camadas](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf)de Imagem de Terreno.

* **Camada do ponto de elemento:** Esse tipo de camada exibe um ponto no globo para cada elemento de uma dimensão. Consulte [Trabalhar com camadas](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9)de ponto de elemento.

* **Camada vetorial:** Esse tipo de camada exibe dados vetoriais (arte em linha) no globo. Consulte [Trabalhar com camadas](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620)de vetor.

Na análise de big data, você pode selecionar qual dessas camadas deseja exibir para uma tarefa de análise específica.

## Camadas de perfil geográfico {#section-4d9fb9b357764493a4d97d2b4068bb67}

O [!DNL Geography] perfil fornece um conjunto de camadas de imagem padrão, que são armazenadas em Profiles\Geography\Maps folder within the data workbench server installation directory:

* **Mármore Azul 2km:** Essa camada de imagem do terreno cria um mapa do mundo em 3-D, que é o que é exibido quando você adiciona a visualização do globo a um espaço de trabalho. Quando essa camada não está selecionada, o globo não é visível, mas as outras camadas ainda são exibidas. O [!DNL Blue Marble 2km.layer] arquivo faz referência ao [!DNL Blue Marble 2km.tsi] arquivo.

   Para obter informações sobre como trabalhar com a visualização global, consulte o Guia *do usuário da Análise de* big data.

* **Pontos Zip:** Essa camada de ponto de elemento permite mapear locais em seu conjunto de dados usando um Código ZIP dos Estados Unidos. O arquivo de [!DNL Zip Points.txt] pesquisa (fornecido pela Adobe) contém uma lista de todos os códigos ZIP dos Estados Unidos e a latitude e longitude de cada código ZIP. O [!DNL Zip Points.layer] arquivo faz referência ao [!DNL Zip Points.txt] arquivo e ao [!DNL Zipcode.dim] arquivo e contém os parâmetros de configuração necessários para exibir os locais no globo. Cada elemento da dimensão CEP ( [!DNL Zipcode.dim]) que você define em seu conjunto de dados é mapeado no globo usando a latitude e a longitude listadas para esse CEP no arquivo de [!DNL Zip Points.txt] pesquisa.

   Para obter informações sobre como definir dimensões, consulte o Guia de Configuração de *Conjunto de Dados.*

* **Limites:** Essa camada vetorial fornece os principais limites políticos mundiais, como países, assim como os limites das características físicas naturais da Terra, como lagos e ilhas. O [!DNL Boundaries.layer] arquivo faz referência a um ou mais dos arquivos [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec]e [!DNL world boundaries.vec] .

* **Coordenadas de IP:** Essa camada de ponto de elemento usa pontos dinâmicos para permitir que você mapeie locais em seu conjunto de dados usando endereços IP. O [!DNL IP Coordinates.layer] arquivo faz referência à dimensão Coordenadas ( [!DNL Coordinates.dim]) e especifica a métrica Visitantes como a métrica a ser usada para determinar o tamanho dos pontos no globo para cada coordenada.

Seu [!DNL Geography] perfil ou outros perfis na instalação podem conter camadas de imagem adicionais fornecidas pela Adobe ou criadas pela sua empresa.

## Criar novas camadas {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

Você pode criar novas camadas de imagem copiando o tipo apropriado de arquivo de camada incluído no [!DNL Geography] perfil em qualquer pasta Perfis\*nome do perfil*\Mapas e, em seguida, renomeando e editando o arquivo conforme apropriado. Todas as novas camadas devem atender aos seguintes requisitos:

* O [!DNL .layer] arquivo deve seguir o formato de um dos tipos de camada suportados.
* O [!DNL .layer] arquivo deve fazer referência aos arquivos de pesquisa e dimensão apropriados, se necessário.
* O arquivo de pesquisa referenciado também deve ser armazenado dentro do diretório de instalação do servidor da análise de big data e seu caminho deve ser especificado com precisão no [!DNL .layer] arquivo.

Para obter mais informações sobre o formato e os parâmetros para cada tipo de arquivo de camada e seus arquivos associados, consulte a seção neste capítulo para o tipo de camada apropriado.
