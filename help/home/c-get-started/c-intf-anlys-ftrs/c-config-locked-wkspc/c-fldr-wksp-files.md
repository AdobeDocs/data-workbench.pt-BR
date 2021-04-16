---
description: Na pasta Espaços de trabalho do diretório de instalação do Data Workbench, um arquivo folder.lock especifica se os espaços de trabalho nessa pasta específica estão bloqueados, enquanto um arquivo workspace name.lock especifica se um espaço de trabalho específico está bloqueado.
title: Arquivos Folder.lock e workspace.lock
uuid: d4c69e16-0596-4542-854f-bc614167ae80
exl-id: 980b8692-8aa5-481f-b6bc-33836d8a3a76
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 1%

---

# Arquivos Folder.lock e workspace.lock{#folder-lock-and-workspace-lock-files}

Na pasta Espaços de trabalho do diretório de instalação do Data Workbench, um arquivo folder.lock especifica se os espaços de trabalho nessa pasta específica estão bloqueados, enquanto um arquivo workspace name.lock especifica se um espaço de trabalho específico está bloqueado.

Ao bloquear pastas inteiras, você pode bloqueá-las no nível da pasta Espaços de trabalho ou no nível da subpasta (guia). Você também pode bloquear ou desbloquear todas as suas pastas (no nível de pasta de espaços de trabalho) e, em seguida, especificar as exceções para subpastas específicas (usando arquivos [!DNL folder.lock]) ou espaços de trabalho específicos (usando arquivos *workspace name*.lock).

O exemplo a seguir do [!DNL Profile Manager] destaca três elementos:

* Um arquivo [!DNL folder.lock] para a pasta de espaços de trabalho principal
* Um arquivo [!DNL Monthly Numbers.lock] para o arquivo do espaço de trabalho [!DNL Monthly Numbers.vw]

* Um arquivo [!DNL folder.lock] para a subpasta Espaços de trabalho\Personalizado

![](assets/wsp_Locking_lockFiles.png)

Neste exemplo, o arquivo [!DNL Workspaces folder.lock] é definido como bloqueado, bloqueando todos os espaços de trabalho nesta instância do Data Workbench. O arquivo de subpasta [!DNL folder.lock] Espaços de trabalho\Personalizados está definido como desbloqueado, o que desbloqueia todos os espaços de trabalho na guia [!DNL Custom]. Finalmente, o arquivo [!DNL Monthly Numbers.lock] é definido como bloqueado, bloqueando o espaço de trabalho Números mensais .

## Criar arquivos .lock {#section-c4f78b4b43c347368a376904effb41d2}

Você pode criar um arquivo [!DNL new folder.lock] usando a opção [!DNL Create menu] no [!DNL Profile Manager] ou no [!DNL Workspaces Manager]. Você também pode criar um arquivo [!DNL folder.lock] ou *workspace name*.lock copiando e colando um arquivo [!DNL .lock] existente na pasta apropriada, alterando o nome do arquivo (somente para arquivos *workspace name*.lock) e alterando a configuração no arquivo, se necessário.

**Para criar um novo arquivo folder.lock**

1. No Data Workbench, abra o [!DNL Workspaces Manager] clicando com o botão direito do mouse em um espaço de trabalho e clicando em **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**.
1. Clique na pasta para a qual deseja criar um arquivo [!DNL folder.lock].
1. Na coluna [!DNL User] dessa pasta, clique com o botão direito do mouse na célula e clique em **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. Um arquivo [!DNL new folder.lock] é exibido. [!DNL New folder.lock] por padrão, os arquivos são definidos como  [] desbloqueados.
1. (Opcional) Se você precisar alterar a configuração no arquivo :

   1. Clique com o botão direito do mouse na marca de seleção do arquivo.
   1. Clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O arquivo [!DNL folder.lock] é aberto.

   1. Altere a configuração para [locked].
   1. Salve e feche o arquivo.

1. Para tornar essa configuração a configuração para todos os usuários que trabalham com o mesmo perfil de trabalho, clique com o botão direito do mouse na marca de seleção do arquivo e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.

Os espaços de trabalho nesta pasta agora são bloqueados ou desbloqueados de acordo com a configuração no novo arquivo.

**Para criar um arquivo .lock a partir de um arquivo existente**

1. No [!DNL Profile Manager] ou [!DNL Workspaces Manager], clique com o botão direito do mouse na marca de seleção de um arquivo [!DNL .lock] existente e clique em **[!UICONTROL Copy]**.
1. Na coluna [!DNL User] da pasta em que deseja colar o arquivo [!DNL .lock], clique com o botão direito do mouse na célula e clique em **[!UICONTROL Paste]**.
1. Se esse arquivo for usado para bloquear um espaço de trabalho individual, clique com o botão direito do mouse na marca de seleção do arquivo [!DNL .lock] na coluna [!DNL User] e altere seu nome no campo [!DNL File] para corresponder ao nome do espaço de trabalho que deseja bloquear.

   Por exemplo, para bloquear o espaço de trabalho [!DNL Monthly Numbers.vw], você nomearia o arquivo como &quot;[!DNL Monthly Numbers.lock]&quot;.Se esse arquivo for usado para bloquear um espaço de trabalho individual, clique com o botão direito do mouse na marca de seleção do arquivo [!DNL .lock] na coluna [!DNL User] e altere seu nome no campo [!DNL File] para corresponder ao nome do espaço de trabalho que deseja bloquear. Por exemplo, para bloquear o espaço de trabalho [!DNL Monthly Numbers.vw], você nomearia o arquivo como &quot;[!DNL Monthly Numbers.lock]&quot;.

1. Para alterar a configuração no arquivo :

   1. Clique com o botão direito do mouse na marca de seleção do arquivo.
   1. Clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O arquivo [!DNL .lock] é aberto.

   1. Altere a configuração para [locked] ou [unlocked].
   1. Salve e feche o arquivo.

1. Para tornar essa configuração a configuração para todos os usuários que trabalham com o mesmo perfil de trabalho, clique com o botão direito do mouse na marca de seleção do arquivo e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.

Os espaços de trabalho selecionados agora estão bloqueados ou desbloqueados de acordo com a configuração no novo arquivo.
