---
description: Um servidor de análise de big data se torna ciente de uma fonte de dados, como um sensor, quando recebe dados dessa fonte.
solution: Analytics
title: Compreender o tempo "A partir de"
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---


# Compreender o tempo &quot;A partir de&quot;{#understanding-as-of-time}

Um servidor de análise de big data se torna ciente de uma fonte de dados, como um sensor, quando recebe dados dessa fonte.

A data de início é uma garantia de que a empresa [!DNL data workbench server] tem dados para todas as fontes de dados de que tem conhecimento.

Digamos que temos um conjunto de três [!DNL Sensors] que enviam dados para um [!DNL data workbench server]: WEB1, WEB2 e WEB3. À medida que [!DNL data workbench server] recebe e processa os dados dessas [!DNL Sensors], ele automaticamente chega a esperar dados de cada uma dessas fontes. A data de início indica a última vez que os dados [!DNL data workbench server] recebidos de todas essas três fontes.

Em termos práticos, o [!DNL data workbench server] único problema é a Hora de Chegada e não o que pode ser chamado de &quot;Hora da Parede&quot;, ou o tempo de um relógio na parede. O tempo só [!DNL data workbench server] conhece a hora como a de cada vez. Isso é particularmente importante para fins de relatórios, pois garante que os relatórios sejam sempre executados com base no tempo de início, garantindo que os relatórios com apenas dados parciais nunca possam ser enviados para os usuários finais do sistema.

O [!DNL data workbench server] usa dados enviados pelo transmissor para fornecer a Data de início, sejam dados reais coletados do site ou pulsações periódicas enviadas por seu [!DNL Sensors]. Essas pulsações servem dois propósitos:

1. Para manter uma conexão persistente HTTP/1.1 aberta entre o [!DNL Sensor] e o [!DNL data workbench server].

1. Para manter o tempo de Ativação atualizado no evento, o tráfego do site não está sendo coletado e enviado para o [!DNL data workbench server].

