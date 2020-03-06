---
description: Etapas para editar arquivos Report.cfg existentes usando a Área de trabalho ou um editor de texto.
solution: Analytics
title: Editar arquivos Report.cfg existentes
topic: Data workbench
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Editar arquivos Report.cfg existentes{#editing-existing-report-cfg-files}

Etapas para editar arquivos Report.cfg existentes usando a Área de trabalho ou um editor de texto.

>[!NOTE]
>
>* Você deve estar trabalhando online para editar [!DNL Report.cfg] arquivos. Para trabalhar online, na barra de título, clique com o botão direito do mouse [!DNL Worktop]na barra de título e clique em **[!UICONTROL Work Online]**.
   >
   >
* Se o **[!UICONTROL Allow Report Regeneration]** parâmetro no [!DNL Report.cfg] arquivo estiver definido como [!DNL True], ao fazer alterações nesse arquivo e salvar o arquivo de volta no servidor, o [!DNL Report] regera automaticamente os relatórios nesse conjunto. Embora regenere os relatórios, eles não reenviam os relatórios por email. Para obter etapas para fazer isso, consulte [Reenviando relatórios por email](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607).
>



É possível editar um existente [!DNL Report.cfg] do editor de texto [!DNL Worktop] ou usando um editor de texto.

Editar um [!DNL Report.cfg] arquivo usando a [!DNL Reports] guia do [!DNL Worktop] permite que você edite apenas os parâmetros, vetores e itens de vetor que já existem no arquivo. Se precisar adicionar um parâmetro ou vetor ao arquivo, edite-o usando um editor de texto, como o Bloco de notas.

* [Para editar um Report.cfg existente usando a área de trabalho](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945)
* [Para editar um Report.cfg existente usando um editor de texto](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## Para editar um Report.cfg existente usando a área de trabalho {#section-7bce3bca006149c79be7678430f21945}

>[!NOTE]
>
>Você deve estar trabalhando on-line para editar o formulário [!DNL Report.cfg] do [!DNL Worktop].

1. Na análise de big data, na [!DNL Reports] guia, selecione a subpasta (guia ou subdiretório suspenso) para o conjunto de relatórios que deseja configurar.
1. Clique em **[!UICONTROL Report.cfg]**. Os parâmetros do [!DNL Report.cfg] conjunto de relatórios são exibidos.

1. Edite os parâmetros de configuração conforme desejado. Para obter informações sobre esses parâmetros, consulte Parâmetros [](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)Report.cfg.
1. Salve o arquivo clicando com o botão direito do mouse **[!UICONTROL Report.cfg (modified)]** na parte superior dos parâmetros e clicando em **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.

## Para editar um Report.cfg existente usando um editor de texto {#section-06f3d2a8d7f34bc2841180caf10a1eb7}

1. Abra o arquivo clicando com o botão direito do mouse [!DNL Reports Manager] em um espaço de trabalho e clicando em **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Reports Manager]**.

1. Clique na pasta do conjunto de relatórios.
1. Clique com o botão direito do mouse na marca de seleção ao lado [!DNL Report.cfg] do conjunto de relatórios e clique em **[!UICONTROL Make Local]**.

1. Na [!DNL User] coluna, clique com o botão direito do mouse na marca de seleção ao lado [!DNL Report.cfg] desse conjunto de relatórios e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O [!DNL Report.cfg] arquivo é aberto.

   A amostra [!DNL Report.cfg] mostrada em [Configurar o conjunto](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) de relatórios contém apenas os parâmetros incluídos no [!DNL Report.cfg] arquivo por padrão. O exemplo a seguir inclui todos os parâmetros disponíveis para o [!DNL Report.cfg] arquivo que você pode usar como modelos para as entradas de parâmetro:

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

1. Edite os parâmetros de configuração conforme desejado. Para obter informações sobre esses parâmetros, consulte Parâmetros [](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)Report.cfg.
1. Salve e feche o arquivo.
1. No [!DNL Reports Manager], clique com o botão direito do mouse na marca de seleção na [!DNL User] coluna do [!DNL Report.cfg] arquivo e selecione **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.

