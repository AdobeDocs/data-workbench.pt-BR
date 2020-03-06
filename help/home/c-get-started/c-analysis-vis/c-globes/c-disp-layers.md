---
description: O perfil Geografia armazena uma coleção de camadas e arquivos de imagem.
solution: Analytics
title: Exibir camadas
topic: Data workbench
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exibir camadas{#display-layers}

O perfil Geografia armazena uma coleção de camadas e arquivos de imagem.

Ao exibir um globo, você pode selecionar quais das camadas disponíveis serão exibidas para uma tarefa de análise específica:

* **Mármore Azul 2km:** Essa camada exibe o globo. Quando essa camada não está selecionada, o globo não é visível.
* **Coordenadas de IP:** Essa camada de ponto de elemento exibe a latitude e a longitude de locais em seu conjunto de dados com base nos endereços IP do visitante.
* **Pontos Zip:** Essa camada exibe a latitude e a longitude de locais em seu conjunto de dados com base em uma lista de códigos ZIP dos Estados Unidos fornecida pela Adobe. O arquivo de [!DNL Zip Points.txt] pesquisa contém os dados de CEP, latitude e longitude a serem exibidos, enquanto o [!DNL Zip Points.layer] arquivo contém os parâmetros de configuração necessários para exibir esses dados no globo. Ambos os arquivos são armazenados no diretório Profiles\Geography\Maps folder within the Data Workbench server installation directory.

* ***Outros nomes de camada disponíveis:*** Cada nome de camada representa um [!DNL .layer] arquivo armazenado na pasta Profiles\Geography\Maps folder, Perfis\IP Geo-location\Maps ou Perfis\IP Geo-Intelligence\Maps no diretório de instalação do Insight Server.

>[!NOTE]
>
>Para ter o perfil IP Geo-location ou IP Geo-Intelligence, você deve assinar o serviço de dados IP Geo-location ou IP Geo-intelligence, respectivamente.

Para controlar a ordem em que as camadas são exibidas, é possível usar um [!DNL order.txt] arquivo. Consulte [Personalização de menus usando arquivos](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)Order.txt.

**Alternar camadas em um globo**

* Clique com o botão direito do mouse na visualização e clique no nome da camada desejada. Um X à esquerda da camada indica que ela está visível.

