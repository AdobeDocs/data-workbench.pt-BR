---
description: As tarefas administrativas para a funcionalidade do repetidor são muito semelhantes às do Insight Server.
title: Administrar repetidor
uuid: 4fbfce3a-2610-4dcd-a585-cb7ee07b90db
exl-id: 5c7a4f95-be4b-4c2c-8dea-19037ba0b5cc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 12%

---

# Administrar repetidor{#administering-repeater}

{{eol}}

As tarefas administrativas para a funcionalidade do repetidor são muito semelhantes às do Insight Server.

Aplicam-se as seguintes tarefas administrativas: exceções ou alterações que você deve fazer para que a variável [!DNL Insight Server] A DPU pode ser usada com o servidor repetidor é anotada após cada etapa.

* [Revalidar o certificado digital](../../../home/c-inst-svr/c-admin-inst-svr/c-reval-dgtl-cert.md#concept-f0020a6f0d6f477099b7a8f0b6e2944c)
* [Confirmar se o serviço está sendo executado](../../../home/c-inst-svr/c-admin-inst-svr/c-cfrm-svc-rng.md#concept-15b046e92d254bbd95dec829abc76677) Na lista de serviços no Painel de controle dos serviços, procure por &quot;Repetidor&quot;.

* [Configurar o controle de acesso](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)
* [Monitorar o espaço em disco](../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/c-mntr-disk-spc.md#concept-a83447e44f4e47aba282328be395a0d4) Os tipos de dados que se aplicam ao servidor repetidor são dados de evento, sistema operacional e sistema. Se estiver usando o servidor repetidor para armazenamento de backup e for necessário disponibilizar mais espaço de armazenamento de dados na máquina, você pode mover todos os arquivos de log do dia mais atual para outra máquina ou meio de armazenamento de dados (unidade zip, fita e assim por diante). Mover os dados não requer a interrupção do serviço repetidor.

   >[!NOTE]
   >
   >Você deve verificar a integridade das cópias de backup de seu [!DNL .vsl] arquivos antes de excluir qualquer um deles do Repetidor.

* [Configurar alertas administrativos](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa)
* [Monitorar eventos administrativos](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adm-evts.md#task-4c78325b3e6e4dde8fa94c1896e19e34)
* [Monitorar logs de auditoria](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adt-lgs.md#task-5dd9830424fe440ea1369215a1aca231)
* [Configurar comunicações](../../../home/c-inst-svr/c-admin-inst-svr/t-config-com.md#task-471305ecf7a644789a288f93c42514ec)
* [Reiniciar o serviço](../../../home/c-inst-svr/c-admin-inst-svr/t-rest-svc.md#task-97f97f1019bc440080ab2fddfdc04c74)  [!DNL Repeater] foi criada para funcionar continuamente. Se você reiniciar a máquina, o repetidor será reiniciado automaticamente. Se você precisar iniciar e parar o repetidor manualmente, é possível fazer isso usando o Painel de controle dos Serviços no Windows.
