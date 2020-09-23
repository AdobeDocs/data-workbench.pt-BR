---
description: Para detectar erros do sistema e do aplicativo o mais rápido possível e corrigi-los antes que causem problemas importantes ou paralisações, monitore regularmente os registros de eventos.
solution: Analytics
title: Monitorar eventos para erros
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 6%

---


# Monitorar eventos para erros{#monitoring-events-for-errors}

Para detectar erros do sistema e do aplicativo o mais rápido possível e corrigi-los antes que causem problemas importantes ou paralisações, monitore regularmente os registros de eventos.

**Frequência recomendada:** A cada 5 a 10 minutos

Para monitorar seus produtos de software de servidor de Adobe, sua ferramenta de gerenciamento automatizado pode ser configurada para monitorar o registro de eventos em busca de erros com a fonte &quot;Adobe&quot; e alertar a equipe apropriada para problemas que possam exigir intervenção.

No Windows, as mensagens de erro do aplicativo são enviadas para o Log de Eventos do aplicativo no Windows, que você pode acessar usando o Visualizador de Eventos do Windows. No Unix, mensagens de erro de aplicativo são enviadas para o syslog do Unix usando o recurso LOG_DAEMON.

**Para abrir o Visualizador de Eventos do Windows**

* Clique em **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

