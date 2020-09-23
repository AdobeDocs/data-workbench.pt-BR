---
description: O backup dos dados do evento deve ser feito diariamente usando os sistemas de backup normais da empresa e os procedimentos de recuperação de desastres.
solution: Analytics
title: Backup de dados do evento
uuid: 1b9e5dfe-0bf2-4ee9-bf70-1dd320a678d6
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 5%

---


# Backup de dados do evento{#backing-up-event-data}

O backup dos dados do evento deve ser feito diariamente usando os sistemas de backup normais da empresa e os procedimentos de recuperação de desastres.

**Frequência recomendada:** Diariamente

[!DNL Insight Server] inicia novos arquivos de log às 12:00 AM GMT diariamente. O Adobe recomenda que você faça backup dos arquivos de registro todos os dias, logo após as 12h00 GMT, para que você capture todos os dados do dia anterior. Por exemplo, fazer backup de todos os arquivos de registro às 12:05 AM GMT em 15 de dezembro captura todos os dados de 14 de dezembro. [!DNL Insight Server] não precisa ser interrompido durante backups de arquivos de log e toda a funcionalidade permanece disponível.

## Backup da integração, sistema operacional, saída e dados do sistema {#section-217e52a99f944d8e83a3cc98f3d06e7e}

**Frequência recomendada:** Diariamente

A integração, o sistema operacional, a saída e os dados do sistema devem ser copiados em backup regularmente e de forma diligente usando os sistemas normais de backup e recuperação de desastres da sua empresa.
