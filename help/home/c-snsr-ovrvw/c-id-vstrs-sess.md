---
description: Ao coletar dados do evento de um servidor da Web, o Sensor define automaticamente um cookie persistente para cada visitante que contém um identificador aleatório pequeno, sem capturar qualquer informação de identificação pessoal.
solution: Analytics
title: Como o sensor identifica visitantes e sessões?
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 6%

---


# Como o sensor identifica visitantes e sessões?{#how-does-sensor-identify-visitors-and-sessions}

Ao coletar dados do evento de um servidor da Web, o Sensor define automaticamente um cookie persistente para cada visitante que contém um identificador aleatório pequeno, sem capturar qualquer informação de identificação pessoal.

Este cookie Adobe é usado para identificar o visitante exclusivo e todas as sessões relacionadas.

Por padrão, [!DNL Sensor] captura todos os campos do Formato de arquivo de log estendido W3C de cada cabeçalho HTTP, mas você pode configurar [!DNL Sensor] para capturar qualquer cabeçalho transmitido entre o cliente e o servidor. Para obter informações sobre os campos de dados do evento coletados [!DNL Sensor] em [!DNL .vsl] arquivos, consulte Campos [de registro de dados do](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)Evento.

Os navegadores de alguns visitantes não armazenam cookies persistentemente e um número muito pequeno de navegadores de visitantes não aceita cookies (mesmo cookies de sessão). Mesmo que representem apenas uma fração do tráfego total de um site, eles podem resultar em um significativo erro de contagem se cada visualização de página por esse visitante for contada incorretamente como uma sessão inteira, como é feito por algum software de análise de arquivo de log. O Adobe soluciona esse problema ao permitir a análise de visitantes com e sem o uso de cookies.

Para obter mais informações sobre o Filtro de sessões quebradas, consulte o Guia *do sensor de* Data Workbench.
