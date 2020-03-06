---
description: Etapas para garantir que o reprocessamento ou a retransformação ocorra sem problemas e termine a tempo para que os usuários da análise de big data voltem ao trabalho
solution: Analytics
title: Preparação para reprocessamento ou retransformação
topic: Data workbench
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Preparação para reprocessamento ou retransformação{#preparing-for-reprocessing-or-retransformation}

Etapas para garantir que o reprocessamento ou a retransformação ocorra sem problemas e termine a tempo para que os usuários da análise de big data voltem ao trabalho

1. Determine o tempo decorrido do processamento ou transformação anterior verificando o perfil do conjunto de dados [!DNL Processing Mode History] na [!DNL Detailed Status] interface.

   1. Ao trabalhar no perfil do conjunto de dados, abra a [!DNL Detailed Status] interface.
   1. Clique em **[!UICONTROL Processing Status]** > *&lt;**[!UICONTROL dataset profile name]**>* > **[!UICONTROL Processing Mode History]** para visualizar os tempos decorridos do processamento ou transformação anterior.

      * Entrada rápida é o tempo total necessário para o processamento de log.
      * A Mesclagem rápida é o tempo total necessário para a transformação.
      * A soma das duas vezes (Fast Input + Fast Merge) é o tempo total necessário para o processamento do conjunto de dados.
      O exemplo abaixo indica que o processamento de log levou aproximadamente 43 segundos, enquanto a transformação demorou menos de 2 minutos.

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      Para obter mais informações sobre a [!DNL Detailed Status] interface, consulte o Guia *do Usuário da Análise de* big data.


1. Programe e planeje o reprocessamento. Como os usuários da análise de big data não têm acesso aos dados durante a fase de processamento do log, certifique-se de programar o reprocessamento para ocorrer durante um tempo apropriado, como durante o fim de semana.
1. Monitore o progresso do reprocessamento e da retransformação usando os campos na seção [!DNL Processing Legend.] Para obter mais informações sobre o [!DNL Processing Legend], consulte o Guia *do Usuário da Análise de* big data.
