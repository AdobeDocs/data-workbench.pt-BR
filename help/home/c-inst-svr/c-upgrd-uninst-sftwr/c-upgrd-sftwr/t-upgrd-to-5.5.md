---
description: Atualização dos componentes do servidor para a Data Workbench 6.1 da instalação 5.4.
solution: Analytics
title: Atualização do servidor DWB 5.4 para 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---


# Atualização do servidor DWB: 5.4 para 5.5{#dwb-server-upgrade-to}

Atualização dos componentes do servidor para a Data Workbench 6.1 da instalação 5.4.

Consequentemente, a atualização de [!DNL Insight] 5.4 para [!DNL Insight] 5.5 é relativamente simples.

Você também pode atualizar diretamente da versão [!DNL Insight] 5.3 para a [!DNL Insight] 5.5 usando as etapas abaixo. Certifique-se de executar todas as tarefas de atualização listadas na seção [Upgrade do Insight 5.4 para o 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) e na seção [Upgrading do Insight 5.4 para o 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) .

1. Pare os [!DNL Insight Server] serviços em todos os servidores no cluster, exceto os [!DNL Insight Master Server].

   1. Copie os novos [!DNL ReportServer.exe] e [!DNL Insight.exe] arquivos para a pasta Software\Insight.

   1. Depois que o [!DNL Insight] cliente tiver atualizado, copie os arquivos [!DNL InsightServer.exe] e [!DNL InsightServer64.exe] os arquivos na pasta \Bin.

   1. Aguarde o start [!DNL Insight Master Server] e verifique a versão em execução por meio da [!DNL Connections] visualização.

1. No cluster [!DNL Master Server] no [!DNL Insight] cliente:

   1. Faça uma cópia local do [!DNL Base] perfil existente e renomeie-o (por exemplo, BaseBackup).
   1. Copie o novo [!DNL Base] perfil para a pasta Perfis.
   1. Repita essas duas etapas para a pasta Transformar.

1. Copie a pasta Scripts do pacote do servidor para o [!DNL Master Server] diretório de instalação do Servidor.
1. Copie o [!DNL Terrain Images.cfg.off] arquivo na pasta Componentes do [!DNL Master Server].
   **Para atualizar o software cliente de[!DNL Insight]5.4 para 5.5**

No [!DNL Insight.cfg] arquivo, verifique se a configuração Atualizar software está definida como TRUE.
