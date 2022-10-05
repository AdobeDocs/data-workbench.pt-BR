---
description: O backup dos dados de eventos deve ser feito diariamente usando os sistemas de backup normais de sua empresa e os procedimentos de recuperação de desastres.
title: Backup de dados do evento
uuid: 1b9e5dfe-0bf2-4ee9-bf70-1dd320a678d6
exl-id: 5afeb3a2-a2e7-4155-8fb9-1abc9c22c3c6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 5%

---

# Backup de dados do evento{#backing-up-event-data}

{{eol}}

O backup dos dados de eventos deve ser feito diariamente usando os sistemas de backup normais de sua empresa e os procedimentos de recuperação de desastres.

**Frequência recomendada:** Diariamente

[!DNL Insight Server] inicia novos arquivos de log às 12:00 AM GMT diariamente. O Adobe recomenda que você faça backup dos arquivos de log todos os dias logo após as 12h GMT, para que você capture todos os dados do dia anterior. Por exemplo, fazer o backup de todos os arquivos de log às 12h05 GMT em 15 de dezembro captura todos os dados de 14 de dezembro. [!DNL Insight Server] não precisa ser interrompida durante backups de arquivos de log e toda a funcionalidade permanece disponível.

## Backup de integração, sistema operacional, saída e dados do sistema {#section-217e52a99f944d8e83a3cc98f3d06e7e}

**Frequência recomendada:** Diariamente

A integração, o sistema operacional, a saída e os dados do sistema devem ser copiados regularmente e diligentemente usando os sistemas normais de backup e recuperação de desastres da sua empresa.
