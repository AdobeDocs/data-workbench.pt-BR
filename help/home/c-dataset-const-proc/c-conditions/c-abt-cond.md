---
description: As transformações e dimensões usam condições para determinar quando determinadas instruções ou ações se aplicam a campos de log.
title: Sobre condições
uuid: 882fe761-895c-4226-a019-270c50ae6da2
exl-id: 0d44282f-1327-4f11-90fc-7e6a2ef8dc76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 2%

---

# Sobre condições{#about-conditions}

{{eol}}

As transformações e dimensões usam condições para determinar quando determinadas instruções ou ações se aplicam a campos de log.

O parâmetro Condição de entrada de log usa condições para determinar quais entradas de log devem ser incluídas no processo de construção do conjunto de dados. Este apêndice descreve os diferentes tipos de condições disponíveis no servidor do Data Workbench.

Uma condição é incluída em uma das duas categorias:

* **[!DNL Test Operations]:** [!DNL Compare], [!DNL Not Empty], [!DNL Range], [!DNL Regular Expression]e [!DNL String Match] são usadas para testar diferentes estados nos campos de log disponíveis.

* **[!DNL Boolean Operations]:** O [!DNL And], [!DNL Or]e [!DNL Neither] são utilizadas condições para combinar as operações de ensaio acima descritas. Por exemplo, se você tiver uma [!DNL Range] e uma [!DNL String Match] condição que deve ser falsa para tomar a ação apropriada, você tornaria essas duas operações filho da [!DNL Neither] condição. Observe que a variável [!DNL And] é usada como a raiz de todos os testes de condição no sistema.
