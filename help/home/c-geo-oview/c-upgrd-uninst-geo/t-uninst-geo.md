---
description: Etapas para desinstalar o Data WorkbenchGeografia.
title: Desinstalar a Geografia do Data Workbench
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
exl-id: e3898423-3b28-4786-834a-1d1ff9deb7c6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 4%

---

# Desinstalar a Geografia do Data Workbench{#uninstalling-data-workbench-geography}

Etapas para desinstalar o Data WorkbenchGeografia.

>[!NOTE]
>
>Se o perfil com o qual você está usando o Data Workbench [!DNL Geography] estiver em execução em um cluster de servidores do Data Workbench, desinstale o perfil [!DNL Geography] do servidor principal do Data Workbench no cluster.

1. Use as etapas a seguir para atualizar o arquivo [!DNL profile.cfg] para cada perfil com o qual você estava usando o Data Workbench [!DNL Geography].

   1. Abra o [!DNL Profile Manager].
   1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL profile.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece na coluna [!DNL User].

   1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. A janela [!DNL profile.cfg] é exibida.

   1. Na janela [!DNL profile.cfg], exclua a entrada de perfil [!DNL Geography] do vetor [!DNL Directories].

   1. Se você tiver usado um serviço de dados, exclua a entrada de perfil [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] do vetor [!DNL Directories].

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. No [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção de [!DNL profile.cfg] na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***.

1. Exclua a pasta Geografia da pasta Perfis no diretório de instalação do servidor do Data Workbench.
1. Se você tiver usado um serviço de dados, exclua a pasta Geosintelligence de IP ou Geolocalização de IP da pasta Profiles no diretório de instalação do servidor do Data Workbench.
1. Exclua a pasta Geografia da pasta Pesquisas no diretório de instalação do servidor do Data Workbench.
1. Se você tem usado um serviço de dados, exclua a pasta Geo-intelligence IP ou Geo-location IP da pasta Lookups no diretório de instalação do servidor do Data Workbench.
1. Se você criou novas imagens do terreno, exclua o arquivo [!DNL Terrain Images.cfg] da pasta Componentes no diretório de instalação do servidor do Data Workbench.
