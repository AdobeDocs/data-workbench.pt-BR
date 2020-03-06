---
description: Na pasta Espaços de trabalho do diretório de instalação do Análise de big data, um arquivo folder.lock especifica se os espaços de trabalho dessa pasta específica estão bloqueados, enquanto um arquivo nome.lock do espaço de trabalho especifica se um espaço de trabalho específico está bloqueado.
solution: Analytics
title: Arquivos Folder.lock e workspace.lock
topic: Data workbench
uuid: d4c69e16-0596-4542-854f-bc614167ae80
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Arquivos Folder.lock e workspace.lock{#folder-lock-and-workspace-lock-files}

Na pasta Espaços de trabalho do diretório de instalação do Análise de big data, um arquivo folder.lock especifica se os espaços de trabalho dessa pasta específica estão bloqueados, enquanto um arquivo nome.lock do espaço de trabalho especifica se um espaço de trabalho específico está bloqueado.

Ao bloquear pastas inteiras, você pode bloqueá-las no nível da pasta Espaços de trabalho ou no nível da subpasta (guia). Você também pode bloquear ou desbloquear todas as pastas (no nível de pasta de espaços de trabalho) e especificar as exceções para subpastas específicas (usando [!DNL folder.lock] arquivos) ou espaços de trabalho específicos (usando arquivos *de espaço de trabalho name*.lock).

O exemplo a seguir [!DNL Profile Manager] destaca três elementos:

* Um [!DNL folder.lock] arquivo para a pasta Espaços de Trabalho principal
* Um [!DNL Monthly Numbers.lock] arquivo para o arquivo do [!DNL Monthly Numbers.vw] espaço de trabalho

* Um [!DNL folder.lock] arquivo para a subpasta Espaços de trabalho\Personalizado

![](assets/wsp_Locking_lockFiles.png)

Neste exemplo, o [!DNL Workspaces folder.lock] arquivo é definido como bloqueado, o que bloqueia todos os espaços de trabalho nesta instância do Análise de big data. O arquivo de subpasta Espaços de trabalho\Personalizado [!DNL folder.lock] está definido como desbloqueado, o que desbloqueia todos os espaços de trabalho na [!DNL Custom] guia. Finalmente, o [!DNL Monthly Numbers.lock] arquivo está definido como bloqueado, o que bloqueia a área de trabalho Números mensais.

## Criação de arquivos .lock {#section-c4f78b4b43c347368a376904effb41d2}

Você pode criar um [!DNL new folder.lock] arquivo usando a [!DNL Create menu] opção no [!DNL Profile Manager] ou no [!DNL Workspaces Manager]. Você também pode criar um arquivo name [!DNL folder.lock] .lock ou de *espaço de trabalho copiando e colando um* arquivo existente na pasta apropriada, alterando o nome do arquivo (somente para arquivos name [!DNL .lock] .lock de ** espaço de trabalho) e alterando a configuração no arquivo, se necessário.

**Para criar um novo arquivo folder.lock**

1. Na Análise de big data, abra o arquivo clicando com o botão direito do mouse [!DNL Workspaces Manager] em um espaço de trabalho e clicando em **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**.
1. Clique na pasta para a qual deseja criar um [!DNL folder.lock] arquivo.
1. Na [!DNL User] coluna da pasta, clique com o botão direito do mouse na célula e clique em **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. Um [!DNL new folder.lock] arquivo é exibido. [!DNL New folder.lock] por padrão, os arquivos são definidos como [desbloqueados] .
1. (Opcional) Se você precisar alterar a configuração no arquivo:

   1. Clique com o botão direito do mouse na marca de seleção do arquivo.
   1. Clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O [!DNL folder.lock] arquivo é aberto.

   1. Altere a configuração para [bloqueada].
   1. Salve e feche o arquivo.

1. Para tornar essa configuração a configuração para todos os usuários que trabalham com o mesmo perfil de trabalho, clique com o botão direito do mouse na marca de seleção do arquivo e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Os espaços de trabalho desta pasta agora estão bloqueados ou desbloqueados de acordo com a configuração no novo arquivo.

**Para criar um arquivo .lock a partir de um arquivo existente**

1. No [!DNL Profile Manager] ou [!DNL Workspaces Manager], clique com o botão direito do mouse na marca de seleção de um [!DNL .lock] arquivo existente e clique em **[!UICONTROL Copy]**.
1. Na [!DNL User] coluna da pasta na qual você deseja colar o [!DNL .lock] arquivo, clique com o botão direito do mouse na célula e clique em **[!UICONTROL Paste]**.
1. Se esse arquivo for usado para bloquear um espaço de trabalho individual, clique com o botão direito do mouse na marca de seleção do [!DNL .lock] arquivo na [!DNL User] coluna e altere seu nome no [!DNL File] campo para corresponder ao nome do espaço de trabalho que você deseja bloquear.

   Por exemplo, para bloquear a área de trabalho, você deve nomear o arquivo como &quot; [!DNL Monthly Numbers.vw] [!DNL Monthly Numbers.lock]&quot;.Se esse arquivo for usado para bloquear um espaço de trabalho individual, clique com o botão direito do mouse na marca de seleção do [!DNL .lock] arquivo na [!DNL User] coluna e altere seu nome no [!DNL File] campo para corresponder ao nome do espaço de trabalho que você deseja bloquear. Por exemplo, para bloquear a área de trabalho, você deve nomear o arquivo como &quot; [!DNL Monthly Numbers.vw] [!DNL Monthly Numbers.lock]&quot;.

1. Para alterar a configuração no arquivo:

   1. Clique com o botão direito do mouse na marca de seleção do arquivo.
   1. Clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O [!DNL .lock] arquivo é aberto.

   1. Altere a configuração para [bloqueada] ou [desbloqueada].
   1. Salve e feche o arquivo.

1. Para tornar essa configuração a configuração para todos os usuários que trabalham com o mesmo perfil de trabalho, clique com o botão direito do mouse na marca de seleção do arquivo e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Os espaços de trabalho selecionados agora são bloqueados ou desbloqueados de acordo com a configuração no novo arquivo.
