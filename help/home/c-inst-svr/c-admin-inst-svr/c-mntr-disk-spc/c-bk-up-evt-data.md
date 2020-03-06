---
description: O backup dos dados de eventos deve ser feito diariamente usando os sistemas de backup normais de sua empresa e os procedimentos de recuperação de desastres.
solution: Insight
title: Backup de dados de evento
uuid: 1b9e5dfe-0bf2-4ee9-bf70-1dd320a678d6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Backup de dados de evento{#backing-up-event-data}

O backup dos dados de eventos deve ser feito diariamente usando os sistemas de backup normais de sua empresa e os procedimentos de recuperação de desastres.

**Frequência recomendada:** Diariamente

[!DNL Insight Server] inicia novos arquivos de log às 12:00 AM GMT diariamente. A Adobe recomenda que você faça backup dos arquivos de registro todos os dias, logo após as 12h00 GMT, para que você capture todos os dados do dia anterior. Por exemplo, fazer backup de todos os arquivos de registro às 12:05 AM GMT em 15 de dezembro captura todos os dados de 14 de dezembro. [!DNL Insight Server] não precisa ser interrompido durante backups de arquivos de log e toda a funcionalidade permanece disponível.

## Backup da integração, sistema operacional, saída e dados do sistema {#section-217e52a99f944d8e83a3cc98f3d06e7e}

**Frequência recomendada:** Diariamente

A integração, o sistema operacional, a saída e os dados do sistema devem ser copiados em backup regularmente e de forma diligente usando os sistemas normais de backup e recuperação de desastres da sua empresa.
