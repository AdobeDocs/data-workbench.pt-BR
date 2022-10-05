---
description: Etapas para desinstalar o Data WorkbenchGeografia.
title: Desinstalar a Geografia do Data Workbench
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
exl-id: e3898423-3b28-4786-834a-1d1ff9deb7c6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 4%

---

# Desinstalar a Geografia do Data Workbench{#uninstalling-data-workbench-geography}

{{eol}}

Etapas para desinstalar o Data WorkbenchGeografia.

>[!NOTE]
>
>Se o perfil com o qual você está usando o Data Workbench [!DNL Geography] está em execução em um cluster de servidores do Data Workbench, desinstale o [!DNL Geography] perfil do servidor do Data Workbench principal no cluster.

1. Use as etapas a seguir para atualizar o [!DNL profile.cfg] arquivo para cada perfil com o qual você estava usando o Data Workbench [!DNL Geography].

   1. Abra o [!DNL Profile Manager].
   1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL profile.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece no [!DNL User] coluna.

   1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. O [!DNL profile.cfg] será exibida.

   1. No [!DNL profile.cfg] , exclua a [!DNL Geography] entrada de perfil do [!DNL Directories] vetor.

   1. Se tiver usado um serviço de dados, exclua o [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] entrada de perfil do [!DNL Directories] vetor.

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. No [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção de [!DNL profile.cfg] no [!DNL User] e, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Exclua a pasta Geografia da pasta Perfis no diretório de instalação do servidor do Data Workbench.
1. Se você tiver usado um serviço de dados, exclua a pasta Geosintelligence de IP ou Geolocalização de IP da pasta Profiles no diretório de instalação do servidor do Data Workbench.
1. Exclua a pasta Geografia da pasta Pesquisas no diretório de instalação do servidor do Data Workbench.
1. Se você tem usado um serviço de dados, exclua a pasta Geo-intelligence IP ou Geo-location IP da pasta Lookups no diretório de instalação do servidor do Data Workbench.
1. Se você criou novas imagens do terreno, exclua o [!DNL Terrain Images.cfg] da pasta Componentes no diretório de instalação do servidor do Data Workbench.
