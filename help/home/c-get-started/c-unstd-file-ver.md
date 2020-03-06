---
description: A área de trabalho facilita determinar onde cada espaço de trabalho específico é armazenado, seja no servidor da Análise de big data, na máquina local ou em ambos.
solution: Analytics
title: Controle de versão de arquivo
topic: Data workbench
uuid: 5e7430f3-1425-41d2-828b-bc8f5786bf3b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Controle de versão de arquivo{#file-versioning}

A área de trabalho facilita determinar onde cada espaço de trabalho específico é armazenado, seja no servidor da Análise de big data, na máquina local ou em ambos.

## Como identificar versões de arquivo {#section-d555c96b016344f19b356c12213dd2a9}

**Servidor**

Uma área de trabalho do servidor é armazenada no servidor Análise de big data conectado e está disponível para todos os usuários que têm acesso a esse perfil e guia. Uma área de trabalho do servidor é exibida como uma única miniatura.

![](assets/wsp_thumb_server.png)

Os espaços de trabalho do servidor são armazenados por padrão na subpasta apropriada dentro da pasta Espaços de trabalho no servidor do Análise de big data conectado.

**Local**

Um espaço de trabalho local é a versão local de um espaço de trabalho do servidor. Um espaço de trabalho local é exibido como duas miniaturas sobrepostas. A miniatura na parte superior é cercada por um brilho, o que indica que alterações recentes foram feitas localmente na área de trabalho do servidor. Este brilho se dissipa com o tempo.

![](assets/wsp_thumb_local.png)

Os espaços de trabalho locais são armazenados por padrão na pasta de [!DNL User\working profile name\Workspaces\tab] nomes no diretório de instalação do Análise de big data (ou Insight).

>[!NOTE]
>
>Quando tiver uma versão local de um espaço de trabalho do servidor, você deverá reverter para a versão do servidor antes de baixar uma versão atualizada do espaço de trabalho do servidor. Para reverter para a versão do servidor sem alterações locais, clique com o botão direito do mouse na miniatura do espaço de trabalho local e clique em **[!UICONTROL Revert to server version]**.

**Usuário**

Uma área de trabalho do usuário é uma área de trabalho que foi criada e existe somente na máquina local. Uma área de trabalho do usuário é exibida como uma única miniatura com um contorno pontilhado de uma área de trabalho em branco atrás dela, indicando que não há nenhum espaço de trabalho de origem no servidor da Análise de big data conectado.

![](assets/wsp_thumb_user.png)

Os espaços de trabalho do usuário são armazenados por padrão na pasta User\*working profile name*\Workspaces\*tab name* no diretório de instalação do Insight.
