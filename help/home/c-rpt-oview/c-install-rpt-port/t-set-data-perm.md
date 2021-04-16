---
description: Para habilitar o portal de relatórios para gravar no banco de dados que contém as informações necessárias para autenticar usuários, você deve definir as permissões apropriadas para o banco de dados.
title: Definir permissões para o banco de dados
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
exl-id: 901cf702-633c-4660-b1bd-4937d0c3293c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%

---

# Definir permissões para o banco de dados{#set-permissions-for-the-database}

Para habilitar o portal de relatórios para gravar no banco de dados que contém as informações necessárias para autenticar usuários, você deve definir as permissões apropriadas para o banco de dados.

1. Na máquina em que o IIS está sendo executado, navegue até \*PortalName*\data\users.mdb.
1. Clique com o botão direito do mouse no arquivo **[!UICONTROL users.mdb]** e selecione **[!UICONTROL Properties]**.
1. Na guia [!DNL Security], em Grupos ou nomes de usuário, clique em **[!UICONTROL Users]**.
1. Em [!DNL Permission for User], na linha Gravar, selecione **[!UICONTROL Allow]**.
1. Clique em **[!UICONTROL OK]** e feche a caixa de diálogo [!DNL Properties].
