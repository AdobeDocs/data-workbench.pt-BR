---
description: As transformações e dimensões usam condições para determinar quando determinadas instruções ou ações se aplicam aos campos de log.
solution: Analytics
title: Sobre condições
topic: Data workbench
uuid: 882fe761-895c-4226-a019-270c50ae6da2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sobre condições{#about-conditions}

As transformações e dimensões usam condições para determinar quando determinadas instruções ou ações se aplicam aos campos de log.

O parâmetro Condição de entrada do log usa condições para determinar quais entradas de log devem ser incluídas no processo de construção do conjunto de dados. Este apêndice descreve os diferentes tipos de condições disponíveis no servidor de análise de big data.

Uma condição se enquadra em uma das duas categorias:

* **[!DNL Test Operations]:**As condições[!DNL Compare],[!DNL Not Empty],[!DNL Range],[!DNL Regular Expression]e[!DNL String Match]são usadas para testar diferentes estados nos campos de log disponíveis.

* **[!DNL Boolean Operations]:**As condições[!DNL And],[!DNL Or]e[!DNL Neither]são utilizadas para combinar as operações de ensaio descritas acima. Por exemplo, se você tem uma[!DNL Range]condição e uma[!DNL String Match]condição que devem ser ambas falsas para tomar a ação apropriada, você tornaria essas duas operações secundárias da[!DNL Neither]condição. Observe que a[!DNL And]condição é usada como a raiz de todos os testes de condição no sistema.

