---
description: Um servidor do Data Workbench se torna ciente de uma fonte de dados, como um Sensor, quando recebe dados dessa fonte.
title: Compreender o tempo "A partir de"
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# Compreender o tempo &quot;A partir de&quot;{#understanding-as-of-time}

Um servidor do Data Workbench se torna ciente de uma fonte de dados, como um Sensor, quando recebe dados dessa fonte.

A partir do tempo é uma garantia de que o [!DNL data workbench server] tenha dados para todas as fontes de dados das quais tem conhecimento.

Digamos que temos um conjunto de três [!DNL Sensors] que enviam dados para um [!DNL data workbench server]: WEB1, WEB2 e WEB3. Como o [!DNL data workbench server] recebe e processa os dados desses [!DNL Sensors], ele automaticamente espera dados de cada uma dessas fontes. A Data de início indica a última vez que o [!DNL data workbench server] recebeu dados de todas essas três fontes.

Em termos práticos, o [!DNL data workbench server] só se preocupa com a Hora de início e não com o que pode ser chamado de &quot;hora da parede&quot;, ou com o horário de um relógio na parede. O [!DNL data workbench server] conhece o horário somente como a Data de início. Isso é particularmente importante para fins de relatório, pois garante que os relatórios sempre sejam executados com base no tempo de início, o que garante que os relatórios com apenas dados parciais nunca possam ser enviados para os usuários finais do sistema.

O [!DNL data workbench server] usa dados enviados do transmissor para fornecer a Data de início, sejam dados reais coletados do site ou pulsações periódicas enviadas pelo [!DNL Sensors]. Essas pulsações servem dois propósitos:

1. Para manter uma conexão persistente HTTP/1.1 aberta entre [!DNL Sensor] e [!DNL data workbench server].

1. Para manter o tempo de Ativação atualizado no caso de o tráfego do site não estar sendo coletado e enviado para o [!DNL data workbench server].
