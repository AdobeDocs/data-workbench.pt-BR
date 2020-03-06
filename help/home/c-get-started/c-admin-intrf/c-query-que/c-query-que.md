---
description: Normalmente, o servidor da Análise de big data responde consultas de usuários recebidas à medida que são recebidas e continua a fornecer resultados e atualizações em tempo real até que o usuário não as solicite.
solution: Analytics
title: Fila de consulta
topic: Data workbench
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Fila de consulta{#query-queue}

Normalmente, o servidor da Análise de big data responde consultas de usuários recebidas à medida que são recebidas e continua a fornecer resultados e atualizações em tempo real até que o usuário não as solicite.

Às vezes, principalmente em sistemas com muitos usuários do Análise de big data, o número de consultas ativas requer mais recursos do sistema do que os disponíveis no servidor. [!DNL Query Queue] permite que o servidor coloque algumas consultas temporariamente suspensas até que os recursos necessários para fornecer respostas fiquem disponíveis. O [!DNL Query Queue] também fornece recursos para priorizar consultas com base em diversos parâmetros, de modo que, em caso de contenção de recursos, as consultas de prioridade mais alta sejam respondidas primeiro.

As consultas de um único cliente ou servidor de relatórios são colocadas em um grupo e agendadas como uma unidade. Você pode configurar monitores de recursos para limitar a quantidade de determinados recursos do sistema usados por consultas. Quando os recursos monitorados permitem o agendamento de outro conjunto de consultas, o grupo de prioridade mais alta é agendado. Os usuários cujas consultas ainda não estão programadas, devido a limitações de recursos, não recebem um erro, mas são notificados de que suas consultas estão na fila e que o usuário pode continuar a trabalhar na amostra local.

A configuração padrão inclui uma configuração simples para o [!DNL Query Queue], mas a deixa desativada. Os administradores podem ativar ou desativar os monitores de recursos [!DNL Query Queue], configurar os monitores de recursos para determinar a quantidade de vários recursos que são usados para consultar e configurar políticas de priorização complexas para usuários diferentes.

**Para configurar o arquivo Server.cfg para[!DNL Query Queuing]**

1. Abra [!DNL Server.cfg] clicando em **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** > **[!UICONTROL Dataset]**.
1. Clique com o botão direito do mouse **[!UICONTROL Server.cfg]** e torne-o local para edição.
1. Expandir [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. Configure os seguintes parâmetros:

   * **Grupos de usuários:** Permite configurar políticas, usuários e a prioridade da fila. Consulte Grupos [de usuários da fila de](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1) consulta para obter definições.

   * **Ativo:** (Vetor) Ativa ou desativa o [!DNL Query Queue]. Os valores válidos são true ou false. A configuração padrão é false.

   * **Grupo de usuários padrão:** (String) Digite um nome do grupo de usuários ao qual os usuários são adicionados, se não estiverem listados em nenhum grupo de usuários.
   * **Monitores de recursos:** (Vetor) Clique com o botão direito do mouse para adicionar um monitor de recursos. Você pode especificar se o [!DNL Query Queue] monitora a memória ou o número de consultas. Clique com o botão direito do mouse **[!UICONTROL Resource Monitor]** para escolher Monitor de orçamento de memória ou Monitor de número de consultas. Consulte Monitores [de recursos da fila de](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325) consulta para obter mais informações.

   * **Prioridade intocável:** (Int) Especifica que os pacotes com prioridade maior ou igual a esse valor nunca são predados para o agendamento de pacotes de prioridade mais alta. Usado em conjunto com o [!DNL Memory Budget Monitor] descrito na Tabela [Parâmetros do Grupo](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1)de Usuários.

