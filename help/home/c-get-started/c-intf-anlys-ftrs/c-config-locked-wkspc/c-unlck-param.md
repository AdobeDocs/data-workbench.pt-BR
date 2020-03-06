---
description: O parâmetro Unlock no arquivo Insight.cfg do usuário especifica se o usuário tem permissão para desbloquear temporariamente espaços de trabalho bloqueados para edição.
solution: Analytics
title: Definir o parâmetro de desbloqueio
topic: Data workbench
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definir o parâmetro de desbloqueio{#set-the-unlock-parameter}

O parâmetro Unlock no arquivo Insight.cfg do usuário especifica se o usuário tem permissão para desbloquear temporariamente espaços de trabalho bloqueados para edição.

Se o parâmetro Desbloquear já estiver presente no [!DNL Insight.cfg] arquivo do usuário, você poderá editar o parâmetro usando o Análise de big data. Se ele ainda não estiver presente no [!DNL Insight.cfg] arquivo do usuário, adicione-o ao arquivo usando um editor de texto, como o Bloco de notas.

**Para definir um[!DNL Unlock]parâmetro existente no arquivo Insight.cfg**

1. Em um espaço de trabalho, clique com o botão direito do mouse em **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. O [!DNL Insight.cfg] arquivo é aberto.
1. Para o parâmetro Unlock, digite true ou false. True permite que o usuário desbloqueie temporariamente qualquer espaço de trabalho bloqueado, enquanto false não desbloqueia.
1. Para salvar as alterações de configuração, clique com o botão direito do mouse **[!UICONTROL Insight.cfg (modified)]** na parte superior da janela e clique em **[!UICONTROL Save as Insight.cfg]**.

**Para adicionar o parâmetro Unlock ao arquivo Insight.cfg**

1. Navegue até o diretório de instalação do Análise de big data e abra o [!DNL Insight.cfg] arquivo usando um editor de texto, como o Bloco de notas.
1. Adicione o parâmetro Unlock ao final do arquivo, como no exemplo a seguir:

[!DNL Unlock = bool: false]

1. Defina o valor como true ou false. True permite que o usuário desbloqueie temporariamente qualquer espaço de trabalho bloqueado, enquanto false não desbloqueia.
1. Salve e feche o arquivo.

