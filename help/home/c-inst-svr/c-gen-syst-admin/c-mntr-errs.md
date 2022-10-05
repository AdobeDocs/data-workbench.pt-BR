---
description: Para detectar erros do sistema e do aplicativo o mais rápido possível e resolvê-los antes que causem grandes problemas ou paralisações, você deve monitorar regularmente seus registros de eventos.
title: Monitorar eventos para erros
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
exl-id: 88f48594-5c73-4ae3-8014-b8543e689426
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 6%

---

# Monitorar eventos para erros{#monitoring-events-for-errors}

{{eol}}

Para detectar erros do sistema e do aplicativo o mais rápido possível e resolvê-los antes que causem grandes problemas ou paralisações, você deve monitorar regularmente seus registros de eventos.

**Frequência recomendada:** A cada 5-10 minutos

Para monitorar os produtos de software do servidor Adobe, a ferramenta de gerenciamento automatizado pode ser configurada para monitorar o registro de eventos quanto a erros com o &quot;Adobe&quot; de origem e, em seguida, alertar o pessoal adequado para problemas que podem exigir intervenção.

No Windows, mensagens de erro do aplicativo são enviadas para o Registro de Eventos do Aplicativo no Windows, que você pode acessar usando o Visualizador de Eventos do Windows. No Unix, as mensagens de erro do aplicativo são enviadas para o syslog do Unix usando o recurso LOG_DAEMON.

**Para abrir o Visualizador de Eventos do Windows**

* Clique em **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.
