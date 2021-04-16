---
description: Atualização dos componentes do servidor para o Data Workbench 6.1 a partir da instalação 5.4.
title: Atualização do servidor DWB 5.4 para 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
exl-id: dd8c2a89-6a40-4ebf-a964-eb4851ab94a5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---

# Atualização do servidor DWB: 5.4 para 5.5{#dwb-server-upgrade-to}

Atualização dos componentes do servidor para o Data Workbench 6.1 a partir da instalação 5.4.

Consequentemente, a atualização de [!DNL Insight] 5.4 para [!DNL Insight] 5.5 é relativamente simples.

Você também pode atualizar diretamente de [!DNL Insight] 5.3 para [!DNL Insight] 5.5 usando as etapas abaixo. Certifique-se de executar todas as tarefas de atualização listadas na seção [Atualização do Insight 5.4 para 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) e na seção [Atualização do Insight 5.4 para 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9).

1. Pare os serviços [!DNL Insight Server] em todos os servidores no cluster, exceto para [!DNL Insight Master Server].

   1. Copie os novos arquivos [!DNL ReportServer.exe] e [!DNL Insight.exe] para a pasta Software\Insight .

   1. Depois que o cliente [!DNL Insight] for atualizado, copie os arquivos [!DNL InsightServer.exe] e [!DNL InsightServer64.exe] para a pasta \Bin.

   1. Aguarde até que [!DNL Insight Master Server] seja iniciado e verifique a versão em execução por meio da visualização [!DNL Connections].

1. No [!DNL Master Server] do cluster no cliente [!DNL Insight]:

   1. Faça uma cópia local do perfil [!DNL Base] existente e renomeie-o (por exemplo, BaseBackup).
   1. Copie o novo perfil [!DNL Base] para a pasta Perfis .
   1. Repita essas duas etapas para a pasta Transform .

1. Copie a pasta Scripts do pacote de servidor para o [!DNL Master Server] no diretório de instalação do Servidor.
1. Copie o arquivo [!DNL Terrain Images.cfg.off] na pasta Componentes do [!DNL Master Server].
   **Para atualizar o software cliente de  [!DNL Insight] 5.4 para 5.5**

No arquivo [!DNL Insight.cfg], verifique se a configuração Atualizar software está definida como TRUE.
