---
description: Para monitorar mais detalhadamente sua implementação, você pode monitorar todas as portas em suas máquinas de servidor, bem como os produtos de software em execução em cada uma dessas portas.
title: Monitorar portas e aplicativos
uuid: 63d92718-81df-49eb-adda-8b49bde57a9d
exl-id: 418b2e5c-42ec-40f0-9cae-375194288143
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 4%

---

# Monitorar portas e aplicativos{#monitoring-ports-and-applications}

Para monitorar mais detalhadamente sua implementação, você pode monitorar todas as portas em suas máquinas de servidor, bem como os produtos de software em execução em cada uma dessas portas.

**Frequência recomendada:** a cada 5-10 minutos

Usando um aplicativo ou script, você pode monitorar a porta TCP na qual cada aplicativo está sendo executado (normalmente a porta 80 ou 443) para garantir que o aplicativo esteja vinculado a essa porta. Para fazer isso, solicite uma página de status do aplicativo da máquina que deseja monitorar.

**Para solicitar a página de status do aplicativo**

1. Na máquina que deseja monitorar, modifique os Controles de acesso para permitir que seu aplicativo ou script de monitoramento acesse a máquina. Para obter instruções, consulte [Configurar Controle de Acesso](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).
1. Conecte-se a [!DNL https://IP Address/Status/], onde Endereço IP é o endereço IP da máquina para a qual você deseja receber status.

   Exemplo: [!DNL https://127.0.0.1/Status/]

   A máquina deve responder com uma descrição do status do servidor. Se ele não responder, verifique os registros de eventos e entre em contato com o Atendimento ao cliente do Adobe.

   Para obter mais informações sobre esse tipo de monitoramento avançado, entre em contato com os Serviços de consultoria da Adobe.
