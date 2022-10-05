---
description: Um servidor do Data Workbench se torna ciente de uma fonte de dados, como um Sensor, quando recebe dados dessa fonte.
title: Compreender o tempo "A partir de"
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# Compreender o tempo &quot;A partir de&quot;{#understanding-as-of-time}

{{eol}}

Um servidor do Data Workbench se torna ciente de uma fonte de dados, como um Sensor, quando recebe dados dessa fonte.

O tempo de permanência é uma garantia de que a variável [!DNL data workbench server] tem dados para todas as fontes de dados de que tem conhecimento.

Digamos que temos um conjunto de três [!DNL Sensors] que enviam dados para um [!DNL data workbench server]: WEB1, WEB2 e WEB3. Como [!DNL data workbench server] recebe e processa os dados desses [!DNL Sensors], é necessário esperar automaticamente dados de cada uma dessas fontes. O tempo de início indica a última vez que a variável [!DNL data workbench server] recebeu dados das três fontes.

Em termos práticos, a variável [!DNL data workbench server] só se preocupa com a hora de início e não com o que pode ser chamado de &quot;hora da parede&quot;, ou com o tempo de um relógio na parede. O [!DNL data workbench server] O conhece o horário somente como a Data de início. Isso é particularmente importante para fins de relatório, pois garante que os relatórios sempre sejam executados com base no tempo de início, o que garante que os relatórios com apenas dados parciais nunca possam ser enviados para os usuários finais do sistema.

O [!DNL data workbench server] O usa dados enviados do transmissor para fornecer a data de início, sejam dados reais coletados do site ou pulsações periódicas enviadas por seu [!DNL Sensors]. Essas pulsações servem dois propósitos:

1. Para manter uma conexão persistente HTTP/1.1 aberta entre as [!DNL Sensor] e [!DNL data workbench server].

1. Para manter o tempo de Ativação atualizado caso o tráfego do site não esteja sendo coletado e enviado para o [!DNL data workbench server].
