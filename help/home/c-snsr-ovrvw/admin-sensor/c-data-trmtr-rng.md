---
description: Verifique se o transmissor está sendo executado configurando alertas, verificando o status do sistema do Sensor e muito mais.
solution: Insight
title: Confirmando se o Transmissor de Dados está em execução
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Confirmando se o Transmissor de Dados está em execução{#confirming-that-the-data-transmitter-is-running}

Verifique se o transmissor está sendo executado configurando alertas, verificando o status do sistema do Sensor e muito mais.

**Frequência recomendada:** A cada 5 a 10 minutos

* [Verifique se o processo do transmissor está em execução.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Configure alertas administrativos no Insight Server.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [Verifique o status do sistema do sensor.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## Verificando o processo de transmissor {#section-79806fa3b7034a8eaf571a66e24874d7}

Uma maneira de verificar se o transmissor está em execução é verificar se o processo do [!DNL Sensor] transmissor está em execução em cada servidor Web onde uma [!DNL Sensor] instância está instalada. O processo do transmissor aparece como &quot;txlogd&quot; na lista de processos do servidor da Web. É possível realizar essa verificação usando uma ferramenta de monitoramento do sistema.

## Configurando Alertas Administrativos no Servidor do Análise de big data {#section-d98e0f18b8fb45a78419fe75610a3b1e}

Outra maneira de verificar se o transmissor está em execução é configurar alertas administrativos automatizados no [!DNL data workbench server]. Quando os alertas administrativos são configurados, o [!DNL data workbench server] gera um alerta de email quando não recebeu dados de um configurado e conectado anteriormente [!DNL Sensor] dentro do período especificado no parâmetro Tempo limite de [!DNL Sensor] alerta (min) no [!DNL data workbench server’s] [!DNL Administrative Alerts.cfg] arquivo. Para obter mais informações sobre como configurar alertas administrativos, consulte o Guia *de Instalação e Administração de Produtos* do Servidor.

## Verificando o status do sistema do sensor {#section-de9d7e359242487a9fbead4ed65aebbc}

Outra maneira de verificar se o transmissor está em execução é verificar manualmente o transmissor [!DNL Servers Manager] na Análise de big data.

**Para exibir o[!DNL Servers Manager]**

* No Análise de big data, clique com o botão direito do mouse em um espaço de trabalho, clique em **[!UICONTROL Admin]**, em seguida, em [!DNL Manage], clique em **[!UICONTROL Servers]**.

Se o ícone de um transmissor [!DNL Sensor] estiver verde, ele estará em execução.

Para obter mais informações sobre o [!DNL Servers Manager], consulte o capítulo Interfaces administrativas do *Data Workbench[!DNL Sensor]Guide*.
