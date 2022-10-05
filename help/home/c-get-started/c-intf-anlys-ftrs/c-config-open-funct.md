---
description: A funcionalidade aberta permite que você abra itens como documentos ou URIs em aplicativos externos, como um editor de texto ou um navegador da Web.
title: Configurar funcionalidade aberta
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
exl-id: c807a284-b544-41cf-958b-27b47d2142ce
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 3%

---

# Configurar funcionalidade aberta{#configure-open-functionality}

{{eol}}

A funcionalidade aberta permite que você abra itens como documentos ou URIs em aplicativos externos, como um editor de texto ou um navegador da Web.

A funcionalidade aberta está configurada no momento somente no [!DNL Site] e somente para abrir URIs. Esta seção fornece informações sobre a configuração da funcionalidade de URI aberta para o [!DNL Site]. Para obter informações sobre como configurar a funcionalidade do Open para outro aplicativo ou para abrir outros itens, entre em contato com os Serviços de consultoria do Adobe.

Em [!DNL Site], é possível clicar com o botão direito do mouse em um URI de uma sobreposição de página ou tabela para exibir o URI no aplicativo para o qual ele foi formatado. Por exemplo, em uma visualização da tabela de URI, você pode clicar em um URI para exibir uma página da Web em um navegador da Web.

Para abrir um URI em uma visualização, primeiro edite o [!DNL Open URI.cfg] arquivo da dimensão URI para identificar a localização e as convenções de nomenclatura que o Data Workbench usa para abrir o URI. Para exibir um URI em seu formato nativo (como o HTML), o Data Workbench deve ter acesso ao local referenciado e ao aplicativo necessário para abrir esse item. Por exemplo, para visualizar uma página da Web, o Data Workbench precisaria acessar a Internet e ter um navegador da Web instalado.

**Para editar o URI aberto.vw**

1. Na [!DNL Profile Manager], clique em **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.
1. Na pasta URI, clique com o botão direito do mouse na marca de seleção ao lado do [!DNL Open URI.vw]e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece no [!DNL User] coluna.
1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]** se o arquivo for um [!DNL .cfg] ou **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** se for um [!DNL .vw] arquivo.
1. Clique em **[!UICONTROL Command]**, em seguida **[!UICONTROL Parameters]** para exibir o conteúdo do arquivo.
1. Modifique o [!DNL Site] e o parâmetro Template conforme necessário:

<table id="table_CDB316DB271F476AB9F9B557B86AFD25">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Para este parâmetro... </th>
   <th colname="col2" class="entry"> Fornecer essas informações... </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>Site </p> </td>
   <td colname="col2"> <p>A localização dos URIs que você deseja abrir. </p> <p>Exemplo: mysite.com </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Modelo </p> </td>
   <td colname="col2"> <p>Os parâmetros que o Data Workbench deve usar para localizar e abrir os URIs. </p> <p>Exemplo: <span class="filepath"> https://%Site%%URI%</span> </p> <p>O modelo padrão mostrado no exemplo informa ao Data Workbench para abrir um navegador da Web, procure o local definido no <span class="wintitle"> Site</span> , em seguida, localize o elemento da dimensão URI que você está tentando abrir. </p> </td>
  </tr>
 </tbody>
</table>

1. Salve o arquivo.
1. Para disponibilizar essa alteração a todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção para a variável [!DNL .vw] no [!DNL User] e clique em **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**.
