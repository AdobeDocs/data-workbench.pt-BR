---
description: Etapas para garantir que o reprocessamento ou a retransformação ocorra sem problemas e termine a tempo para que os usuários do Data Workbench retornem ao trabalho
title: Preparar para reprocessar ou retransformar
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
exl-id: f3746edf-416e-45c2-896c-48a3c875318c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 4%

---

# Preparar para reprocessar ou retransformar{#preparing-for-reprocessing-or-retransformation}

{{eol}}

Etapas para garantir que o reprocessamento ou a retransformação ocorra sem problemas e termine a tempo para que os usuários do Data Workbench retornem ao trabalho

1. Determine o tempo decorrido do processamento ou da transformação anterior, verificando o perfil do conjunto de dados [!DNL Processing Mode History] no [!DNL Detailed Status] interface.

   1. Ao trabalhar no perfil do conjunto de dados, abra o [!DNL Detailed Status] interface.
   1. Clique em **[!UICONTROL Processing Status]** > *&lt;**[!UICONTROL dataset profile name]**>* > **[!UICONTROL Processing Mode History]** para visualizar os tempos decorridos de processamento ou transformação anterior.

      * Entrada rápida é o tempo total necessário para o processamento de log.
      * Fast Merge é o tempo total necessário para a transformação.
      * A soma das duas vezes (Fast Input + Fast Merge) é o tempo total necessário para processar o conjunto de dados.

      O exemplo abaixo indica que o processamento de log levou aproximadamente 43 segundos, enquanto a transformação demorou menos de 2 minutos.

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      Para obter mais informações sobre o [!DNL Detailed Status] consulte a *Guia do usuário do Data Workbench*.


1. Programe e planeje o reprocessamento. Como os usuários do Data Workbench não têm acesso aos dados durante a fase de processamento de log, certifique-se de agendar o reprocessamento para que ocorra durante um tempo apropriado, como durante o fim de semana.
1. Monitore o progresso do reprocessamento e da retransformação usando os campos no [!DNL Processing Legend.] Para obter mais informações sobre o [!DNL Processing Legend], consulte o *Guia do usuário do Data Workbench*.
