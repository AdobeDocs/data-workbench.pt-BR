---
description: Uma configuração típica do Site usa cookies para identificar de forma exclusiva os visitantes de seu site e acompanhar seu comportamento ao longo do tempo.
solution: Insight,Analytics
title: Como o Site Identifica Os Visitantes?
topic: Data workbench
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Como o Site Identifica Os Visitantes?{#how-does-site-identify-visitors}

Uma configuração típica do Site usa cookies para identificar de forma exclusiva os visitantes de seu site e acompanhar seu comportamento ao longo do tempo.

A primeira vez que um determinado navegador (considerado um visitante) faz uma solicitação de seu site, [!DNL Sensor] trabalha com o servidor da Web para definir um cookie persistente (por padrão [!DNL cs(cookie)(v1st)]), que é interpretado internamente no sistema como [!DNL x-trackingid]. Este cookie é definido somente uma vez, na primeira solicitação feita ao seu site por esse visitante. Em seguida, ele é coletado desse visitante toda vez que o navegador fizer uma solicitação (página ou solicitação de objeto incorporado) do site no futuro.

A aceitação de um cookie persistente fica à discrição do navegador. Se um usuário optar por bloquear cookies persistentes, suas solicitações de exibição de página ainda serão registradas, mas os dados de medição dessas solicitações não serão correlacionados a um visitante específico ou a suas sessões no site, a menos que você implemente um método alternativo de identificação do visitante, como o uso da transformação Hash nos campos IP e UserAgent.

>[!NOTE]
>
>Os experimentos do site podem ser analisados somente em conjuntos de dados nos quais o único método de identificação de visitante em uso é o método de cookie persistente [!DNL Sensor] definido. Sensores em execução em servidores J2EE (JBoss, Tomcat, WebLogic e WebSphere) não suportam experimentação controlada.

Durante um experimento controlado, os usuários que não aceitam cookies podem ser colocados em diferentes grupos de experimentos de um clique para o seguinte. Isso se torna um problema somente se você executar sua análise de teste com o Filtro de sessão quebrada desativado [!DNL Insight], o que a Adobe não recomenda.

Para obter mais informações sobre o Filtro de sessão quebrada, consulte o * Guia do usuário [!DNL Insight] *.

Se um visitante apagar o cookie durante um experimento, ele receberá um novo cookie e poderá ser atribuído a um grupo diferente. Como a Adobe identifica o visitante como novo, o experimento não é invalidado.
