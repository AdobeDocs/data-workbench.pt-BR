---
description: Uma configuração típica do Site usa cookies para identificar de forma exclusiva os visitantes do site e rastrear o comportamento deles ao longo do tempo.
solution: Analytics
title: Como o site identifica visitantes?
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
exl-id: 2783ee11-6d6a-463d-86b5-dd63e490201f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---

# Como o site identifica visitantes?{#how-does-site-identify-visitors}

{{eol}}

Uma configuração típica do Site usa cookies para identificar de forma exclusiva os visitantes do site e rastrear o comportamento deles ao longo do tempo.

A primeira vez que um determinado navegador (considerado um visitante) faz uma solicitação de seu site, [!DNL Sensor] O funciona com o servidor da Web para definir um cookie persistente (por padrão) [!DNL cs(cookie)(v1st)]), que é interpretada internamente no sistema como [!DNL x-trackingid]. Este cookie é definido apenas uma vez, na primeira solicitação feita ao seu site por esse visitante. Ele é coletado desse visitante sempre que o navegador fizer uma solicitação (página ou solicitação de objeto incorporado) do site no futuro.

Aceitar um cookie persistente depende do navegador. Se um usuário optar por bloquear cookies persistentes, suas solicitações de exibição de página ainda serão registradas, mas os dados de medição dessas solicitações não serão correlacionados a um visitante específico ou a suas sessões no site, a menos que você implemente um método alternativo de identificação do visitante, como o uso da transformação de Hash nos campos IP e UserAgent.

>[!NOTE]
>
>Experimentos no site podem ser analisados somente em conjuntos de dados em que o único método de identificação de visitante em uso é o [!DNL Sensor] definir método de cookie persistente. Sensores em execução em servidores J2EE (JBoss, Tomcat, WebLogic e WebSphere) não suportam experimentação controlada.

Durante um experimento controlado, os usuários que não aceitam cookies podem ser colocados em diferentes grupos de experimentos de um clique para o seguinte. Isso se torna um problema somente se você executar a análise de teste com o Filtro de Sessão Quebrada desativado em [!DNL Insight], que Adobe não é recomendado.

Para obter mais informações sobre o Filtro de Sessão Quebrado, consulte o * [!DNL Insight] Guia do usuário*.

Se um visitante limpar o cookie durante uma experiência, ele recebe um novo cookie e pode ser atribuído a um grupo diferente. Como o Adobe identifica o visitante como novo, a experiência não é invalidada.
