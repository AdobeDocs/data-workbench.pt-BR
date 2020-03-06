---
description: Informações sobre como atualizar e desinstalar o software do Servidor de relatórios.
solution: Analytics
title: Atualização e desinstalação do Servidor de relatórios
topic: Data workbench
uuid: 42f0d190-1a88-424d-be4b-90338144d287
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Atualização e desinstalação do Servidor de relatórios{#upgrading-and-uninstalling-report-server}

Informações sobre como atualizar e desinstalar o software do Servidor de relatórios.

* [Atualização do relatório](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [Desinstalação do relatório](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## Atualização do Servidor de Relatório {#section-95fea4bddad74616a8aea450dcdb2282}

Se você estiver atualizando para a versão [!DNL Report Server] 5.4, poderá usar as instruções para atualizar seu [!DNL Report Server] software. Se você estiver usando [!DNL Report Server] 3.6 ou anterior, entre em contato com a Adobe para obter ajuda com a atualização.

Para atualizar a versão [!DNL Report Server] 5.4, use o análise de big data para copiar um arquivo de atualização para o servidor do análise de big data ao qual [!DNL Report Server] se conecta. Após isso, as instâncias [!DNL Report] do servidor atualizam-se automaticamente quando se conectam a esse servidor e carregam um perfil.

>[!NOTE]
>
>Antes de atualizar [!DNL Report Server], verifique se você atualizou corretamente o software do servidor da análise de big data, bem como os perfis em execução no servidor da análise de big data. Para obter mais informações, entre em contato com os Serviços de consultoria da Adobe.

Para executar o procedimento a seguir, primeiro você deve obter o arquivo de atualização para [!DNL Report Server].

**Para atualizar para[!DNL Report Server]5.4 e versões posteriores**

1. Faça backup de todos os arquivos em [!DNL E:\Portal] e remova todos os arquivos e pastas dentro desse diretório.
1. Copy the contents of the new build into [!DNL E:\Portal].
1. Modifique [!DNL global.asa], [!DNL email.asp]e [!DNL TopNavigation.xml] conforme as instruções da seção anterior.

1. Copie o [!DNL users.mdb] do backup.

   >[!NOTE]
   >
   >Se você não gerou relatórios com uma saída .png, é necessário acessar as pastas de relatórios individuais e modificar os relatórios para incluir um formato de relatório de png. [!DNL reports.xml] Caso contrário, você receberá um erro 500. Seu original [!DNL reports.xml] seria semelhante ao seguinte:

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

1. Na página [!DNL report.cfg], inclua um formato de saída de png e save. Além disso, ele deve gerar relatórios no formato png.

**Para atualizar para o[!DNL Report Server]4.0**

1. No computador da análise de big data, copie o arquivo de atualização do Servidor de relatórios para a [!DNL Temp\Software] pasta no diretório em que a análise de big data está instalada.
1. Inicie a análise de big data e carregue o [!DNL Configuration] perfil.
1. Clique na **[!UICONTROL Configure Connection to Servers]** miniatura.
1. No [!DNL Servers Manager], clique com o botão direito do mouse no ícone do servidor da análise de big data e clique em **[!UICONTROL Server Files]**.

1. Na pasta Software, abra a [!DNL Report Server] pasta.
1. Clique com o botão direito do mouse na marca de **[!UICONTROL Temp]** seleção para [!DNL ReportServer.exe] e selecione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Desinstalação do Servidor de Relatório {#section-96eb3281c45a45c0a7065deaa6845c25}

**Para desinstalar[!DNL Report Server]**

1. Cancele o registro do [!DNL Report Windows] serviço.

   1. Abra um prompt de comando e navegue até o subdiretório bin na pasta onde você instalou o servidor do análise de big data (InsightServer64.exe). Exemplo: [!DNL D:\Adobe\Report\bin]
   1. No prompt de comando, execute o seguinte comando para pará-lo e cancelar o registro como um serviço no Microsoft Windows: [!DNL visualreport /unregserver]

1. Exclua o diretório de instalação do Servidor de relatórios.

