---
description: O parâmetro Bytes de amostra no arquivo Server.cfg especifica o tamanho do cache de dados (em bytes) para o Data Workbench.
title: Server.cfg
uuid: 7e789133-09fc-442d-b643-cca8620f4a97
exl-id: fb7667f6-4061-4bde-8a48-6489b24e0411
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 1%

---

# Server.cfg{#server-cfg}

{{eol}}

O parâmetro Bytes de amostra no arquivo Server.cfg especifica o tamanho do cache de dados (em bytes) para o Data Workbench.

O valor padrão é 250e6. Instruções para abrir e salvar o [!DNL Server.cfg] são iguais aos de [!DNL Log Processing Mode.cfg]. Consulte [Log Processing Mode.cfg](../../../home/c-dataset-const-proc/c-add-config-files/t-log-proc-mode.md#task-e530907cb34f488182afe625e6d9e44a).

>[!NOTE]
>
>Como o parâmetro deste arquivo afeta o desempenho do sistema, entre em contato com o Adobe antes de fazer qualquer alteração.

É possível limitar ainda mais o tamanho do cache de dados da máquina do Data Workbench que se conecta ao servidor do Data Workbench, definindo o parâmetro Tamanho máximo de amostra na variável [!DNL Insight.cfg] arquivo. Para obter mais informações, consulte o *Guia do usuário do Data Workbench*.
