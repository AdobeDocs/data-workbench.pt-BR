---
description: Antes que o painel possa operar, você deve permitir que ele acesse o SQL Server.
solution: Analytics
title: Configuração do SQL Server
topic: Data workbench
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuração do SQL Server{#configuring-the-sql-server}

Antes que o painel possa operar, você deve permitir que ele acesse o SQL Server.

1. Abra o SQL Management Studio como um Administrador.
1. Adicione um novo logon clicando com o botão direito do mouse **[!UICONTROL Logins]** e selecionando **[!UICONTROL New Login]**.
1. Insira o nome de identidade completo do pool de aplicativos.

   Por padrão, a identidade do pool de aplicativos é nomeada após o pool de aplicativos. Se você escolher `dashboard`, a identidade será nomeada `IIS AppPool\dashboard`. 1. Selecione **[!UICONTROL Server Roles]** e verifique a **[!UICONTROL dbcreator]** função.
1. Click **[!UICONTROL OK]** to add the new user.
