---
description: Etapas para reenviar relatórios por email.
solution: Analytics
title: Reenviando relatórios por email
topic: Data workbench
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Reenviando relatórios por email{#resending-reports-by-email}

Etapas para reenviar relatórios por email.

Se o **[!UICONTROL Allow Report Regeneration]** parâmetro no [!DNL Report.cfg] arquivo estiver definido como [!DNL True], quando você fizer alterações em um [!DNL Report.cfg] arquivo e salvar esse arquivo de volta no servidor, o Servidor de relatórios gera automaticamente os relatórios nesse conjunto. Ele não reenvia os relatórios por email.

1. Na [!DNL Reports] guia, selecione a subpasta (guia ou subdiretório suspenso) para o conjunto de relatórios que deseja reenviar.
1. Clique em **[!UICONTROL Report.cfg]**. Os parâmetros do [!DNL Report.cfg] conjunto de relatórios são exibidos.
1. Altere o **[!UICONTROL Start Date]** parâmetro para a hora futura na qual você deseja que os relatórios sejam reenviados.
1. Salve o arquivo clicando com o botão direito do mouse **[!UICONTROL Report.cfg (modified)]** na parte superior dos parâmetros e clicando em **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.
Os relatórios neste conjunto são regenerados e reenviados por email para os destinatários especificados.
