---
description: O parâmetro Unlock no arquivo Insight.cfg de um usuário especifica se ele tem permissão para desbloquear temporariamente espaços de trabalho bloqueados para edição.
title: Definir o parâmetro de desbloqueio
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
exl-id: 5eda919f-4cfe-4692-9dbf-f7cf64fde1de
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 3%

---

# Definir o parâmetro de desbloqueio{#set-the-unlock-parameter}

{{eol}}

O parâmetro Unlock no arquivo Insight.cfg de um usuário especifica se ele tem permissão para desbloquear temporariamente espaços de trabalho bloqueados para edição.

Se o parâmetro Desbloquear já estiver presente no [!DNL Insight.cfg] , é possível editar o parâmetro usando o Data Workbench. Se ainda não estiver presente no [!DNL Insight.cfg] , você deve adicioná-lo ao arquivo usando um editor de texto, como o Bloco de notas.

**Para definir um [!DNL Unlock] no arquivo Insight.cfg**

1. Em um espaço de trabalho, clique com o botão direito do mouse **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. O [!DNL Insight.cfg] é aberto.
1. Para o parâmetro Desbloquear , digite verdadeiro ou falso. True permite que o usuário desbloqueie temporariamente qualquer espaço de trabalho bloqueado, enquanto false não desbloqueia.
1. Para salvar as alterações de configuração, clique com o botão direito do mouse **[!UICONTROL Insight.cfg (modified)]** na parte superior da janela e clique em **[!UICONTROL Save as Insight.cfg]**.

**Para adicionar o parâmetro Desbloquear ao arquivo Insight.cfg**

1. Navegue até o diretório de instalação do Data Workbench e abra o [!DNL Insight.cfg] arquivo usando um editor de texto, como o Bloco de notas.
1. Adicione o parâmetro Unlock ao final do arquivo, como no exemplo a seguir:

[!DNL Unlock = bool: false]

1. Defina o valor como true ou false. True permite que o usuário desbloqueie temporariamente qualquer espaço de trabalho bloqueado, enquanto false não desbloqueia.
1. Salve e feche o arquivo.
