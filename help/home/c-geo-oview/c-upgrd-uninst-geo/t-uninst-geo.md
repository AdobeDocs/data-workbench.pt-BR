---
description: Etapas para desinstalar a análise de big dataGeografia.
solution: Analytics
title: Desinstalação da geografia da análise de big data
topic: Data workbench
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Desinstalação da geografia da análise de big data{#uninstalling-data-workbench-geography}

Etapas para desinstalar a análise de big dataGeografia.

>[!NOTE]
>
>Se o perfil com o qual você está usando a análise de big data [!DNL Geography] estiver sendo executado em um cluster de servidores da análise de big data, desinstale o [!DNL Geography] perfil do servidor da análise de big data mestre no cluster.

1. Use as seguintes etapas para atualizar o [!DNL profile.cfg] arquivo para cada perfil com o qual você estava usando a análise de big data [!DNL Geography].

   1. Abra o [!DNL Profile Manager].
   1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL profile.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção para este arquivo é exibida na [!DNL User] coluna.

   1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. A [!DNL profile.cfg] janela é exibida.

   1. Na [!DNL profile.cfg] janela, exclua a entrada do [!DNL Geography] perfil do [!DNL Directories] vetor.

   1. Se você tiver usado um serviço de dados, exclua a entrada [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] do perfil do [!DNL Directories] vetor.

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Na [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção para [!DNL profile.cfg] na [!DNL User] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Exclua a pasta Geografia da pasta Perfis no diretório de instalação do servidor da análise de big data.
1. Se você tiver usado um serviço de dados, exclua a pasta IP Geo-Intelligence ou IP Geo-location da pasta Perfis no diretório de instalação do servidor da análise de big data.
1. Exclua a pasta Geografia da pasta Pesquisas no diretório de instalação do servidor da análise de big data.
1. Se você tiver usado um serviço de dados, exclua a pasta IP Geo-Intelligence ou IP Geo-location da pasta Lookups no diretório de instalação do servidor da análise de big data.
1. Se você tiver criado novas imagens de terreno, exclua o [!DNL Terrain Images.cfg] arquivo da pasta Componentes no diretório de instalação do servidor da análise de big data.
