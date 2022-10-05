---
description: Etapas para mapear o portal de relatórios para um diretório virtual (IIS 5.0).
title: Mapear o portal de relatórios para um diretório virtual (IIS 5.0)
uuid: 9514c33e-c139-4cc2-97c2-8b241522c44d
exl-id: 20d8e9ea-c5b6-4a1b-9b15-557cc71ad5d9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 6%

---

# Mapear o portal de relatórios para um diretório virtual (IIS 5.0){#mapping-report-portal-to-a-virtual-directory-iis}

{{eol}}

Etapas para mapear o portal de relatórios para um diretório virtual (IIS 5.0).

1. Na máquina em que [!DNL Report Portal] estiver instalado, inicie o Gerenciador do IIS usando **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]** ou **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]**.

1. Selecionar **[!UICONTROL Local Machine]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. Clique com o botão direito do mouse **[!UICONTROL Default Web Site]** e selecione **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. Quando a variável [!DNL Virtual Directory Wizard] abre, clique em **[!UICONTROL Next]**.

1. Complete as etapas a seguir para definir o diretório virtual raiz para [!DNL Report Portal]:

   1. Quando solicitado para um alias, digite o nome do [!DNL Report Portal], depois clique em **[!UICONTROL Next]**. Por exemplo, se você quiser usar &quot;Portal&quot; como o nome de seu [!DNL Report Portal], atribua o alias &quot;Portal&quot; ao diretório virtual. Clique em **[!UICONTROL Next]** quando terminar.

   1. Quando solicitado para o caminho físico, procure e selecione o *&lt;**[!UICONTROL PortalName]**>* **[!UICONTROL \PortalASP]** , depois clique em **[!UICONTROL Next]**.

      Exemplo: [!DNL C:\Inetpub\wwwroot\Portal\PortalASP]

   1. Quando solicitado a fornecer permissões, verifique se as seguintes opções estão ativadas:

      * **[!UICONTROL Read]**
      * **[!UICONTROL Run scripts (such as ASP)]**
   1. Clique em **[!UICONTROL Next]** e depois em **[!UICONTROL Finish]**. O diretório virtual que você criou é exibido no Site padrão, como mostrado no exemplo a seguir.

   ![](assets/RptPort_scrn_VirDirManual.png)

1. Clique com o botão direito do mouse no diretório virtual que acabou de criar e selecione **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. Use o [!DNL Virtual Directory] assistente para criar um alias para cada um dos diretórios físicos a seguir. Isso cria um diretório virtual com o nome adequado para cada um desses recursos físicos.

<table id="table_B2E04423C20F40CAA8EDA3FCBA210AA2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Crie este alias . . . </th> 
   <th colname="col2" class="entry"> Para este recurso físico . . . </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Núcleo </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalArquivos\Core </p> <p>Exemplo: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Core</span> </p> </td> 
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
   <td colname="col2"> <p>\<i>PortalName</i>\PortalArquivos\Imagens </p> <p>Exemplo: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Images</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Saída </td> 
   <td colname="col2"> <p>Localização física do diretório em que <span class="keyword"> Servidor de relatórios</span> salva a saída dos conjuntos de relatórios. A pasta de saída pode ser localizada em qualquer lugar, pode ser nomeada qualquer coisa e contém uma subpasta para cada conjunto de relatórios. </p> <p>Esse deve ser o mesmo diretório especificado no parâmetro Raiz de Saída da <span class="filepath"> Report.cfg</span> para um conjunto de relatórios. Para obter mais informações, consulte <a href="../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d"> Configurar arquivos Report.cfg</a>. </p> <p>O local padrão é \<i>PortalName</i>\PortalFiles\Output. </p> <p>Exemplo: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Output</span> </p> <p>O <i>PortalName</i>O diretório \PortalFiles\Output contém o <span class="filepath"> profiles.xml</span> , que deve ser movido para o diretório de saída especificado para esse alias. </p> <p>É fundamental que a <span class="wintitle"> Caminho</span> for definido corretamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Quando terminar, verifique se o IIS exibe seis novos diretórios virtuais. Certifique-se de que a estrutura de diretório tenha uma pasta pai (com o mesmo nome do portal) e cinco subpastas, conforme mostrado abaixo.

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. Ao terminar, acesse [Editar o arquivo de configuração da sessão](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7) para continuar com o processo de instalação.
