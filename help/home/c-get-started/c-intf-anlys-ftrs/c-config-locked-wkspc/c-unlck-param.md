---
description: O parâmetro Unlock no arquivo Insight.cfg de um usuário especifica se ele tem permissão para desbloquear temporariamente espaços de trabalho bloqueados para edição.
title: Definir o parâmetro de desbloqueio
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
exl-id: 5eda919f-4cfe-4692-9dbf-f7cf64fde1de
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 3%

---

# Definir o parâmetro de desbloqueio{#set-the-unlock-parameter}

O parâmetro Unlock no arquivo Insight.cfg de um usuário especifica se ele tem permissão para desbloquear temporariamente espaços de trabalho bloqueados para edição.

Se o parâmetro Desbloquear já estiver presente no arquivo [!DNL Insight.cfg] do usuário, você poderá editar o parâmetro usando o Data Workbench. Se ele ainda não estiver presente no arquivo [!DNL Insight.cfg] do usuário, será necessário adicioná-lo ao arquivo usando um editor de texto, como o Bloco de notas.

**Para definir um  [!DNL Unlock] parâmetro existente no arquivo Insight.cfg**

1. Em um espaço de trabalho, clique com o botão direito do mouse em **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. O arquivo [!DNL Insight.cfg] é aberto.
1. Para o parâmetro Desbloquear , digite verdadeiro ou falso. True permite que o usuário desbloqueie temporariamente qualquer espaço de trabalho bloqueado, enquanto false não desbloqueia.
1. Para salvar as alterações de configuração, clique com o botão direito do mouse **[!UICONTROL Insight.cfg (modified)]** na parte superior da janela e clique em **[!UICONTROL Save as Insight.cfg]**.

**Para adicionar o parâmetro Desbloquear ao arquivo Insight.cfg**

1. Navegue até o diretório de instalação do Data Workbench e abra o arquivo [!DNL Insight.cfg] usando um editor de texto, como o Bloco de Notas.
1. Adicione o parâmetro Unlock ao final do arquivo, como no exemplo a seguir:

[!DNL Unlock = bool: false]

1. Defina o valor como true ou false. True permite que o usuário desbloqueie temporariamente qualquer espaço de trabalho bloqueado, enquanto false não desbloqueia.
1. Salve e feche o arquivo.
