---
description: Os arquivos de log (.vsl) contêm os campos de dados de evento coletados de servidores pelos Sensores e usados pelo servidor do Data Workbench no processo de construção do conjunto de dados.
title: Campos de registro de dados do evento (arquivos .vsl)
uuid: ad9e773c-a128-4094-9e20-45a6de025c8f
exl-id: d48b593f-5a3a-4a4e-9a71-3b91024c9a48
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 2%

---

# Campos de registro de dados do evento{#event-data-record-fields}

{{eol}}

Os arquivos de log (.vsl) contêm os campos de dados de evento coletados de servidores pelos Sensores e usados pelo servidor do Data Workbench no processo de construção do conjunto de dados.

Os nomes dos campos geralmente seguem a convenção de nomenclatura do formato de arquivo de log estendido W3C. Muitos dos campos têm prefixos que indicam a fonte das informações contidas no campo :

* &quot;cs&quot; indica a comunicação do cliente com o servidor
* &quot;sc&quot; indica a comunicação do servidor com o cliente
* &quot;s&quot; indica informações do servidor
* &quot;c&quot; indica informações do cliente
* &quot;x&quot; indica informações criadas por um produto Adobe
