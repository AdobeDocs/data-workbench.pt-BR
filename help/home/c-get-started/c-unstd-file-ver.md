---
description: A área de trabalho facilita determinar onde cada espaço de trabalho específico é armazenado, seja no servidor do Data Workbench, na máquina local ou em ambos.
title: Controle de versão de arquivo
uuid: 5e7430f3-1425-41d2-828b-bc8f5786bf3b
exl-id: 82a70d51-a95c-4ddd-8d3c-cd0364940693
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 2%

---

# Controle de versão de arquivo{#file-versioning}

{{eol}}

A área de trabalho facilita determinar onde cada espaço de trabalho específico é armazenado, seja no servidor do Data Workbench, na máquina local ou em ambos.

## Identificação de versões de arquivo {#section-d555c96b016344f19b356c12213dd2a9}

**Servidor**

Um espaço de trabalho de servidor é armazenado no servidor do Data Workbench conectado e está disponível para todos os usuários que têm acesso a esse perfil e guia. Um espaço de trabalho de servidor é exibido como uma única miniatura.

![](assets/wsp_thumb_server.png)

Os espaços de trabalho do servidor são armazenados por padrão na subpasta apropriada na pasta Espaços de trabalho no servidor do Data Workbench conectado.

**Local**

Um espaço de trabalho local é a versão local de um espaço de trabalho de servidor. Um espaço de trabalho local é exibido como duas miniaturas sobrepostas. A miniatura na parte superior inicialmente é cercada por um brilho, o que indica que as alterações recentes foram feitas localmente na área de trabalho do servidor. Esse brilho se dissipa com o tempo.

![](assets/wsp_thumb_local.png)

Os espaços de trabalho locais são armazenados por padrão na variável [!DNL User\working profile name\Workspaces\tab] pasta de nome no diretório de instalação do Data Workbench (ou Insight).

>[!NOTE]
>
>Quando tiver uma versão local de um espaço de trabalho do servidor, você deverá reverter para a versão do servidor antes de baixar uma versão atualizada do espaço de trabalho do servidor. Para reverter para a versão do servidor sem alterações locais, clique com o botão direito do mouse na miniatura do espaço de trabalho local e clique em **[!UICONTROL Revert to server version]**.

**Usuário**

Um espaço de trabalho de usuário é um espaço de trabalho que foi criado em e existe somente no computador local. Um espaço de trabalho do usuário é exibido como uma única miniatura com um contorno pontilhado de um espaço de trabalho em branco atrás dele, indicando que não há um espaço de trabalho de origem no servidor do Data Workbench conectado.

![](assets/wsp_thumb_user.png)

Os espaços de trabalho do usuário são armazenados por padrão na pasta User\*working profile name*\Workspaces\*tab name* no diretório de instalação do Insight.
