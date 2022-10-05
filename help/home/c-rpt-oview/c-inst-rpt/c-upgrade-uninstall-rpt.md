---
description: Informações sobre como atualizar e desinstalar o software do Servidor de relatórios.
title: Atualizar e desinstalar o servidor de relatórios
uuid: 42f0d190-1a88-424d-be4b-90338144d287
exl-id: 86d0d848-4e2a-45cb-a1b3-b8a856332d33
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 2%

---

# Atualizar e desinstalar o servidor de relatórios{#upgrading-and-uninstalling-report-server}

{{eol}}

Informações sobre como atualizar e desinstalar o software do Servidor de relatórios.

* [Atualização do relatório](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [Desinstalação do relatório](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## Atualizar o servidor de relatórios {#section-95fea4bddad74616a8aea450dcdb2282}

Se estiver atualizando para [!DNL Report Server] 5.4, você pode usar as instruções para atualizar o [!DNL Report Server] software. Se estiver usando [!DNL Report Server] 3.6 ou anterior, entre em contato com o Adobe para obter assistência com a atualização.

Para atualizar [!DNL Report Server] 5.4, use o Data Workbench para copiar um arquivo de atualização para o servidor do Data Workbench para o qual [!DNL Report Server] conecta-se. Depois de fazer isso, [!DNL Report] As instâncias do servidor atualizam-se automaticamente quando se conectam a esse servidor e carregam um perfil.

>[!NOTE]
>
>Antes de atualizar [!DNL Report Server], certifique-se de ter atualizado corretamente o software do servidor do Data Workbench, bem como os perfis em execução no servidor do Data Workbench. Para obter mais informações, entre em contato com os Serviços de consultoria do Adobe.

Para executar o procedimento a seguir, primeiro obtenha o arquivo de atualização para [!DNL Report Server].

**Para atualizar para [!DNL Report Server] 5.4 e versões posteriores**

1. Faça um backup de todos os arquivos em [!DNL E:\Portal] e remover todos os arquivos e pastas dentro desse diretório.
1. Copie o conteúdo da nova build em [!DNL E:\Portal].
1. Modificar [!DNL global.asa], [!DNL email.asp]e [!DNL TopNavigation.xml] de acordo com as instruções da seção anterior.

1. Copie o [!DNL users.mdb] do backup.

   >[!NOTE]
   >
   >Se você não gerou relatórios com uma saída .png anteriormente, é necessário entrar nas pastas de relatório individuais e modificar a variável [!DNL reports.xml] para incluir um formato de relatório de png. Caso contrário, você poderá receber um erro 500. Seu original [!DNL reports.xml] seria semelhante ao seguinte:

   ```
      <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

   Ela precisaria ser modificada para o seguinte:

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
    <REPORT format="png">
    <NAME>Dashboard</NAME>
     <PATH>Dashboard.png</PATH>
     <WEB_PATH>Dashboard.png</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

1. No [!DNL report.cfg], inclua um formato de saída de png e salve. Além disso, ele deve gerar relatórios no formato png.

**Para atualizar para [!DNL Report Server] 4,0**

1. No computador do Data Workbench, copie o arquivo de atualização do Servidor de Relatório para a [!DNL Temp\Software] no diretório em que o Data Workbench está instalado.
1. Inicie o Data Workbench e carregue o [!DNL Configuration] perfil.
1. Clique no botão **[!UICONTROL Configure Connection to Servers]** miniatura.
1. No [!DNL Servers Manager], clique com o botão direito do mouse no ícone do servidor do Data Workbench e clique em **[!UICONTROL Server Files]**.

1. Na pasta Software , abra o [!DNL Report Server] pasta.
1. Clique com o botão direito do mouse no **[!UICONTROL Temp]** marca de verificação para [!DNL ReportServer.exe] e selecione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Desinstalar o servidor de relatórios {#section-96eb3281c45a45c0a7065deaa6845c25}

**Para desinstalar[!DNL Report Server]**

1. Cancele o registro da variável [!DNL Report Windows] serviço.

   1. Abra um prompt de comando e navegue até o subdiretório bin, na pasta onde você instalou o servidor do Data Workbench (InsightServer64.exe). Exemplo: [!DNL D:\Adobe\Report\bin]
   1. No prompt de comando, execute o seguinte comando para pará-lo e cancelar o registro como um serviço no Microsoft Windows: [!DNL visualreport /unregserver]

1. Exclua o diretório de instalação do Servidor de relatórios.
