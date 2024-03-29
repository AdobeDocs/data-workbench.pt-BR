---
description: Instruções para desinstalar o servidor Insight, Transformar ou Repetidor.
title: Desinstalar o software
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
exl-id: 3ba5e5e3-c1a2-4ecb-9f88-a3fe923837e7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 4%

---

# Desinstalar o software{#uninstalling-your-software}

{{eol}}

Instruções para desinstalar o servidor Insight, Transformar ou Repetidor.

## Desinstalar o Adobe do servidor Insight {#section-7d7befe672854df79bb6c28ec02f6670}

1. Cancele o registro da variável [!DNL Insight Server] Serviço Windows.

   1. Abra um prompt de comando e navegue até o subdiretório bin, na pasta onde você instalou o [!DNL Insight Server].

      Exemplo: [!DNL C:\Adobe\Server\bin]

   1. No prompt de comando, execute o seguinte comando para pará-lo e cancelar o registro como um serviço no Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Exclua o [!DNL Insight Server] diretório de instalação.

## Desinstalar Transformar {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. Use as etapas a seguir para atualizar o [!DNL profile.cfg] arquivo para cada perfil com o qual você estava usando [!DNL Transform].

   1. Abra o [!DNL Profile Manager].
   1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL profile.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece no [!DNL User] coluna.

   1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. O [!DNL profile.cfg] será exibida.

   1. No [!DNL profile.cfg] , exclua a [!DNL Transform] entrada de perfil do vetor Diretórios .

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. No [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção de [!DNL profile.cfg] no [!DNL User] e, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Exclua o [!DNL Transform] da pasta de [!DNL Profiles] na sua pasta [!DNL Insight Server] diretório de instalação.

## Desinstalar o Repetidor {#section-2f94141d956749d88f549dbea26e5272}

1. Cancele o registro da variável [!DNL Repeater] Serviço Windows.

   1. Abra um prompt de comando e navegue até o subdiretório bin, na pasta onde você instalou o [!DNL Repeater].

      Exemplo: [!DNL D:\Adobe\Repeater\bin]

   1. No prompt de comando, execute o seguinte comando para pará-lo e cancelar o registro como um serviço no Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Exclua o [!DNL Repeater] diretório de instalação.
