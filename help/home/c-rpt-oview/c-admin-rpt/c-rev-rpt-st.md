---
description: Informações sobre o status do Servidor de relatórios e o status do conjunto de relatórios.
solution: Analytics
title: Revisando o status do relatório
topic: Data workbench
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Revisando o status do relatório{#reviewing-report-status}

Informações sobre o status do Servidor de relatórios e o status do conjunto de relatórios.

* [Status do Servidor de Relatório](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [Status do conjunto de relatórios](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## Status do Servidor de Relatório {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**Frequência recomendada:** Somente quando necessário

[!DNL Report] envia informações de status para o servidor da análise de big data a cada dois minutos em relação ao status do [!DNL Report] Servidor. Essas informações podem ser vistas sob o [!DNL Report Server Status] nó na [!DNL Detailed Status] interface.

**Para abrir a[!DNL Detailed Status]visualização**

1. Na análise de big data, clique com o botão direito do mouse em uma área de trabalho e clique em **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. Na [!DNL Servers] interface, clique com o botão direito do mouse no ícone do servidor da análise de big data ao qual a [!DNL Report] máquina se conecta e clique em **[!UICONTROL Detailed Status.]**

1. Clique em **[!UICONTROL Report Server Status]**.

Se mais de um [!DNL Report] estiver conectado ao servidor da análise de big data, uma entrada será exibida para cada um [!DNL Report Server] no vetor Status. O intervalo de dois minutos pode ser substituído especificando-se um valor no parâmetro Intervalo de status (segundos) no [!DNL Reporting] nó do [!DNL ReportServer.cfg] arquivo.

Para obter informações sobre o [!DNL ReportServer.cfg] arquivo, consulte [Configurar o conjunto](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)de relatórios. Para obter informações sobre como configurar [!DNL Report], consulte [Instalação do relatório](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

Para obter mais informações sobre [!DNL Detailed Status], consulte o capítulo Interfaces administrativas do Guia *do usuário da Análise de* big data.

## Status do conjunto de relatórios {#section-8569b94266b74a1f85d2a85106a2aaef}

**Frequência recomendada:** Somente quando necessário

[!DNL Report] transmite informações de status para cada conjunto de relatórios ao servidor da Análise de big data. Informações básicas, como quando um conjunto de relatórios é gerado e onde é distribuído, são exibidas na análise de big data acima do conjunto de relatórios em texto verde. Durante a execução de relatórios, o [!DNL Report] Server gera uma mensagem a cada dois minutos, indicando a porcentagem de conclusão das consultas atuais. Esse intervalo de dois minutos pode ser substituído especificando-se um valor no parâmetro Intervalo de mensagem de conclusão (segundos) no [!DNL Reporting] nó do [!DNL ReportServer.cfg] arquivo.

![](assets/report_status.png)

>[!NOTE]
>
>Se um erro ocorreu durante a execução de um relatório, o erro é indicado em texto vermelho abaixo da miniatura desse relatório. Você pode clicar com o botão direito do mouse no espaço de trabalho para exibir a mensagem de erro completa.

