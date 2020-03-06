---
description: Etapas para mapear o Portal de relatórios para um diretório virtual (IIS 5.0).
solution: Analytics
title: Mapeamento do portal de relatórios para um diretório virtual (IIS 5.0)
topic: Data workbench
uuid: 9514c33e-c139-4cc2-97c2-8b241522c44d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mapeamento do portal de relatórios para um diretório virtual (IIS 5.0){#mapping-report-portal-to-a-virtual-directory-iis}

Etapas para mapear o Portal de relatórios para um diretório virtual (IIS 5.0).

1. No computador em que [!DNL Report Portal] está instalado, inicie o Gerenciador do IIS usando **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]** ou **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]**.

1. Selecionar **[!UICONTROL Local Machine]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. Clique com o botão direito do mouse **[!UICONTROL Default Web Site]** e selecione **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. Quando a janela [!DNL Virtual Directory Wizard] abrir, clique em **[!UICONTROL Next]**.

1. Complete as etapas a seguir para definir o diretório virtual raiz para [!DNL Report Portal]:

   1. Quando solicitado a fornecer um alias, digite o nome do alias [!DNL Report Portal]e clique em **[!UICONTROL Next]**. Por exemplo, se você quiser usar &quot;Portal&quot; como o nome do seu [!DNL Report Portal], atribua o alias &quot;Portal&quot; ao diretório virtual. Clique em **[!UICONTROL Next]** quando terminar.

   1. Quando solicitado a fornecer o caminho físico, procure e selecione o diretório *&lt;**[!UICONTROL PortalName]**>* **[!UICONTROL \PortalASP]** e clique em **[!UICONTROL Next]**.

      Exemplo: [!DNL C:\Inetpub\wwwroot\Portal\PortalASP]

   1. Quando solicitado a fornecer permissões, verifique se as seguintes opções estão habilitadas:

      * **[!UICONTROL Read]**
      * **[!UICONTROL Run scripts (such as ASP)]**
   1. Click **[!UICONTROL Next]**, then click **[!UICONTROL Finish]**. O diretório virtual que você criou é exibido sob o Site padrão, como mostra o exemplo a seguir.
   ![](assets/RptPort_scrn_VirDirManual.png)

1. Clique com o botão direito do mouse no diretório virtual que você acabou de criar e selecione **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. Use o [!DNL Virtual Directory] assistente para criar um alias para cada um dos seguintes diretórios físicos. Isso cria um diretório virtual com o nome adequado para cada um desses recursos físicos.

<table id="table_B2E04423C20F40CAA8EDA3FCBA210AA2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Crie este alias. . . </th> 
   <th colname="col2" class="entry"> Para este recurso físico. . . </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Núcleo </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Core </p> <p>Exemplo: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Core</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CSS </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\CSS </p> <p>Exemplo: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\CSS</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> HTC </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\HTC </p> <p>Exemplo: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\HTC</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Imagens </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Images </p> <p>Exemplo: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Images</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Saída </td> 
   <td colname="col2"> <p>Local físico do diretório no qual o Servidor <span class="keyword"> de</span> Relatório salva a saída dos conjuntos de relatórios. A pasta de saída pode ser localizada em qualquer lugar, pode ser nomeada qualquer item e contém uma subpasta para cada conjunto de relatórios. </p> <p>Esse deve ser o mesmo diretório especificado no parâmetro Saída raiz no arquivo <span class="filepath"> Report.cfg</span> para um conjunto de relatórios. Para obter mais informações, consulte <a href="../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d"> Configuração de arquivos</a>Report.cfg. </p> <p>O local padrão é \<i>PortalName</i>\PortalFiles\Output. </p> <p>Exemplo: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Output</span> </p> <p>O arquivo <i>PortalName</i>\PortalFiles\Output directory contains the <span class="filepath"> profile.xml</span> , que deve ser movido para o diretório de saída especificado para esse alias. </p> <p>É importante que o atributo <span class="wintitle"> Path</span> seja definido corretamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Quando terminar, verifique se o IIS exibe seis novos diretórios virtuais. Verifique se a estrutura de diretório tem uma pasta pai (com o mesmo nome do portal) e cinco subpastas, como mostrado abaixo.

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. Quando terminar, vá para [Editar o arquivo](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7) de configuração da sessão para continuar o processo de instalação.

