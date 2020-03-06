---
description: 'null'
solution: Insight,Analytics
title: Modificando o parâmetro ExpPartialMatch (Opcional)
topic: Data workbench
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modificando o parâmetro ExpPartialMatch (Opcional){#modifying-the-exppartialmatch-parameter-optional}

Se você quiser ativar seus experimentos controlados para remapear todo o site ou um subdiretório inteiro do site para outro local, você pode definir o parâmetro ExpPartialMatch no [!DNL txlogd.conf] arquivo como &quot;ativado&quot;. O padrão é &quot;off&quot;.

Veja a seguir um exemplo do parâmetro ExpPartialMatch:

[!DNL ExpPartialMatch off]

Tenha muito cuidado ao definir esse parâmetro como &quot;ligado&quot;, pois pode resultar em um remapeamento inadvertido de todo o seu site.
