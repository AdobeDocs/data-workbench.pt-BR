---
description: Para habilitar o Portal de relatórios para gravar no banco de dados que contém as informações necessárias para autenticar os usuários, é necessário definir as permissões apropriadas para o banco de dados.
solution: Analytics
title: Definir permissões para o banco de dados
topic: Data workbench
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definir permissões para o banco de dados{#set-permissions-for-the-database}

Para habilitar o Portal de relatórios para gravar no banco de dados que contém as informações necessárias para autenticar os usuários, é necessário definir as permissões apropriadas para o banco de dados.

1. Na máquina em que o IIS está sendo executado, navegue até \*PortalName*\data\users.mdb.
1. Clique com o botão direito do mouse no **[!UICONTROL users.mdb]** arquivo e selecione **[!UICONTROL Properties]**.
1. Na [!DNL Security] guia Grupos ou nomes de usuários, clique em **[!UICONTROL Users]**.
1. Na [!DNL Permission for User]linha Gravar, selecione **[!UICONTROL Allow]**.
1. Clique **[!UICONTROL OK]** e feche a caixa de [!DNL Properties] diálogo.
