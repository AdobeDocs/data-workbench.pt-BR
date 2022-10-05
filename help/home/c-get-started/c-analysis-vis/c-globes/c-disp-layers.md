---
description: O perfil Geografia armazena uma coleção de camadas e arquivos de imagem.
title: Exibir camadas
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
exl-id: 12ec913f-c7e5-49b5-8792-db0881cb5cfe
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 1%

---

# Exibir camadas{#display-layers}

{{eol}}

O perfil Geografia armazena uma coleção de camadas e arquivos de imagem.

Ao exibir um globo, é possível selecionar quais das camadas disponíveis serão exibidas para uma tarefa de análise específica:

* **Marcha Azul 2km:** Essa camada exibe o globo. Quando essa camada não está selecionada, o globo não fica visível.
* **Coordenadas de IP:** Essa camada de ponto de elemento exibe a latitude e a longitude de locais em seu conjunto de dados com base nos endereços IP do visitante.
* **Pontos do CEP:** Essa camada exibe a latitude e a longitude de locais em seu conjunto de dados com base em uma lista de códigos postais dos Estados Unidos fornecida pelo Adobe. O [!DNL Zip Points.txt] o arquivo de pesquisa contém os dados de CEP, latitude e longitude a serem exibidos, enquanto o [!DNL Zip Points.layer] contém os parâmetros de configuração necessários para exibir esses dados em todo o mundo. Ambos os arquivos são armazenados na pasta Profiles\Geografia\Maps no diretório de instalação do servidor do Data Workbench.

* ***Outros nomes de camada disponíveis:*** Cada nome de camada representa uma [!DNL .layer] arquivo armazenado na pasta Perfis\Geografia\Maps , Perfis\IP Geo-location\Mapas ou Perfis\IP Geo-intelligence\Maps no diretório de instalação do Insight Server.

>[!NOTE]
>
>Para ter o perfil de Geolocalização de IP ou Geolocalização de IP, você deve assinar o serviço de dados de Geolocalização de IP ou Geolocalização de IP, respectivamente.

Para controlar a ordem em que as camadas são exibidas, é possível usar um [!DNL order.txt] arquivo. Consulte [Personalização de menus usando arquivos Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

**Para alternar camadas em um globo**

* Clique com o botão direito do mouse na visualização e clique no nome da camada desejada. Um X à esquerda da camada indica que a camada está visível.
