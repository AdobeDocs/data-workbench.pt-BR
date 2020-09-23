---
description: As tarefas administrativas para a funcionalidade do repetidor são muito semelhantes às do Insight Server.
solution: Analytics
title: Administrar repetidor
uuid: 4fbfce3a-2610-4dcd-a585-cb7ee07b90db
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 12%

---


# Administrar repetidor{#administering-repeater}

As tarefas administrativas para a funcionalidade do repetidor são muito semelhantes às do Insight Server.

São aplicáveis as seguintes tarefas administrativas: exceções ou alterações que devem ser feitas para que a [!DNL Insight Server] DPU possa ser usada com o servidor repetidor sejam anotadas após cada etapa.

* [Revalidar o certificado digital](../../../home/c-inst-svr/c-admin-inst-svr/c-reval-dgtl-cert.md#concept-f0020a6f0d6f477099b7a8f0b6e2944c)
* [Confirmar se o serviço está sendo executado](../../../home/c-inst-svr/c-admin-inst-svr/c-cfrm-svc-rng.md#concept-15b046e92d254bbd95dec829abc76677) Na lista de serviços no painel de controle de Serviços, procure por &quot;Repetidor&quot;.

* [Configurar o controle de acesso](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)
* [Monitoramento do espaço](../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/c-mntr-disk-spc.md#concept-a83447e44f4e47aba282328be395a0d4) em disco Os tipos de dados que se aplicam ao servidor repetidor são dados de evento, sistema operacional e sistema. Se você estiver usando o servidor repetidor para o armazenamento de backup e for necessário disponibilizar mais espaço para o armazenamento de dados na máquina, você poderá mover todos os arquivos de log do dia mais recentes para outra máquina ou mídia de armazenamento de dados (unidade zip, fita e assim por diante). Mover os dados não requer que você pare o serviço repetidor.

   >[!NOTE]
   >
   >Você deve verificar a integridade das cópias de backup dos seus [!DNL .vsl] arquivos antes de excluí-los do Repeater.

* [Configurar alertas administrativos](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa)
* [Monitorar eventos administrativos](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adm-evts.md#task-4c78325b3e6e4dde8fa94c1896e19e34)
* [Monitorar logs de auditoria](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adt-lgs.md#task-5dd9830424fe440ea1369215a1aca231)
* [Configurar comunicações](../../../home/c-inst-svr/c-admin-inst-svr/t-config-com.md#task-471305ecf7a644789a288f93c42514ec)
* [A reinicialização da funcionalidade do Serviço](../../../home/c-inst-svr/c-admin-inst-svr/t-rest-svc.md#task-97f97f1019bc440080ab2fddfdc04c74) [!DNL Repeater] foi projetada para ser executada continuamente. Se você reiniciar a máquina, o repetidor será reiniciado automaticamente. Se precisar start e parar o repetidor manualmente, você pode fazer isso usando o painel de controle de Serviços no Windows.

