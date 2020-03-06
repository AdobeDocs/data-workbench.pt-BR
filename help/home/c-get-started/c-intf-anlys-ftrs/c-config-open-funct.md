---
description: A funcionalidade de abertura permite que você abra itens como documentos ou URIs em aplicativos externos, como um editor de texto ou um navegador da Web.
solution: Analytics
title: Configurar funcionalidade aberta
topic: Data workbench
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurar funcionalidade aberta{#configure-open-functionality}

A funcionalidade de abertura permite que você abra itens como documentos ou URIs em aplicativos externos, como um editor de texto ou um navegador da Web.

A funcionalidade aberta está atualmente configurada apenas no [!DNL Site] aplicativo e somente para abrir URIs. Esta seção fornece informações sobre como configurar a funcionalidade de URI aberto para [!DNL Site]. Para obter informações sobre como configurar a funcionalidade do Open para outro aplicativo ou abrir outros itens, entre em contato com os Serviços de consultoria da Adobe.

Em [!DNL Site], você pode clicar com o botão direito do mouse em um URI de uma sobreposição de página ou tabela para exibir o URI no aplicativo para o qual ele foi formatado. Por exemplo, em uma visualização de tabela de URI, você pode clicar em um URI para exibir uma página da Web em um navegador da Web.

Para abrir um URI a partir de uma visualização, primeiro edite o [!DNL Open URI.cfg] arquivo da dimensão URI para identificar a localização e as convenções de nomenclatura que o Análise de big data usa para abrir o URI. Para exibir um URI em seu formato nativo (como HTML), a Análise de big data deve ter acesso ao local referenciado e ao aplicativo necessário para abrir esse item. Por exemplo, para exibir uma página da Web, o Análise de big data precisaria de acesso à Internet e ter um navegador da Web instalado.

**Para editar o URI aberto.vw**

1. In the [!DNL Profile Manager], click **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.
1. Na pasta URI, clique com o botão direito do mouse na marca de seleção ao lado do [!DNL Open URI.vw]arquivo e clique em **[!UICONTROL Make Local]**. Uma marca de seleção para este arquivo é exibida na [!DNL User] coluna.
1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]** se o arquivo for um [!DNL .cfg] arquivo ou **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** se for um [!DNL .vw] arquivo.
1. Clique em **[!UICONTROL Command]**, em seguida, **[!UICONTROL Parameters]** para exibir o conteúdo do arquivo.
1. Modifique o [!DNL Site] parâmetro e o parâmetro Modelo conforme necessário:

<table id="table_CDB316DB271F476AB9F9B557B86AFD25"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para este parâmetro... </th> 
   <th colname="col2" class="entry"> Fornecer estas informações... </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Site </p> </td> 
   <td colname="col2"> <p>A localização dos URIs que você deseja abrir. </p> <p>Exemplo: mysite.com </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modelo </p> </td> 
   <td colname="col2"> <p>Os parâmetros que o Análise de big data deve usar para localizar e abrir os URIs. </p> <p>Exemplo: <span class="filepath"> http://%Site%%URI%</span> </p> <p>O modelo padrão mostrado no exemplo informa ao Análise de big data para abrir um navegador da Web, procure o local definido no parâmetro <span class="wintitle"> Site</span> e localize o elemento de dimensão URI que você está tentando abrir. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Salve o arquivo.
1. Para disponibilizar essa alteração para todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção do [!DNL .vw] arquivo na [!DNL User] coluna e clique em **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**.

