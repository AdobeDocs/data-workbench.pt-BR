---
description: As transformações e dimensões usam condições para determinar quando determinadas instruções ou ações se aplicam a campos de log.
title: Sobre condições
uuid: 882fe761-895c-4226-a019-270c50ae6da2
exl-id: 0d44282f-1327-4f11-90fc-7e6a2ef8dc76
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 2%

---

# Sobre condições{#about-conditions}

As transformações e dimensões usam condições para determinar quando determinadas instruções ou ações se aplicam a campos de log.

O parâmetro Condição de entrada de log usa condições para determinar quais entradas de log devem ser incluídas no processo de construção do conjunto de dados. Este apêndice descreve os diferentes tipos de condições disponíveis no servidor do Data Workbench.

Uma condição é incluída em uma das duas categorias:

* **[!DNL Test Operations]:** [!DNL Compare],  [!DNL Not Empty],  [!DNL Range],  [!DNL Regular Expression] e  [!DNL String Match] condições são usadas para testar para estados diferentes nos campos de log disponíveis.

* **[!DNL Boolean Operations]:** As  [!DNL And]condições  [!DNL Or],  [!DNL Neither]  e são usadas para combinar as operações de teste descritas acima. Por exemplo, se você tiver uma condição [!DNL Range] e uma condição [!DNL String Match] que devem ser falsas para tomar a ação apropriada, você faria essas duas operações filho da condição [!DNL Neither]. Observe que a condição [!DNL And] é usada como a raiz de todos os testes de condição no sistema.
