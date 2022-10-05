---
description: Ao criar uma camada de ponto de elemento que faz referência a um arquivo de pesquisa para obter dados de latitude e longitude, o local do ponto é obtido recuperando cada elemento e sua latitude e longitude associadas do arquivo de pesquisa.
title: Definir camadas de ponto de elemento que fazem referência a arquivos de pesquisa
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
exl-id: b6928821-c825-43e2-8c7b-2ce0f49aa67e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 4%

---

# Definir camadas de ponto de elemento que fazem referência a arquivos de pesquisa{#defining-element-point-layers-referencing-lookup-files}

{{eol}}

Ao criar uma camada de ponto de elemento que faz referência a um arquivo de pesquisa para obter dados de latitude e longitude, o local do ponto é obtido recuperando cada elemento e sua latitude e longitude associadas do arquivo de pesquisa.

Em vez de usar um arquivo de pesquisa, você pode usar o [!DNL Dynamic Points] , que incorpora a latitude e a longitude de um local no nome de cada elemento de uma dimensão. Consulte [Definir camadas de ponto de elemento usando pontos dinâmicos](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

Para definir uma camada de ponto de elemento que faça referência a um arquivo de pesquisa, você deve criar ou já ter disponível o seguinte:

* **Uma dimensão** definido no [!DNL Transformation.cfg] arquivo ou um conjunto de dados de transformação inclui arquivo. Para obter informações sobre arquivos de configuração de transformação, consulte o *Guia de configuração do conjunto de dados*.

* **Um arquivo de pesquisa** contendo os dados utilizados para plotar cada ponto de dados. Esse arquivo deve conter pelo menos três colunas de dados para cada ponto de dados: a chave, a longitude e a latitude. Para obter mais informações sobre o formato necessário do arquivo de pesquisa, consulte [Formato de arquivo de pesquisa do ponto de elemento](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121).

* **Um arquivo de camada** que especifica a localização do arquivo de pesquisa e identifica a dimensão e métrica relacionadas, bem como os nomes de chave, longitude e latitude da coluna no arquivo de pesquisa. Para obter mais informações sobre o formato necessário do arquivo de camada, consulte [Formato de arquivo de camada de ponto de elemento](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>O [!DNL Zip Points.layer] , fornecido com o [!DNL Geography] perfil, é uma camada de ponto de elemento que identifica a variável [!DNL Zipcode.dim] , o [!DNL Sessions.metric] , o [!DNL Zip Points.txt] arquivo de pesquisa e os nomes das colunas chave, longitude, latitude e nome no arquivo de pesquisa.
