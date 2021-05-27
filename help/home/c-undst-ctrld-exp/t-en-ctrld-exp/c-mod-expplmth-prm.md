---
description: Modificar o parâmetro ExpPartialMatch (opcional)
title: Modificar o parâmetro ExpPartialMatch (opcional)
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
exl-id: 8ad45368-85a4-4865-b66b-52c29c28799c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 18%

---

# Modificar o parâmetro ExpPartialMatch (opcional){#modifying-the-exppartialmatch-parameter-optional}

Se quiser permitir que seus experimentos controlados remapeiem todo o site ou um subdiretório inteiro do site para outro local, você pode definir o parâmetro ExpPartialMatch no arquivo [!DNL txlogd.conf] como &quot;ativado&quot;. O padrão é &quot;off&quot;.

A seguir, um exemplo do parâmetro ExpPartialMatch :

[!DNL ExpPartialMatch off]

Tenha muito cuidado ao definir esse parâmetro como &quot;ativado&quot;, pois isso pode resultar em um remapeamento inadvertido de todo o seu site.
