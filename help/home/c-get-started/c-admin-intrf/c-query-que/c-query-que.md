---
description: Normalmente, o servidor do Data Workbench responde consultas de usuários recebidas à medida que são recebidas e continua a fornecer resultados e atualizações em tempo real até que o usuário não esteja mais solicitando essas consultas.
title: Fila de query
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
exl-id: 5d9b20bf-9396-4016-beed-cee8f533f3ea
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 1%

---

# Fila de query{#query-queue}

Normalmente, o servidor do Data Workbench responde consultas de usuários recebidas à medida que são recebidas e continua a fornecer resultados e atualizações em tempo real até que o usuário não esteja mais solicitando essas consultas.

Às vezes, especialmente em sistemas com muitos usuários do Data Workbench, o número de consultas ativas requer mais recursos do sistema do que os disponíveis no servidor. [!DNL Query Queue] O permite que o servidor coloque algumas consultas temporariamente em espera até que os recursos necessários para fornecer respostas fiquem disponíveis. O [!DNL Query Queue] também fornece recursos para priorizar consultas com base em uma variedade de parâmetros, de modo que, no caso de contenção de recursos, as consultas de prioridade mais alta sejam respondidas primeiro.

Consultas de um único cliente ou servidor de relatório são colocadas em um conjunto e agendadas como uma unidade. Você pode configurar monitores de recursos para limitar a quantidade de determinados recursos do sistema usados por queries. Quando os recursos monitorados permitem o agendamento de outro conjunto de query, o conjunto de maior prioridade é agendado. Os usuários cujas consultas ainda não estão agendadas, devido a limitações de recursos, não recebem um erro, mas são notificados de que suas consultas estão na fila e que o usuário pode continuar a trabalhar na amostra local.

A configuração padrão inclui uma configuração simples para o [!DNL Query Queue], mas a deixa desativada. Os administradores podem habilitar ou desabilitar o [!DNL Query Queue], configurar monitores de recursos para determinar a quantidade de vários recursos são usados para consultas e configurar políticas complexas de priorização para usuários diferentes.

**Para configurar o arquivo Server.cfg para[!DNL Query Queuing]**

1. Abra [!DNL Server.cfg] clicando em **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** > **[!UICONTROL Dataset]**.
1. Clique com o botão direito do mouse em **[!UICONTROL Server.cfg]** e torne-o local para edição.
1. Expandir [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. Configure os seguintes parâmetros:

   * **Grupos de usuários:** Permite configurar políticas, usuários e a prioridade da fila. Consulte [Grupos de usuários da fila de query](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1) para obter as definições.

   * **Ativo:** (vetor) ativa ou desativa o  [!DNL Query Queue]. Os valores válidos são verdadeiros ou falsos. A configuração padrão é false.

   * **Grupo de usuários padrão:** (String) digite um nome do grupo de usuários ao qual os usuários serão adicionados, se não estiverem listados em nenhum grupo de usuários.
   * **Monitores de recursos:**  (Vetor) Clique com o botão direito do mouse para adicionar um monitor de recursos. Você pode especificar se o [!DNL Query Queue] monitora a memória ou o número de consultas. Clique com o botão direito do mouse **[!UICONTROL Resource Monitor]** para escolher Memory Budget Monitor ou Number of Queries Monitor. Consulte [Monitores de recursos da fila de query](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325) para obter mais informações.

   * **Prioridade intocável:**  (Int) Especifica que os pacotes com prioridade maior ou igual a este valor nunca são predados para o agendamento de pacotes de prioridade mais alta. Usado em conjunto com o [!DNL Memory Budget Monitor] descrito na [Tabela de parâmetros do grupo de usuários](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1).
