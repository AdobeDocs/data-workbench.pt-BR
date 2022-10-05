---
description: Informações conceituais sobre as camadas de perfil Geografia, tipos de camadas de imagem e criação de novas camadas.
title: Entender camadas de imagem
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
exl-id: ffe084ec-db8b-46f4-8266-0f1b771b3349
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 1%

---

# Entender camadas de imagem{#understanding-imagery-layers}

{{eol}}

Informações conceituais sobre as camadas de perfil Geografia, tipos de camadas de imagem e criação de novas camadas.

## Tipos de camadas de imagem {#section-ce25364651a04cd1b83f9ac7c231fa41}

Análise de big data [!DNL Geography] permite exibir os seguintes tipos de camadas de imagem no Data Workbench:

* **Camada de imagem do terreno:** Esse tipo de camada exibe imagens do terreno da Terra, sobre as quais podem ser exibidos dados geográficos. A visualização de globo no Data Workbench é um exemplo de uma camada de imagem do terreno. Consulte [Trabalhar com camadas de imagem do terreno](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

* **Camada do ponto de elemento:** Esse tipo de camada exibe um ponto no globo para cada elemento de uma dimensão. Consulte [Trabalhar com camadas de ponto de elemento](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9).

* **Camada de vetor:** Esse tipo de camada exibe dados vetoriais (arte de linha) no globo. Consulte [Trabalhar com camadas de vetor](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620).

No Data Workbench, é possível selecionar qual dessas camadas deseja exibir para uma tarefa de análise específica.

## Camadas de perfil geográfico {#section-4d9fb9b357764493a4d97d2b4068bb67}

O [!DNL Geography] O perfil fornece um conjunto de camadas de imagem padrão, que são armazenadas na pasta Perfis\Geografia\Maps no diretório de instalação do servidor do Data Workbench:

* **Marcha Azul 2km:** Essa camada de imagem do terreno cria um mapa-3-D do mundo, que é o que é exibido quando você adiciona a visualização do globo a um espaço de trabalho. Quando essa camada não está selecionada, o globo não é visível, mas as outras camadas ainda são exibidas. O [!DNL Blue Marble 2km.layer] O arquivo faz referência ao [!DNL Blue Marble 2km.tsi] arquivo.

   Para obter informações sobre como trabalhar com a visualização de globo, consulte o *Guia do usuário do Data Workbench*.

* **Pontos do CEP:** Essa camada de ponto de elemento permite mapear locais em seu conjunto de dados usando um CEP dos Estados Unidos. O [!DNL Zip Points.txt] O arquivo de pesquisa (fornecido pelo Adobe) contém uma lista de todos os códigos postais dos Estados Unidos e a latitude e longitude de cada código postal. O [!DNL Zip Points.layer] O arquivo faz referência ao [!DNL Zip Points.txt] e o [!DNL Zipcode.dim] e contém os parâmetros de configuração necessários para exibir os locais no globo. Cada elemento da dimensão CEP ( [!DNL Zipcode.dim]) que você define no conjunto de dados é mapeado no mundo utilizando a latitude e a longitude listadas para esse CEP na [!DNL Zip Points.txt] arquivo de pesquisa.

   Para obter informações sobre como definir dimensões, consulte *Guia de configuração do conjunto de dados.*

* **Limites:** Essa camada vetorial fornece os principais limites políticos mundiais, como países, além dos limites de características físicas naturais da Terra, como lagos e ilhas. O [!DNL Boundaries.layer] O arquivo faz referência a um ou mais dos [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec]e [!DNL world boundaries.vec] arquivos.

* **Coordenadas de IP:** Essa camada de ponto de elemento usa pontos dinâmicos para permitir que você mapeie locais em seu conjunto de dados usando endereços IP. O [!DNL IP Coordinates.layer] arquivo faz referência à dimensão Coordenadas ( [!DNL Coordinates.dim]) e especifica a métrica Visitantes como a métrica a ser usada para determinar o tamanho dos pontos no mundo para cada coordenada.

Seu [!DNL Geography] O perfil ou outros perfis na sua instalação podem conter camadas de imagem adicionais fornecidas pelo Adobe ou criadas pela sua empresa.

## Criar novas camadas {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

Você pode criar novas camadas de imagem copiando o tipo apropriado de arquivo de camada incluído na [!DNL Geography] perfil em qualquer pasta Perfis\*nome do perfil*\Mapas, renomeando e editando o arquivo conforme apropriado. Todas as novas camadas devem atender aos seguintes requisitos:

* O [!DNL .layer] deve seguir o formato de um dos tipos de camada compatíveis.
* O [!DNL .layer] O arquivo deve fazer referência aos arquivos de pesquisa e dimensão apropriados, se necessário.
* O arquivo de pesquisa referenciado também deve ser armazenado dentro do diretório de instalação do servidor do Data Workbench e seu caminho deve ser especificado com precisão no [!DNL .layer] arquivo.

Para obter mais informações sobre o formato e os parâmetros de cada tipo de arquivo de camada e seus arquivos associados, consulte a seção neste capítulo para o tipo de camada apropriado.
