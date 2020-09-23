---
description: Os arquivos de log (.vsl) contêm os campos de dados de evento que são coletados dos servidores pelos Sensores e usados pelo servidor da análise de big data no processo de construção do conjunto de dados.
solution: Analytics
title: Campos de registro de dados do evento
uuid: ad9e773c-a128-4094-9e20-45a6de025c8f
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 5%

---


# Campos de registro de dados do evento{#event-data-record-fields}

Os arquivos de log (.vsl) contêm os campos de dados de evento que são coletados dos servidores pelos Sensores e usados pelo servidor da análise de big data no processo de construção do conjunto de dados.

Os nomes dos campos geralmente seguem a convenção de nomenclatura para o formato de arquivo de log estendido W3C. Muitos dos campos têm prefixos que indicam a fonte das informações contidas no campo:

* &quot;cs&quot; indica a comunicação do cliente com o servidor
* &quot;sc&quot; indica a comunicação do servidor ao cliente
* &quot;s&quot; indica informações do servidor
* &quot;c&quot; indica informações do cliente
* &quot;x&quot; indica informações criadas por um produto Adobe

