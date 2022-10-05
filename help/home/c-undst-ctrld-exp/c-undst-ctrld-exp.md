---
description: Experimentos controlados são testes que permitem comparar resultados obtidos de um grupo de amostras experimental com os de um grupo de controle padrão.
solution: Analytics
title: Data Workbench experimentos controlados
uuid: 5fce2d9e-4975-44e4-a7c0-11064d8d28b4
exl-id: 40bcf6a4-c722-427c-81ac-45dec1eae0b5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# Data Workbench experimentos controlados{#data-workbench-controlled-experiments}

{{eol}}

Experimentos controlados são testes que permitem comparar resultados obtidos de um grupo de amostras experimental com os de um grupo de controle padrão.

O Site permite que você implemente, meça e analise experimentos controlados e seus resultados, conforme eles se relacionam a diferentes aspectos de seu site. Isso permite que você teste hipóteses relacionadas à melhoria do desempenho do site antes de gastar tempo significativo ou dinheiro implementando totalmente as alterações propostas.

>[!NOTE]
>
>Experimentos no site podem ser analisados somente em conjuntos de dados em que o único método de identificação de visitante em uso é o [!DNL Sensor] definir método de cookie persistente. Sensores em execução em servidores J2EE (JBoss, Tomcat, WebLogic e WebSphere) não suportam experimentação controlada. Para obter mais informações, consulte a seguinte seção.

Usando o Site, é possível implementar experimentos A/B, A/B/A e multivariados controlados para coletar dados de teste suficientes para fornecer dados estatisticamente precisos para uma avaliação detalhada da hipótese, sem afetar o desempenho atual do site.
