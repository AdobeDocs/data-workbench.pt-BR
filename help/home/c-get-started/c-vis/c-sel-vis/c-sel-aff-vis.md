---
description: Em um espaço de trabalho, uma visualização representa um conjunto de resultados de query.
title: Entender como uma seleção afeta outras visualizações
uuid: d46f4e8d-df6f-4a7f-a796-eb9f11536ae5
exl-id: 7756646b-9309-41aa-a098-8988f6c065c8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 3%

---

# Entender como uma seleção afeta outras visualizações{#understanding-how-a-selection-affects-other-visualizations}

{{eol}}

Em um espaço de trabalho, uma visualização representa um conjunto de resultados de query.

Quando você faz uma seleção, a Data Workbench filtra os resultados das consultas que usa para produzir as visualizações no espaço de trabalho. O filtro específico varia de acordo com a visualização.

Os exemplos a seguir ilustram como a Data Workbench aplica uma seleção a três tipos diferentes de visualizações. A revisão desses exemplos ajuda você a entender o efeito de filtragem que as seleções têm nas visualizações. Eles também ajudam você a entender como interpretar os resultados que você vê em uma visualização filtrada.

* [Filtragem de uma visualização com uma métrica de sessões](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-7cc06493ecb34cd4a696dbf0f0a7aaef)
* [Filtragem de uma visualização com uma métrica de visitantes](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-97d38c7f03e8457189a9c72d69514ed2)
* [Filtragem de uma visualização com uma métrica de visitantes por sessão](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-f746182311d648dcb98716b0fe846e25)

## Filtragem de uma visualização com uma métrica de sessões {#section-7cc06493ecb34cd4a696dbf0f0a7aaef}

Neste exemplo, a variável [!DNL /direct.asp/?ldPage=hme] O URI na visualização à esquerda está filtrando a métrica para Sessões exibidas na visualização à direita.

![](assets/client-vis1.png)

* **Efeito da seleção na consulta:** A Data Workbench filtra as Sessões do URI selecionado. Neste exemplo, a query que gera o valor para a variável [!DNL /pops/disclosure_pop.asp] O elemento é filtrado da seguinte maneira:

   ```
   Sessions[ URI="/pops/disclosure_pop.asp" AND URI="/direct.asp
   /?ldPage=hme"] by Page View by Session
   ```

* **Interpretação da visualização:** A visualização filtrada representa o número de Sessões que incluem os URIs listados na visualização e [!DNL /direct.asp/?ldPage=hme]. Este exemplo mostra que havia 1.113 sessões durante as quais os visitantes visualizaram ambos [!DNL /pops/disclosure_pop.asp] página e [!DNL /direct.asp/?ldPage=hme] na mesma sessão.

## Filtragem de uma visualização com uma métrica de visitantes {#section-97d38c7f03e8457189a9c72d69514ed2}

Neste exemplo, a variável [!DNL /direct.asp/?ldPage=home] O URI na visualização à esquerda está filtrando a métrica para Visitantes na visualização à direita.

![](assets/client-vis2.png)

* **Efeito da seleção na consulta:** A Data Workbench filtra os Visitantes do URI selecionado. Neste exemplo, a query que gera o valor para a variável [!DNL /pops/disclosure_pop.asp] O URI é filtrado da seguinte maneira:

   ```
   Visitors[ URI="/pops/disclosure_pop.asp" by Page View by Visitor 
     AND URI="/direct.asp/?ldPage=hme" by Page View by Visitor ]
   ```

* **Interpretação da visualização:** A visualização filtrada descreve os Visitantes que visualizaram os URIs listados na visualização e [!DNL /direct.asp/?ldPage=hme] (embora não necessariamente durante a mesma sessão). O exemplo acima mostra que 2.041 visitantes visualizaram ambos [!DNL /pops/disclosure_pop.asp] e [!DNL /direct.asp/?ldPage=hme].

## Filtragem de uma visualização com uma métrica de visitantes por sessão {#section-f746182311d648dcb98716b0fe846e25}

Neste exemplo, a variável [!DNL /direct.asp/?ldPage=hme] O URI na visualização à esquerda está filtrando a métrica visitante por sessão na visualização à direita.

![](assets/client-vis3.png)

* **Efeito da seleção na consulta:** A Data Workbench filtra os Visitantes por Sessão para o URI selecionado. Por exemplo, a query que gera o valor para a variável [!DNL /pops/disclosure_pop.asp] O URI é filtrado da seguinte maneira:

   ```
   Visitors[ ( URI="/pops/disclosure_pop.asp" by Page View 
     AND URI="/direct.asp/?ldPage=hme" by Page View ) by Session ]
   ```

* **Interpretação da visualização:** A visualização filtrada descreve os Visitantes que visualizaram ambos os URIs listados na visualização e [!DNL /direct.asp/?ldPage=hme] durante a mesma sessão. Este exemplo mostra que 1.069 visitantes visualizaram ambos [!DNL /pops/disclosure_pop.asp] e [!DNL /direct.asp/?ldPage=hme] durante uma única sessão.
