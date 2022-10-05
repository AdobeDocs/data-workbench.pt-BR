---
description: Verifique se o transmissor está sendo executado configurando alertas, verificando o status do sistema do Sensor e muito mais.
title: Confirmar se o transmissor de dados está em execução
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
exl-id: 10ba704e-85be-425f-8a5d-9429100f367d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---

# Confirmar se o transmissor de dados está em execução{#confirming-that-the-data-transmitter-is-running}

{{eol}}

Verifique se o transmissor está sendo executado configurando alertas, verificando o status do sistema do Sensor e muito mais.

**Frequência recomendada:** A cada 5-10 minutos

* [Verifique se o processo do transmissor está em execução.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Configurar alertas administrativos no servidor Insight.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [Verifique o status do sistema do sensor.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## Verificando o processo do transmissor {#section-79806fa3b7034a8eaf571a66e24874d7}

Uma maneira de verificar se o transmissor está em execução é verificar se a variável [!DNL Sensor] o processo do transmissor está em execução em cada servidor da Web em que um [!DNL Sensor] está instalada. O processo do transmissor aparece como &quot;txlogd&quot; na lista de processos do servidor da Web. Você pode executar essa verificação usando uma ferramenta de monitoramento de sistema.

## Configuração de alertas administrativos no servidor do Data Workbench {#section-d98e0f18b8fb45a78419fe75610a3b1e}

Outra maneira de verificar se o transmissor está em execução é configurar alertas administrativos automatizados no [!DNL data workbench server]. Quando alertas administrativos tiverem sido configurados, a variável [!DNL data workbench server] gera um alerta de email quando não recebeu dados de um [!DNL Sensor] no período especificado no [!DNL Sensor] Tempo limite do alerta (min) no [!DNL data workbench server’s] [!DNL Administrative Alerts.cfg] arquivo. Para obter mais informações sobre como configurar alertas administrativos, consulte o *Guia de Instalação e Administração de Produtos para Servidores*.

## Verificando o status do sistema do sensor {#section-de9d7e359242487a9fbead4ed65aebbc}

Outra maneira de verificar se o transmissor está em execução é verificar manualmente a função [!DNL Servers Manager] no Data Workbench.

**Para exibir o[!DNL Servers Manager]**

* No Data Workbench, clique com o botão direito do mouse em um espaço de trabalho, clique em **[!UICONTROL Admin]**, em seguida em [!DNL Manage], clique em **[!UICONTROL Servers]**.

Se o ícone de um [!DNL Sensor] for verde, o transmissor estará em execução.

Para obter mais informações sobre o [!DNL Servers Manager], consulte o capítulo Interfaces administrativas do *Data Workbench [!DNL Sensor] Guia*.
