---
description: 'null'
solution: Analytics,Analytics
title: Modificar o parâmetro ExpPartialMatch (opcional)
topic: Data workbench
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 14%

---


# Modificar o parâmetro ExpPartialMatch (opcional){#modifying-the-exppartialmatch-parameter-optional}

Se você quiser habilitar seus experimentos controlados para remapear o site inteiro ou um subdiretório inteiro do site para outro local, você pode definir o parâmetro ExpPartialMatch no [!DNL txlogd.conf] arquivo como &quot;ativado&quot;. O padrão é &quot;off&quot;.

Veja a seguir um exemplo do parâmetro ExpPartialMatch:

[!DNL ExpPartialMatch off]

Tenha muito cuidado ao definir esse parâmetro como &quot;ligado&quot;, pois pode resultar em um remapeamento inadvertido de todo o seu site.
