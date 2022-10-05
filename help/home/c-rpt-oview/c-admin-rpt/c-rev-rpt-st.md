---
description: Informações sobre o status do Servidor de relatórios e o status do conjunto de relatórios.
title: Revisar o status do relatório
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
exl-id: a986f148-f019-457c-ade8-a4eaecbb1de7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# Revisar o status do relatório{#reviewing-report-status}

{{eol}}

Informações sobre o status do Servidor de relatórios e o status do conjunto de relatórios.

* [Status do servidor de relatórios](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [Status do conjunto de relatórios](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## Status do servidor de relatórios {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**Frequência recomendada:** Apenas quando necessário

[!DNL Report] envia informações de status para o servidor do Data Workbench a cada dois minutos em relação ao status da variável [!DNL Report] Servidor. Essas informações podem ser vistas sob a [!DNL Report Server Status] no nó [!DNL Detailed Status] interface.

**Para abrir o [!DNL Detailed Status] visualização**

1. No Data Workbench, clique com o botão direito do mouse em um espaço de trabalho e clique em **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. No [!DNL Servers] , clique com o botão direito do mouse no ícone do servidor do Data Workbench que [!DNL Report] a máquina se conecta e clica **[!UICONTROL Detailed Status.]**

1. Clique em **[!UICONTROL Report Server Status]**.

Se mais de um [!DNL Report] estiver conectado ao servidor do Data Workbench, será exibida uma entrada para cada [!DNL Report Server] no vetor de status. O intervalo de dois minutos pode ser substituído pela especificação de um valor no parâmetro Intervalo de status (segundos) na variável [!DNL Reporting] nó do [!DNL ReportServer.cfg] arquivo.

Para obter informações sobre o [!DNL ReportServer.cfg] arquivo, consulte [Configurar o conjunto de relatórios](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0). Para obter informações sobre como configurar [!DNL Report], consulte [Instalar relatório](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

Para obter mais informações sobre [!DNL Detailed Status], consulte o capítulo Interfaces administrativas do *Guia do usuário do Data Workbench*.

## Status do conjunto de relatórios {#section-8569b94266b74a1f85d2a85106a2aaef}

**Frequência recomendada:** Apenas quando necessário

[!DNL Report] transmite informações de status para cada conjunto de relatórios para o servidor do Data Workbench. Informações básicas, como quando um conjunto de relatórios é gerado e onde é distribuído, é exibido no Data Workbench acima do conjunto de relatórios em texto verde. Ao executar relatórios, [!DNL Report] O servidor gera uma mensagem a cada dois minutos, indicando a porcentagem completa das consultas atuais. Esse intervalo de dois minutos pode ser substituído pela especificação de um valor no parâmetro Intervalo de Mensagem de Conclusão (segundos) na variável [!DNL Reporting] nó do [!DNL ReportServer.cfg] arquivo.

![](assets/report_status.png)

>[!NOTE]
>
>Se ocorrer um erro ao executar um relatório, ele será indicado em texto vermelho abaixo da miniatura desse relatório. Você pode clicar com o botão direito do mouse no espaço de trabalho para exibir a mensagem de erro completa.
