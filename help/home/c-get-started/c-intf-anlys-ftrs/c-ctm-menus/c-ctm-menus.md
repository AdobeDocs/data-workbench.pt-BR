---
description: Você pode personalizar a aparência dos menus, incluindo o menu da janela do espaço de trabalho (acessado clicando com o botão direito do mouse em qualquer espaço de trabalho) e os menus que listam métricas, dimensões e camadas de mapa.
title: Personalizar um menu
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
exl-id: 7a377d9c-d339-43d8-a71a-a322416b2e60
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 2%

---

# Personalizar um menu{#customize-a-menu}

Você pode personalizar a aparência dos menus, incluindo o menu da janela do espaço de trabalho (acessado clicando com o botão direito do mouse em qualquer espaço de trabalho) e os menus que listam métricas, dimensões e camadas de mapa.

A hierarquia de qualquer menu reflete a estrutura de seu diretório no [!DNL Profile Manager]. Por exemplo, o menu da janela do espaço de trabalho espelha a estrutura do diretório Menu e o menu de métricas espelha a estrutura do diretório Métricas . Para qualquer menu, o diretório correspondente pode conter os seguintes itens:

* **Arquivos:** esses arquivos representam as visualizações, legendas, anotações, interfaces administrativas, métricas, dimensões ou camadas de mapa que podem ser abertas clicando no item de menu correspondente.
* **Um  [!DNL order.txt] arquivo:** esse arquivo especifica em qual ordem o menu exibe seus itens.
* **Subdiretórios:** cada subdiretório representa um submenu. Cada subdiretório pode conter seus próprios arquivos, subdiretórios e arquivos [!DNL order.txt].

Por exemplo, o menu [!DNL Add Legend] contém os itens de menu Métrica, Cor, Valor e Confiança, nessa ordem. Em comparação, o diretório Menu\Adicionar Legenda no [!DNL Profile Manager] contém os arquivos [!DNL Color.vw], [!DNL Confidence.vw], [!DNL Metric.vw] e [!DNL Value.vw] em ordem alfabética, bem como um arquivo [!DNL order.txt] para controlar a ordem dos outros arquivos.
