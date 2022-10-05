---
description: Etapas para reenviar relatórios por email.
title: Reenviar relatórios por email
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
exl-id: eb37fd3e-6e7b-4672-bcf0-fffa9f10997d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 6%

---

# Reenviar relatórios por email{#resending-reports-by-email}

{{eol}}

Etapas para reenviar relatórios por email.

Se a variável **[!UICONTROL Allow Report Regeneration]** no [!DNL Report.cfg] O arquivo está definido como [!DNL True], ao fazer alterações em um [!DNL Report.cfg] e salve esse arquivo de volta no servidor, o Servidor de relatórios gera automaticamente os relatórios nesse conjunto. Ele não reenvia os relatórios por email.

1. No [!DNL Reports] selecione a subpasta (guia ou subdiretório suspenso) do conjunto de relatórios que deseja reenviar.
1. Clique em **[!UICONTROL Report.cfg]**. Os parâmetros do [!DNL Report.cfg] para este conjunto de relatórios é exibido.
1. Altere o **[!UICONTROL Start Date]** para a hora futura em que deseja que os relatórios sejam reenviados.
1. Salve o arquivo clicando com o botão direito do mouse **[!UICONTROL Report.cfg (modified)]** na parte superior dos parâmetros e ao clicar em **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.
Os relatórios nesse conjunto são gerados novamente e reenviados por email para os recipients especificados.
