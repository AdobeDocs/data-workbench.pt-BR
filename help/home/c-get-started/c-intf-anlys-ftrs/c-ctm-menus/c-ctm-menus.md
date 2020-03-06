---
description: Você pode personalizar a aparência dos menus, incluindo o menu da janela do espaço de trabalho (acessado clicando com o botão direito do mouse em qualquer espaço de trabalho) e os menus que listam métricas, dimensões e camadas de mapa.
solution: Analytics
title: Personalizar um menu
topic: Data workbench
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Personalizar um menu{#customize-a-menu}

Você pode personalizar a aparência dos menus, incluindo o menu da janela do espaço de trabalho (acessado clicando com o botão direito do mouse em qualquer espaço de trabalho) e os menus que listam métricas, dimensões e camadas de mapa.

A hierarquia de qualquer menu reflete a estrutura de seu diretório no [!DNL Profile Manager]. Por exemplo, o menu da janela do espaço de trabalho reflete a estrutura do diretório Menu e o menu de métricas reflete a estrutura do diretório Métricas. Para qualquer menu, o diretório correspondente pode conter os seguintes itens:

* **Arquivos:** Esses arquivos representam as visualizações, legendas, anotações, interfaces administrativas, métricas, dimensões ou camadas de mapa que podem ser abertas ao clicar no item de menu correspondente.
* **Um[!DNL order.txt]arquivo:** Esse arquivo especifica em qual ordem o menu exibe seus itens.
* **Subdiretórios:** Cada subdiretório representa um submenu. Cada subdiretório pode conter seus próprios arquivos, subdiretórios e [!DNL order.txt] arquivos.

Por exemplo, o [!DNL Add Legend] menu contém os itens de menu Métrica, Cor, Valor e Confiança, nessa ordem. Em comparação, o diretório Menu\Adicionar legenda no [!DNL Profile Manager] contém os arquivos [!DNL Color.vw], [!DNL Confidence.vw], [!DNL Metric.vw]e [!DNL Value.vw] em ordem alfabética, bem como um [!DNL order.txt] arquivo para controlar a ordem dos outros arquivos.
