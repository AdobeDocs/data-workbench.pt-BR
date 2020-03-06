---
description: Ao criar uma camada de ponto de elemento que faz referência a um arquivo de pesquisa para obter dados de latitude e longitude, o local do ponto é obtido recuperando cada elemento e sua latitude e longitude associadas do arquivo de pesquisa.
solution: Analytics
title: Definindo Camadas de Ponto de Elemento que Fazem Referência a Arquivos de Pesquisa
topic: Data workbench
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definindo Camadas de Ponto de Elemento que Fazem Referência a Arquivos de Pesquisa{#defining-element-point-layers-referencing-lookup-files}

Ao criar uma camada de ponto de elemento que faz referência a um arquivo de pesquisa para obter dados de latitude e longitude, o local do ponto é obtido recuperando cada elemento e sua latitude e longitude associadas do arquivo de pesquisa.

Em vez de usar um arquivo de pesquisa, você pode usar a [!DNL Dynamic Points] funcionalidade, que incorpora a latitude e a longitude de um local no nome de cada elemento de uma dimensão. Consulte [Definindo Camadas de Ponto de Elemento Usando Pontos](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3)Dinâmicos.

Para definir uma camada de ponto de elemento que referencie um arquivo de pesquisa, você deve criar ou já ter disponível o seguinte:

* **Uma dimensão** definida no [!DNL Transformation.cfg] arquivo ou um conjunto de dados de transformação inclui o arquivo. Para obter informações sobre arquivos de configuração de transformação, consulte o Guia *de Configuração de* Conjunto de Dados.

* **Um arquivo** de pesquisa contendo os dados usados para plotar cada ponto de dados. Esse arquivo deve conter pelo menos três colunas de dados para cada ponto de dados: a chave, a longitude e a latitude. Para obter mais informações sobre o formato necessário do arquivo de pesquisa, consulte Formato [de Arquivo de Pesquisa do Ponto](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121)de Elemento.

* **Um arquivo** de camada que especifica o local do arquivo de pesquisa e identifica a dimensão e métrica relacionadas, bem como os nomes das colunas chave, longitude e latitude no arquivo de pesquisa. Para obter mais informações sobre o formato necessário do arquivo de camada, consulte Formato [de Arquivo de Camada de Ponto](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981)de Elemento.

>[!NOTE]
>
>O [!DNL Zip Points.layer] arquivo, fornecido com o [!DNL Geography] perfil, é uma camada de ponto de elemento que identifica o [!DNL Zipcode.dim] arquivo, o [!DNL Sessions.metric] arquivo, o arquivo de [!DNL Zip Points.txt] pesquisa e os nomes das colunas chave, longitude, latitude e nome no arquivo de pesquisa.

