---
description: Ao coletar dados de eventos de um servidor da Web, o Sensor define automaticamente um cookie persistente para cada visitante que contém um pequeno identificador aleatório, sem capturar qualquer informação de identificação pessoal.
solution: Insight
title: Como o sensor identifica visitantes e sessões?
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Como o sensor identifica visitantes e sessões?{#how-does-sensor-identify-visitors-and-sessions}

Ao coletar dados de eventos de um servidor da Web, o Sensor define automaticamente um cookie persistente para cada visitante que contém um pequeno identificador aleatório, sem capturar qualquer informação de identificação pessoal.

Este cookie da Adobe é usado para identificar o visitante único e todas as sessões relacionadas.

Por padrão, [!DNL Sensor] captura todos os campos do Formato de arquivo de log estendido W3C de cada cabeçalho HTTP, mas você pode configurar [!DNL Sensor] para capturar qualquer cabeçalho transmitido entre o cliente e o servidor. Para obter informações sobre os campos de dados do evento coletados [!DNL Sensor] em [!DNL .vsl] arquivos, consulte Campos [de registro de dados do](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)evento.

Os navegadores de alguns visitantes não armazenam cookies persistentemente, e um número muito pequeno de navegadores de visitantes não aceita cookies (mesmo cookies de sessão). Mesmo que representem apenas uma fração do tráfego total de um site, eles podem resultar em um significativo erro de contagem se cada exibição de página por um visitante for contada incorretamente como uma sessão inteira, como é feito por algum software de análise de arquivo de log. A Adobe soluciona esse problema ao permitir que você analise os visitantes com e sem usar cookies.

Para obter mais informações sobre o Filtro de sessões quebradas, consulte o Guia ** do sensor da análise de big data.
