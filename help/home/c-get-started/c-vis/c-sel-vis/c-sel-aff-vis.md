---
description: Em um espaço de trabalho, uma visualização representa um conjunto de resultados de consulta.
solution: Analytics
title: Entendendo como uma seleção afeta outras visualizações
topic: Data workbench
uuid: d46f4e8d-df6f-4a7f-a796-eb9f11536ae5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Entendendo como uma seleção afeta outras visualizações{#understanding-how-a-selection-affects-other-visualizations}

Em um espaço de trabalho, uma visualização representa um conjunto de resultados de consulta.

Quando você faz uma seleção, o Análise de big data filtra os resultados das consultas que ele usa para produzir as visualizações no espaço de trabalho. O filtro específico varia por visualização.

Os exemplos a seguir ilustram como a Análise de big data aplica uma seleção a três tipos diferentes de visualizações. A revisão desses exemplos ajuda a entender o efeito de filtragem que as seleções têm nas visualizações. Eles também ajudam você a entender como interpretar os resultados que você vê em uma visualização filtrada.

* [Filtragem de uma visualização com uma métrica de sessões](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-7cc06493ecb34cd4a696dbf0f0a7aaef)
* [Filtragem de uma visualização com uma métrica de visitantes](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-97d38c7f03e8457189a9c72d69514ed2)
* [Filtragem de uma visualização com uma métrica Visitantes por sessão](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-f746182311d648dcb98716b0fe846e25)

## Filtragem de uma visualização com uma métrica de sessões {#section-7cc06493ecb34cd4a696dbf0f0a7aaef}

Neste exemplo, o [!DNL /direct.asp/?ldPage=hme] URI na visualização à esquerda está filtrando a métrica para Sessões exibida na visualização à direita.

![](assets/client-vis1.png)

* **Efeito da seleção na consulta:** A Análise de big data filtra as Sessões do URI selecionado. Neste exemplo, a consulta que gera o valor para o [!DNL /pops/disclosure_pop.asp] elemento é filtrada da seguinte maneira:

   ```
   Sessions[ URI="/pops/disclosure_pop.asp" AND URI="/direct.asp
   /?ldPage=hme"] by Page View by Session
   ```

* **Interpretação da visualização:** A visualização filtrada representa o número de Sessões que incluem os URIs listados na visualização e [!DNL /direct.asp/?ldPage=hme]. Este exemplo mostra que houve 1.113 sessões durante as quais os visitantes visualizaram a [!DNL /pops/disclosure_pop.asp] página e [!DNL /direct.asp/?ldPage=hme] a mesma sessão.

## Filtragem de uma visualização com uma métrica de visitantes {#section-97d38c7f03e8457189a9c72d69514ed2}

Neste exemplo, o [!DNL /direct.asp/?ldPage=home] URI na visualização à esquerda está filtrando a métrica para Visitantes na visualização à direita.

![](assets/client-vis2.png)

* **Efeito da seleção na consulta:** A Análise de big data filtra os Visitantes para o URI selecionado. Neste exemplo, a consulta que gera o valor para o [!DNL /pops/disclosure_pop.asp] URI é filtrada da seguinte maneira:

   ```
   Visitors[ URI="/pops/disclosure_pop.asp" by Page View by Visitor 
     AND URI="/direct.asp/?ldPage=hme" by Page View by Visitor ]
   ```

* **Interpretação da visualização:** A visualização filtrada descreve os Visitantes que visualizaram os URIs listados na visualização e [!DNL /direct.asp/?ldPage=hme] (embora não necessariamente durante a mesma sessão). O exemplo acima mostra que 2.041 visitantes visualizaram tanto [!DNL /pops/disclosure_pop.asp] quanto [!DNL /direct.asp/?ldPage=hme].

## Filtragem de uma visualização com uma métrica Visitantes por sessão {#section-f746182311d648dcb98716b0fe846e25}

Neste exemplo, o [!DNL /direct.asp/?ldPage=hme] URI na visualização à esquerda está filtrando a métrica para visitante por sessão na visualização à direita.

![](assets/client-vis3.png)

* **Efeito da seleção na consulta:** A Análise de big data filtra os Visitantes por sessão para o URI selecionado. Por exemplo, a consulta que gera o valor para o [!DNL /pops/disclosure_pop.asp] URI é filtrada da seguinte maneira:

   ```
   Visitors[ ( URI="/pops/disclosure_pop.asp" by Page View 
     AND URI="/direct.asp/?ldPage=hme" by Page View ) by Session ]
   ```

* **Interpretação da visualização:** A visualização filtrada descreve os Visitantes que visualizaram os dois URIs listados na visualização e [!DNL /direct.asp/?ldPage=hme] durante a mesma sessão. Este exemplo mostra que 1.069 visitantes visualizaram tanto [!DNL /pops/disclosure_pop.asp] quanto [!DNL /direct.asp/?ldPage=hme] durante uma única sessão.

