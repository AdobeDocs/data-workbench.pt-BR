---
description: Ao coletar dados de evento de um servidor da Web, o Sensor define automaticamente um cookie persistente para cada visitante contendo um pequeno identificador aleatório, sem capturar informações de identificação pessoal.
title: Como o sensor identifica visitantes e sessões?
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
exl-id: f5781ed6-ac83-4a8e-b412-8966f8c39c41
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 6%

---

# Como o sensor identifica visitantes e sessões?{#how-does-sensor-identify-visitors-and-sessions}

Ao coletar dados de evento de um servidor da Web, o Sensor define automaticamente um cookie persistente para cada visitante contendo um pequeno identificador aleatório, sem capturar informações de identificação pessoal.

Este cookie de Adobe é usado para identificar o visitante exclusivo e todas as sessões relacionadas.

Por padrão, [!DNL Sensor] captura todos os campos W3C Extended Log File Format de cada cabeçalho HTTP, mas você pode configurar [!DNL Sensor] para capturar qualquer cabeçalho que seja transmitido entre o cliente e o servidor. Para obter informações sobre os campos de dados do evento coletados por [!DNL Sensor] em arquivos [!DNL .vsl], consulte [Campos de registro de dados do evento](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).

Os navegadores de alguns visitantes não armazenam cookies persistentemente e um número muito pequeno de navegadores de visitantes não aceita cookies (mesmo cookies de sessão). Mesmo que representem apenas uma fração do tráfego total de um site, eles podem resultar em inúmeros erros de contagem se cada exibição de página por um visitante for contada incorretamente como uma sessão inteira, como é feito por algum software de análise de arquivo de log. O Adobe soluciona esse problema ao permitir que você analise os visitantes com e sem usar cookies.

Para obter mais informações sobre o Filtro de sessões quebradas, consulte o *Guia do sensor de Data Workbench*.
