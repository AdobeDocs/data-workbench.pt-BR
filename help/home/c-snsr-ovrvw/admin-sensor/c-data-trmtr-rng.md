---
description: Verifique se o transmissor está sendo executado configurando alertas, verificando o status do sistema do Sensor e muito mais.
title: Confirmar se o transmissor de dados está em execução
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
exl-id: 10ba704e-85be-425f-8a5d-9429100f367d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---

# Confirmar se o transmissor de dados está em execução{#confirming-that-the-data-transmitter-is-running}

Verifique se o transmissor está sendo executado configurando alertas, verificando o status do sistema do Sensor e muito mais.

**Frequência recomendada:** a cada 5-10 minutos

* [Verifique se o processo do transmissor está em execução.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Configurar alertas administrativos no servidor Insight.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [Verifique o status do sistema do sensor.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## Verificando o processo do transmissor {#section-79806fa3b7034a8eaf571a66e24874d7}

Uma maneira de verificar se o transmissor está em execução é verificar se o processo do transmissor [!DNL Sensor] está em execução em cada servidor da Web onde uma instância [!DNL Sensor] está instalada. O processo do transmissor aparece como &quot;txlogd&quot; na lista de processos do servidor da Web. Você pode executar essa verificação usando uma ferramenta de monitoramento de sistema.

## Configuração de alertas administrativos no servidor do Data Workbench {#section-d98e0f18b8fb45a78419fe75610a3b1e}

Outra maneira de verificar se o transmissor está em execução é configurar alertas administrativos automatizados no [!DNL data workbench server]. Quando alertas administrativos foram configurados, o [!DNL data workbench server] gera um alerta de email quando não recebeu dados de um [!DNL Sensor] configurado e conectado anteriormente dentro do período especificado no parâmetro [!DNL Sensor] Tempo limite de alerta (min) no arquivo [!DNL data workbench server’s] [!DNL Administrative Alerts.cfg]. Para obter mais informações sobre como configurar alertas administrativos, consulte o *Server Products Installation and Administration Guide*.

## Verificando o status do sistema do sensor {#section-de9d7e359242487a9fbead4ed65aebbc}

Outra maneira de verificar se o transmissor está em execução é verificar manualmente o [!DNL Servers Manager] no Data Workbench.

**Para exibir o[!DNL Servers Manager]**

* No Data Workbench, clique com o botão direito do mouse em um espaço de trabalho, clique em **[!UICONTROL Admin]** e, em [!DNL Manage], clique em **[!UICONTROL Servers]**.

Se o ícone de um [!DNL Sensor] estiver verde, o transmissor estará em execução.

Para obter mais informações sobre [!DNL Servers Manager], consulte o capítulo Interfaces Administrativas do *Guia [!DNL Sensor] de Data Workbench*.
