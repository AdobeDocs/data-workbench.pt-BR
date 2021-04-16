---
description: Antes que o painel possa operar, você deve permitir que ele acesse o SQL Server.
title: Configurar o SQL Server
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
exl-id: 16116cc8-f539-4cf0-ab1d-f2bddd39b38c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%

---

# Configurar o SQL Server{#configuring-the-sql-server}

Antes que o painel possa operar, você deve permitir que ele acesse o SQL Server.

1. Abra o SQL Management Studio como um Administrador.
1. Adicione um novo logon clicando com o botão direito do mouse em **[!UICONTROL Logins]** e selecionando **[!UICONTROL New Login]**.
1. Insira o nome completo da identidade do pool de aplicativos.

   Por padrão, a identidade do pool de aplicativos é nomeada após o pool de aplicativos. Se você escolher `dashboard`, a identidade será chamada de `IIS AppPool\dashboard`. 1. Selecione **[!UICONTROL Server Roles]** e verifique a função **[!UICONTROL dbcreator]**.
1. Clique em **[!UICONTROL OK]** para adicionar o novo usuário.
