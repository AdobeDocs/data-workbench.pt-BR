---
description: Instruções para desinstalar o Insight Server, Transform ou Repeater.
solution: Insight
title: Desinstalação do software
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Desinstalação do software{#uninstalling-your-software}

Instruções para desinstalar o Insight Server, Transform ou Repeater.

## Desinstalação do Insight Server Adobe {#section-7d7befe672854df79bb6c28ec02f6670}

1. Cancele o registro do serviço do [!DNL Insight Server] Windows.

   1. Abra um prompt de comando e navegue até o subdiretório bin na pasta onde você instalou [!DNL Insight Server].

      Exemplo: [!DNL C:\Adobe\Server\bin]

   1. No prompt de comando, execute o seguinte comando para pará-lo e cancelar o registro como um serviço no Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Exclua o diretório [!DNL Insight Server] de instalação.

## Desinstalação do Transform {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. Use as etapas a seguir para atualizar o [!DNL profile.cfg] arquivo para cada perfil com o qual você estava usando [!DNL Transform].

   1. Abra o [!DNL Profile Manager].
   1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL profile.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção para este arquivo é exibida na [!DNL User] coluna.

   1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. A [!DNL profile.cfg] janela é exibida.

   1. Na [!DNL profile.cfg] janela, exclua a entrada de [!DNL Transform] perfil do vetor Diretórios.

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Na [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção para [!DNL profile.cfg] na [!DNL User] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Exclua a [!DNL Transform] pasta da [!DNL Profiles] pasta no diretório [!DNL Insight Server] de instalação.

## Desinstalação do repetidor {#section-2f94141d956749d88f549dbea26e5272}

1. Cancele o registro do serviço do [!DNL Repeater] Windows.

   1. Abra um prompt de comando e navegue até o subdiretório bin na pasta onde você instalou [!DNL Repeater].

      Exemplo: [!DNL D:\Adobe\Repeater\bin]

   1. No prompt de comando, execute o seguinte comando para pará-lo e cancelar o registro como um serviço no Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Exclua o diretório [!DNL Repeater] de instalação.

