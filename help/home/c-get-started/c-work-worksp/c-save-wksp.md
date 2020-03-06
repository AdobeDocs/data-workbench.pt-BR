---
description: Por padrão, fechar um espaço de trabalho desbloqueado salva quaisquer alterações feitas no espaço de trabalho.
solution: Analytics
title: Salvar um espaço de trabalho
topic: Data workbench
uuid: 166f9ef8-c2c4-4dfc-8d7d-453650bee6b8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Salvar um espaço de trabalho{#save-a-workspace}

Por padrão, fechar um espaço de trabalho desbloqueado salva quaisquer alterações feitas no espaço de trabalho.

Se o espaço de trabalho for um espaço de trabalho do servidor, suas alterações serão salvas apenas localmente, a menos que você salve especificamente o espaço de trabalho atualizado no servidor do Análise de big data. Para obter mais informações sobre espaços de trabalho bloqueados, consulte [Desbloquear um espaço de trabalho](../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).

## Salvar um espaço de trabalho localmente {#section-3f331c880f1a490c96844103c2432d61}

O local de salvamento padrão é a pasta name\Workspaces\tab name **** User\profile no diretório de instalação do Análise de big data. Por exemplo, se você estiver trabalhando com o perfil Filmes e salvar um espaço de trabalho localmente na [!UICONTROL Custom] guia, o espaço de trabalho será salvo na pasta **User\Movies\Workspaces\Custom** no diretório de instalação do Análise de big data.

**Para salvar alterações em um espaço de trabalho**

* No espaço de trabalho, clique em **[!UICONTROL File]**, em seguida, **[!UICONTROL Save]**.

**Para salvar um espaço de trabalho existente como um novo espaço de trabalho**

1. Na [!DNL Worktop] guia desejada, clique na miniatura do espaço de trabalho que deseja exibir.
1. No espaço de trabalho, clique em **[!UICONTROL File]** e, em seguida, clique em **[!UICONTROL Save Copy As]**.
1. Na caixa de [!DNL Save Workspace As] diálogo, especifique o nome e o local onde deseja salvar o espaço de trabalho copiado e clique em **[!UICONTROL Save]**.

## Salvar um espaço de trabalho no servidor da Análise de big data {#section-65a23da852ee4186880e002f7c87ea81}

>[!NOTE]
>
>Somente os usuários com as permissões apropriadas podem salvar espaços de trabalho no servidor do Análise de big data. Para obter mais informações, entre em contato com o administrador do sistema.

Salvar espaços de trabalho no servidor da Análise de big data conectado também é chamado de publicar um espaço de trabalho, pois disponibiliza o espaço de trabalho para outros usuários. Por padrão, os espaços de trabalho são salvos no nome **\Workspaces\*nome da guia* do servidor do Análise de big data. Por exemplo, se você estiver trabalhando com o perfil Filmes e salvar um espaço de trabalho no servidor Análise de big data conectado da [!DNL Custom] guia, o espaço de trabalho será salvo no diretório Movies\Workspaces\Custom folder of the Data Workbench server.

**Para salvar um espaço de trabalho no servidor da Análise de big data**

* Na [!DNL Worktop] guia desejada, clique com o botão direito do mouse na miniatura do espaço de trabalho que deseja salvar no servidor do Análise de big data e clique em **[!UICONTROL Save to server]**.

![](assets/mnu_workspaceManager_SaveToServerwksp.png)
