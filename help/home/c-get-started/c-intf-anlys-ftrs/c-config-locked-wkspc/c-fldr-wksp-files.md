---
description: Na pasta Espaços de trabalho do diretório de instalação do Data Workbench, um arquivo folder.lock especifica se os espaços de trabalho nessa pasta específica estão bloqueados, enquanto um arquivo workspace name.lock especifica se um espaço de trabalho específico está bloqueado.
title: Arquivos Folder.lock e workspace.lock
uuid: d4c69e16-0596-4542-854f-bc614167ae80
exl-id: 980b8692-8aa5-481f-b6bc-33836d8a3a76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 1%

---

# Arquivos Folder.lock e workspace.lock{#folder-lock-and-workspace-lock-files}

{{eol}}

Na pasta Espaços de trabalho do diretório de instalação do Data Workbench, um arquivo folder.lock especifica se os espaços de trabalho nessa pasta específica estão bloqueados, enquanto um arquivo workspace name.lock especifica se um espaço de trabalho específico está bloqueado.

Ao bloquear pastas inteiras, você pode bloqueá-las no nível da pasta Espaços de trabalho ou no nível da subpasta (guia). Também é possível bloquear ou desbloquear todas as pastas (no nível de pasta de espaços de trabalho) e especificar as exceções para subpastas específicas (usando [!DNL folder.lock] arquivos) ou espaços de trabalho específicos (usando *nome do espaço de trabalho* arquivos .lock).

O exemplo a seguir da variável [!DNL Profile Manager] destaca três elementos:

* A [!DNL folder.lock] arquivo para a pasta principal Espaços de trabalho
* A [!DNL Monthly Numbers.lock] para o [!DNL Monthly Numbers.vw] arquivo do espaço de trabalho

* A [!DNL folder.lock] arquivo para a subpasta Espaços de Trabalho\Personalizados

![](assets/wsp_Locking_lockFiles.png)

Neste exemplo, a variável [!DNL Workspaces folder.lock] está definido como bloqueado, o que bloqueia todos os espaços de trabalho nesta instância do Data Workbench. A subpasta Espaços de Trabalho\Personalizados [!DNL folder.lock] estiver definido como desbloqueado, o que desbloqueia todos os espaços de trabalho na [!DNL Custom] guia . Finalmente, o [!DNL Monthly Numbers.lock] estiver definido como bloqueado, bloqueando o espaço de trabalho Números mensais .

## Criação de arquivos .lock {#section-c4f78b4b43c347368a376904effb41d2}

Você pode criar um [!DNL new folder.lock] arquivo usando o [!DNL Create menu] na [!DNL Profile Manager] ou [!DNL Workspaces Manager]. Você também pode criar um [!DNL folder.lock] ou *nome do espaço de trabalho* arquivo .lock copiando e colando um arquivo existente [!DNL .lock] para a pasta apropriada, alterando o nome do arquivo (para *nome do espaço de trabalho*.lock (somente arquivos) e alterar a configuração no arquivo, se necessário.

**Para criar um novo arquivo folder.lock**

1. No Data Workbench, abra o [!DNL Workspaces Manager] clicando com o botão direito do mouse em um espaço de trabalho e clicando em **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**.
1. Clique na pasta para a qual deseja criar uma [!DNL folder.lock] arquivo.
1. No [!DNL User] para essa pasta, clique com o botão direito do mouse na célula e clique em **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. A [!DNL new folder.lock] é exibido. [!DNL New folder.lock] os arquivos estão definidos como [desbloqueado] por padrão.
1. (Opcional) Se você precisar alterar a configuração no arquivo :

   1. Clique com o botão direito do mouse na marca de seleção do arquivo.
   1. Clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O [!DNL folder.lock] é aberto.

   1. Altere a configuração para [bloqueado].
   1. Salve e feche o arquivo.

1. Para tornar essa configuração a configuração para todos os usuários que trabalham com o mesmo perfil de trabalho, clique com o botão direito do mouse na marca de seleção do arquivo e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Os espaços de trabalho nesta pasta agora são bloqueados ou desbloqueados de acordo com a configuração no novo arquivo.

**Para criar um arquivo .lock a partir de um arquivo existente**

1. No [!DNL Profile Manager] ou [!DNL Workspaces Manager], clique com o botão direito do mouse na marca de seleção de um [!DNL .lock] e clique em **[!UICONTROL Copy]**.
1. No [!DNL User] para a pasta na qual deseja colar a [!DNL .lock] , clique com o botão direito do mouse na célula e clique em **[!UICONTROL Paste]**.
1. Se esse arquivo for usado para bloquear um espaço de trabalho individual, clique com o botão direito do mouse na marca de seleção para a variável [!DNL .lock] no [!DNL User] e altere seu nome na [!DNL File] para corresponder ao nome do espaço de trabalho que deseja bloquear.

   Por exemplo, para bloquear o [!DNL Monthly Numbers.vw] no espaço de trabalho, você nomearia o arquivo como &quot; [!DNL Monthly Numbers.lock].&quot;Se esse arquivo for usado para bloquear um espaço de trabalho individual, clique com o botão direito do mouse na marca de seleção para a variável [!DNL .lock] no [!DNL User] e altere seu nome na [!DNL File] para corresponder ao nome do espaço de trabalho que deseja bloquear. Por exemplo, para bloquear o [!DNL Monthly Numbers.vw] no espaço de trabalho, você nomearia o arquivo como &quot; [!DNL Monthly Numbers.lock].&quot;

1. Para alterar a configuração no arquivo :

   1. Clique com o botão direito do mouse na marca de seleção do arquivo.
   1. Clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O [!DNL .lock] é aberto.

   1. Altere a configuração para [bloqueado] ou [desbloqueado].
   1. Salve e feche o arquivo.

1. Para tornar essa configuração a configuração para todos os usuários que trabalham com o mesmo perfil de trabalho, clique com o botão direito do mouse na marca de seleção do arquivo e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Os espaços de trabalho selecionados agora estão bloqueados ou desbloqueados de acordo com a configuração no novo arquivo.
