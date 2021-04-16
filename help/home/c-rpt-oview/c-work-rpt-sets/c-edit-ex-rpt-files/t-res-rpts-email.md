---
description: Etapas para reenviar relatórios por email.
title: Reenviar relatórios por email
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
exl-id: eb37fd3e-6e7b-4672-bcf0-fffa9f10997d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 6%

---

# Reenviar relatórios por email{#resending-reports-by-email}

Etapas para reenviar relatórios por email.

Se o parâmetro **[!UICONTROL Allow Report Regeneration]** no arquivo [!DNL Report.cfg] estiver definido como [!DNL True], quando você fizer alterações em um arquivo [!DNL Report.cfg] e salvar esse arquivo de volta no servidor, o Servidor de Relatório automaticamente regerará os relatórios nesse conjunto. Ele não reenvia os relatórios por email.

1. Na guia [!DNL Reports] , selecione a subpasta (subdiretório da guia ou suspenso) do conjunto de relatórios que deseja reenviar.
1. Clique em **[!UICONTROL Report.cfg]**. Os parâmetros de [!DNL Report.cfg] para esse conjunto de relatórios são exibidos.
1. Altere o parâmetro **[!UICONTROL Start Date]** para a hora futura em que deseja que os relatórios sejam reenviados.
1. Salve o arquivo clicando com o botão direito do mouse em **[!UICONTROL Report.cfg (modified)]** na parte superior dos parâmetros e clicando em **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.
Os relatórios nesse conjunto são gerados novamente e reenviados por email para os recipients especificados.
