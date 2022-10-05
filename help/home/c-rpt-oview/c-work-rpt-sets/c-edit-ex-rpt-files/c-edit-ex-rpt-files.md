---
description: Etapas para editar arquivos Report.cfg existentes usando a Área de trabalho ou um editor de texto.
title: Editar arquivos Report.cfg existentes
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
exl-id: 69038c0c-bb01-4e61-aad6-1be0bdec8a6d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 2%

---

# Editar arquivos Report.cfg existentes{#editing-existing-report-cfg-files}

{{eol}}

Etapas para editar arquivos Report.cfg existentes usando a Área de trabalho ou um editor de texto.

>[!NOTE]
>
>* Você deve trabalhar online para editar [!DNL Report.cfg] arquivos. Para trabalhar online, na [!DNL Worktop], clique com o botão direito do mouse na barra de título e clique em **[!UICONTROL Work Online]**.
>
>* Se a variável **[!UICONTROL Allow Report Regeneration]** no [!DNL Report.cfg] O arquivo está definido como [!DNL True], quando você faz alterações nesse arquivo e o salva no servidor, [!DNL Report] gera automaticamente os relatórios nesse conjunto. Embora regenere os relatórios, ele não reenvia os relatórios por email. Para obter etapas para fazer isso, consulte [Reenviar relatórios por email](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607).
>


É possível editar um [!DNL Report.cfg] do [!DNL Worktop] ou usando um editor de texto.

Edição de um [!DNL Report.cfg] arquivo usando o [!DNL Reports] da guia [!DNL Worktop] permite editar somente os parâmetros, vetores e itens de vetor que já existem no arquivo. Se precisar adicionar um parâmetro ou vetor ao arquivo, edite-o usando um editor de texto, como o Bloco de notas.

* [Para editar um Report.cfg existente usando a Área de trabalho](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945)
* [Para editar um Report.cfg existente usando um editor de texto](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## Para editar um Report.cfg existente usando a Área de trabalho {#section-7bce3bca006149c79be7678430f21945}

>[!NOTE]
>
>Você deve trabalhar online para editar o [!DNL Report.cfg] do [!DNL Worktop].

1. No Data Workbench, no [!DNL Reports] selecione a subpasta (guia ou subdiretório suspenso) do conjunto de relatórios que deseja configurar.
1. Clique em **[!UICONTROL Report.cfg]**. Os parâmetros do [!DNL Report.cfg] para este conjunto de relatórios é exibido.

1. Edite os parâmetros de configuração conforme desejado. Para obter informações sobre esses parâmetros, consulte [Parâmetros do Report.cfg](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. Salve o arquivo clicando com o botão direito do mouse **[!UICONTROL Report.cfg (modified)]** na parte superior dos parâmetros e ao clicar em **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.

## Para editar um Report.cfg existente usando um editor de texto {#section-06f3d2a8d7f34bc2841180caf10a1eb7}

1. Abra o [!DNL Reports Manager] clicando com o botão direito do mouse em um espaço de trabalho e clicando em **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Reports Manager]**.

1. Clique na pasta do seu conjunto de relatórios.
1. Clique com o botão direito do mouse na marca de seleção ao lado do [!DNL Report.cfg] para este conjunto de relatórios e clique em **[!UICONTROL Make Local]**.

1. No [!DNL User] , clique com o botão direito do mouse na marca de seleção ao lado de [!DNL Report.cfg] para este conjunto de relatórios e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O [!DNL Report.cfg] é aberto.

   A amostra [!DNL Report.cfg] mostrado em [Configurar o conjunto de relatórios](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) contém apenas os parâmetros incluídos no [!DNL Report.cfg] por padrão. O exemplo a seguir inclui todos os parâmetros disponíveis para a variável [!DNL Report.cfg] arquivo que você pode usar como modelos para suas entradas de parâmetro:

   ```
   Attachments = vector: 1 items
     0 = Attachment:
       FileName = string: c:\\myimage.jpg
       Content Type = string: image/jpeg
   Alert Threshold = int: 0
   Allow Report Regeneration = bool: true
   Color Set = int: 1
   Command To Execute = string: 
   Default Excel Template = string: 
   Dimension Name = string: 
   Email Only If Perfect = bool: false
   End Date = string: 
   Every = string: month
   Excel Watchdog Timeout (seconds) = double: 300.0
   Filter Formula = string: 
   Gamma Correction = double: 1
   Hide Logos = bool: false
   Lookup File = string: 
   Mail Report = MailReport: 
     Body XSL Template = string: 
     Recipients = vector: 0 items
     SMTP Server = SmtpServerInfo: 
       Address = string: 
       Password = string: 
       User = string: 
     Sender Address = string: 
     Sender Name = string: 
     Subject = string: 
   Notification Only = bool: false
   Output Root = string: 
   Report Types = vector: 3 items
     0 = string: thumbnail
     1 = string: png
     2 = string: excel
   Start Date = string: 7/1/06 19:16 EDT
   Thumbnail X = int: 240
   Thumbnail Y = int: 180
   Top N Metric = string: 
   Top N Value = int: 0
   Use Local Sample Only = bool: false
   Workspace Path = string: 
   ```

1. Edite os parâmetros de configuração conforme desejado. Para obter informações sobre esses parâmetros, consulte [Parâmetros do Report.cfg](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. Salve e feche o arquivo.
1. No [!DNL Reports Manager], clique com o botão direito do mouse na marca de seleção no [!DNL User] para a coluna [!DNL Report.cfg] e selecione **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.
