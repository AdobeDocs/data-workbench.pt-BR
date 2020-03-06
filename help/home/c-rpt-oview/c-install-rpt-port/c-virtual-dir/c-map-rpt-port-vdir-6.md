---
description: Etapas para mapear o Portal de relatórios para um diretório virtual (IIS 6.0).
solution: Analytics
title: Mapeamento do portal de relatórios para um diretório virtual (IIS 6.0)
topic: Data workbench
uuid: e09d23d7-09de-4180-8260-60527f47aa98
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mapeamento do portal de relatórios para um diretório virtual (IIS 6.0){#mapping-report-portal-to-a-virtual-directory-iis}

Etapas para mapear o Portal de relatórios para um diretório virtual (IIS 6.0).

O mapeamento do [!DNL Report Portal] para um diretório virtual no IIS 6.0 envolve três tarefas separadas:

1. [Editar o arquivo de configuração](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-eaf1c58935074cfa840dac33e1286520)
1. [Importar o arquivo de configuração para o IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-9d61f6bfa93846dcb96973fec5573b19)
1. [Ativar páginas ativas do servidor (ASPs) no IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-a7725ec2afc64ffc854c5bd8c5c31802)

Você deve concluir as três tarefas.

## To Edit the Configuration File {#section-eaf1c58935074cfa840dac33e1286520}

1. Na máquina em que [!DNL Report Portal] está instalado, abra \*PortalName*\ReportPortalSetup.xml em um editor de texto como o Bloco de notas.

1. Use o recurso localizar e substituir do editor para substituir globalmente (Substituir tudo) a string &quot;VSVirtualPortalName&quot; pelo nome do seu portal. Por exemplo, se você deseja usar &quot;VisualReportPortal&quot; como o nome do seu [!DNL Report Portal], você deve procurar &quot;VSVirtualPortalName&quot; e substituí-lo por &quot;VisualReportPortal.&quot;
1. Localize o seguinte elemento neste arquivo:

   ```
   <IIsWebVirtualDir Location= "/LM/W3SVC/1/Root/PortalName/Output" AccessFlags="AccessRead | AccessScript” AppFriendlyName="Output" . . . >
   ```

1. Defina o [!DNL Path] atributo desse elemento para o local físico do diretório no qual [!DNL Report Server] salva a saída dos conjuntos de relatórios.

   A pasta de saída pode ser localizada em qualquer lugar, pode ser nomeada qualquer item e contém uma subpasta para cada conjunto de relatórios.

   >[!NOTE]
   >
   >Esse deve ser o mesmo diretório que você especificou no parâmetro Raiz de saída no [!DNL Report.cfg] arquivo para um conjunto de relatórios. Para obter mais informações, consulte [Configuração de arquivos](../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d)Report.cfg.

   A amostra de código a seguir mostra como você definiria o [!DNL Path] atributo se seus relatórios fossem salvos em [!DNL E:\VSReport\ReportOutput]:

   ```
   < . . . 
   AppIsolated="2" 
       AppRoot="/LM/W3SVC/1/Root/PortalName/OutputFolder" 
       DirBrowseFlags="DirBrowseShowDate | DirBrowseShowTime |...  
       Path="E:\VSReport\ReportOutput"
   ```

   >[!NOTE]
   >
   >É importante que o [!DNL Path] atributo seja definido corretamente.

1. Se você alterou o padrão [!DNL Path] do [!DNL Output] elemento, mova o [!DNL profiles.xml] arquivo do *\PortalName*\PortalFiles\Output folder to the output directory that you specified in Step 4. No exemplo acima, você se moveria [!DNL profiles.xml] para [!DNL E:\VSReport\ReportOutput].

1. Verifique se os [!DNL Path] atributos de todos os outros [!DNL IIsWebVirtualDir] elementos estão mapeados para o local correto, pesquisando todas as instâncias de [!DNL C:\Inetpub\wwwroot] e substituindo-as pelo caminho correto.

1. Salve o arquivo. Se quiser preservar o arquivo original, salve o arquivo de configuração usando um novo nome.

## Para importar o arquivo de configuração para o IIS {#section-9d61f6bfa93846dcb96973fec5573b19}

1. No computador em que [!DNL Report Portal] está instalado, inicie o Gerenciador do IIS usando **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Systems (IIS) Manager]**.

1. Selecionar **[!UICONTROL (local computer)]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. Clique com o botão direito do mouse **[!UICONTROL Default Web Site]** e selecione **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]** (do arquivo).

1. Selecione o **[!UICONTROL ReportPortalSetup.xml]** arquivo e clique em **[!UICONTROL Read File]**.

1. Verifique se seis diretórios virtuais estão listados para seu computador, [!DNL Report Portal] como mostrado no exemplo a seguir.

   ![](assets/rptPort_dia_VirDirs.png)

   Se você não vir seis diretórios virtuais ou se receber uma mensagem de erro, clique **[!UICONTROL Cancel]** e examine o arquivo de configuração em busca de erros.

1. Selecione o primeiro diretório virtual na lista (aquele que é o pai dos outros cinco) e clique em **[!UICONTROL OK]**. O IIS importa os mapeamentos e adiciona os diretórios virtuais ao Site Padrão.

   Certifique-se de que a estrutura de diretório resultante tenha uma pasta pai (com o mesmo nome do portal) e cinco subdiretórios, conforme mostrado no exemplo a seguir.

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. Clique em cada diretório virtual para garantir que o IIS possa localizar o diretório físico que ele representa. Se o IIS exibir um erro, clique com o botão direito do mouse no nome do diretório virtual e verifique se o [!DNL Local Path] campo aponta para o diretório físico correto.

## Para ativar páginas ativas do servidor (ASPs) no IIS {#section-a7725ec2afc64ffc854c5bd8c5c31802}

Para usar [!DNL Report Portal], os ASPs devem estar habilitados no IIS. (Por padrão, os ASPs são desativados quando o IIS 6.0 está instalado.) Use o procedimento a seguir para verificar se os ASPs estão ativados no IIS.

1. Na janela Gerenciador do IIS, selecione **[!UICONTROL (local computer)]** > **[!UICONTROL Web Service Extensions]**.
1. Verifique se a [!DNL Active Server Pages] extensão está definida como [!DNL Allowed].

   ![](assets/report_aspenable.png)

1. Se o Status for Proibido, selecione **[!UICONTROL Active Server Pages]** e clique em **[!UICONTROL Allow]**.
1. Feche o Gerenciador do IIS.

