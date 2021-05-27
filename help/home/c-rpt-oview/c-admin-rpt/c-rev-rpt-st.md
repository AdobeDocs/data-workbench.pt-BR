---
description: Informações sobre o status do Servidor de relatórios e o status do conjunto de relatórios.
title: Revisar o status do relatório
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
exl-id: a986f148-f019-457c-ade8-a4eaecbb1de7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# Revisar o status do relatório{#reviewing-report-status}

Informações sobre o status do Servidor de relatórios e o status do conjunto de relatórios.

* [Status do servidor de relatórios](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [Status do conjunto de relatórios](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## Status do servidor de relatórios {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**Frequência recomendada:** somente quando necessário

[!DNL Report] envia informações de status para o servidor do Data Workbench a cada dois minutos em relação ao status do  [!DNL Report] Servidor. Essas informações podem ser vistas no nó [!DNL Report Server Status] na interface [!DNL Detailed Status].

**Para abrir a  [!DNL Detailed Status] visualização**

1. No Data Workbench, clique com o botão direito do mouse em um espaço de trabalho e clique em **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. Na interface [!DNL Servers], clique com o botão direito do mouse no ícone do servidor do Data Workbench ao qual a máquina [!DNL Report] se conecta e clique em **[!UICONTROL Detailed Status.]**

1. Clique em **[!UICONTROL Report Server Status]**.

Se mais de um [!DNL Report] estiver conectado ao servidor do Data Workbench, uma entrada será exibida para cada [!DNL Report Server] no vetor de status. O intervalo de dois minutos pode ser substituído pela especificação de um valor no parâmetro Intervalo de status (segundos) no nó [!DNL Reporting] do arquivo [!DNL ReportServer.cfg].

Para obter informações sobre o arquivo [!DNL ReportServer.cfg], consulte [Configurar o conjunto de relatórios](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0). Para obter informações sobre como configurar [!DNL Report], consulte [Instalando o Relatório](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

Para obter mais informações sobre [!DNL Detailed Status], consulte o capítulo Interfaces Administrativas do *Guia do Usuário do Data Workbench*.

## Status do conjunto de relatórios {#section-8569b94266b74a1f85d2a85106a2aaef}

**Frequência recomendada:** somente quando necessário

[!DNL Report] transmite informações de status para cada conjunto de relatórios para o servidor do Data Workbench. Informações básicas, como quando um conjunto de relatórios é gerado e onde é distribuído, é exibido no Data Workbench acima do conjunto de relatórios em texto verde. Ao executar relatórios, [!DNL Report] O servidor gera uma mensagem a cada dois minutos, indicando a porcentagem completa das consultas atuais. Esse intervalo de dois minutos pode ser substituído pela especificação de um valor no parâmetro Intervalo de Mensagem de Conclusão (segundos) no nó [!DNL Reporting] do arquivo [!DNL ReportServer.cfg].

![](assets/report_status.png)

>[!NOTE]
>
>Se ocorrer um erro ao executar um relatório, ele será indicado em texto vermelho abaixo da miniatura desse relatório. Você pode clicar com o botão direito do mouse no espaço de trabalho para exibir a mensagem de erro completa.
