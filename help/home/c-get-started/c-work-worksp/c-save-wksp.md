---
description: Por padrão, fechar um espaço de trabalho desbloqueado salva quaisquer alterações feitas no espaço de trabalho.
title: Salvar um espaço de trabalho
uuid: 166f9ef8-c2c4-4dfc-8d7d-453650bee6b8
exl-id: 0f1052f5-496c-443e-b29d-5973c16ef527
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---

# Salvar um espaço de trabalho{#save-a-workspace}

{{eol}}

Por padrão, fechar um espaço de trabalho desbloqueado salva quaisquer alterações feitas no espaço de trabalho.

Se o espaço de trabalho for um espaço de trabalho de servidor, suas alterações serão salvas somente localmente, a menos que você salve especificamente o espaço de trabalho atualizado no servidor do Data Workbench. Para obter mais informações sobre espaços de trabalho bloqueados, consulte [Desbloquear um espaço de trabalho](../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).

## Salvar um espaço de trabalho localmente {#section-3f331c880f1a490c96844103c2432d61}

O local de salvamento padrão é o **Usuário\nome do perfil\Espaços de trabalho\nome da guia** no diretório de instalação do Data Workbench. Por exemplo, se você estiver trabalhando com o perfil Filmes e salvar um espaço de trabalho localmente da variável [!UICONTROL Custom] , o espaço de trabalho é salvo na guia **User\Movies\Workspaces\Custom** no diretório de instalação do Data Workbench.

**Para salvar alterações em um espaço de trabalho**

* Na área de trabalho, clique em **[!UICONTROL File]**, em seguida **[!UICONTROL Save]**.

**Para salvar um espaço de trabalho existente como um novo espaço de trabalho**

1. No [!DNL Worktop] , clique na miniatura do espaço de trabalho que deseja exibir.
1. Na área de trabalho, clique em **[!UICONTROL File]**, depois clique em **[!UICONTROL Save Copy As]**.
1. No [!DNL Save Workspace As] , especifique o nome e o local onde deseja salvar o espaço de trabalho copiado e clique em **[!UICONTROL Save]**.

## Salvar um espaço de trabalho no servidor do Data Workbench {#section-65a23da852ee4186880e002f7c87ea81}

>[!NOTE]
>
>Somente usuários com as permissões apropriadas podem salvar espaços de trabalho no servidor do Data Workbench. Para obter mais informações, entre em contato com o administrador do sistema.

Salvar espaços de trabalho no servidor do Data Workbench conectado também é chamado de publicar um espaço de trabalho porque disponibiliza o espaço de trabalho para outros usuários. Por padrão, os espaços de trabalho são salvos na variável *nome do perfil de trabalho*\Workspace\*nome da guia* pasta do servidor do Data Workbench. Por exemplo, se você estiver trabalhando com o perfil Filmes e salvar um espaço de trabalho no servidor do Data Workbench conectado da variável [!DNL Custom] , o espaço de trabalho é salvo na pasta Filmes\Espaços de trabalho\Personalizado do servidor do Data Workbench.

**Para salvar um espaço de trabalho no servidor do Data Workbench**

* No [!DNL Worktop] clique com o botão direito do mouse na miniatura do espaço de trabalho que deseja salvar no servidor do Data Workbench e clique em **[!UICONTROL Save to server]**.

![](assets/mnu_workspaceManager_SaveToServerwksp.png)
