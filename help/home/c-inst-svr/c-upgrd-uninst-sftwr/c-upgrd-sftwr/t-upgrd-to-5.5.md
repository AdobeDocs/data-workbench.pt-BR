---
description: Atualização dos componentes do servidor para o Data Workbench 6.1 a partir da instalação 5.4.
title: Atualização do servidor DWB 5.4 para 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
exl-id: dd8c2a89-6a40-4ebf-a964-eb4851ab94a5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---

# Atualização do servidor DWB: 5.4 para 5.5{#dwb-server-upgrade-to}

{{eol}}

Atualização dos componentes do servidor para o Data Workbench 6.1 a partir da instalação 5.4.

Consequentemente, a modernização a partir de [!DNL Insight] 5.4 a [!DNL Insight] 5.5 é relativamente simples.

Você também pode atualizar diretamente de [!DNL Insight] 5.3 a [!DNL Insight] 5.5 utilizando as etapas abaixo. Certifique-se de executar todas as tarefas de atualização listadas na [Atualização do Insight 5.4 para 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) e a [Atualização do Insight 5.4 para 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) seção.

1. Pare o [!DNL Insight Server] serviços em todos os servidores do cluster, exceto para [!DNL Insight Master Server].

   1. Copie o novo [!DNL ReportServer.exe] e [!DNL Insight.exe] arquivos para a pasta Software\Insight.

   1. Depois que a variável [!DNL Insight] cliente atualizou, copie o [!DNL InsightServer.exe] e [!DNL InsightServer64.exe] arquivos na pasta \Bin.

   1. Aguarde a [!DNL Insight Master Server] para iniciar, verifique a versão em execução por meio do [!DNL Connections] visualização.

1. No [!DNL Master Server] no [!DNL Insight] cliente:

   1. Faça uma cópia local do [!DNL Base] e renomeie-o (por exemplo, BaseBackup).
   1. Copie o novo [!DNL Base] para a pasta Perfis.
   1. Repita essas duas etapas para a pasta Transform .

1. Copie a pasta Scripts do pacote de servidor para o [!DNL Master Server] no diretório de instalação do servidor.
1. Copie o [!DNL Terrain Images.cfg.off] na pasta Componentes do [!DNL Master Server].
   **Para atualizar o software cliente de [!DNL Insight] 5.4 a 5.5**

No [!DNL Insight.cfg] verifique se a configuração Atualizar software está definida como TRUE.
