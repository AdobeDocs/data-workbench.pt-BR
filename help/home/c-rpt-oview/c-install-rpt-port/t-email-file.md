---
description: O acesso e as permissões em seu Portal de relatórios são controlados por meio de contas individuais de usuário e grupo.
solution: Analytics
title: Editar o arquivo Email.asp
topic: Data workbench
uuid: 18251170-0317-4a32-b9e1-4ebf2d7ad123
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Editar o arquivo Email.asp{#edit-the-email-asp-file}

O acesso e as permissões em seu Portal de relatórios são controlados por meio de contas individuais de usuário e grupo.

Cada vez que você adiciona uma nova conta ou edita uma conta existente, um e-mail de confirmação pode ser enviado para o endereço de e-mail especificado para essa conta (consulte [Trabalhar com contas](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)) e copiado para os endereços de e-mail especificados no [!DNL email.asp] arquivo.

>[!NOTE]
>
>Os emails de notificação são enviados para usuários da conta somente quando você tiver especificado um endereço de email para a conta e configurado corretamente o [!DNL email.asp] arquivo. Se você não quiser que emails de notificação sejam enviados para uma conta, deixe o campo de email da conta em branco.

Este arquivo está localizado na `\*PortalName*\PortalASP` pasta.

1. Na máquina em que o IIS está sendo executado, abra o [!DNL email.asp] arquivo em um editor de texto, como o Bloco de notas.
1. Defina as seguintes variáveis:

<table id="table_44F52DA266364DF993C40678A28E0F0D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para esta variável. . . </th> 
   <th colname="col2" class="entry"> Forneça essas informações. . . </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> smtpserver </td> 
   <td colname="col2"> <p>Nome DNS ou endereço IP do servidor SMTP pelo qual as mensagens são enviadas. </p> <p>Por exemplo: <span class="filepath"> mail.hq.omniture.com</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpserverport </td> 
   <td colname="col2"> A porta na qual o servidor SMTP escuta conexões. Normalmente, é a porta 25. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sensualidade </td> 
   <td colname="col2"> <p>Indica como a mensagem deve ser enviada. Os valores são: </p> <p>1 - Envie mensagens usando o serviço SMTP instalado localmente. Use esse valor se o serviço SMTP estiver instalado no computador em que o script está sendo executado. </p> <p>2 - Envie mensagens usando o serviço SMTP na rede. Use esse valor se o serviço SMTP não estiver instalado no computador em que o script está sendo executado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpconnectiontimeout </td> 
   <td colname="col2">A quantidade de tempo que o <span class="wintitle"> Report</span> deve aguardar uma resposta do servidor SMTP antes de expirar a conexão. </td> 
  </tr> 
 </tbody> 
</table>

1. Para as funções [!DNL NewUserEmail()] e [!DNL UpdateUserEmail()] , defina as seguintes variáveis:

   <table id="table_91C5E36B84A94C4097EE5993592BE587"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Para esta variável. . . </th> 
      <th colname="col2" class="entry"> Forneça essas informações. . . </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> De </td> 
      <td colname="col2">O texto que você deseja exibir na linha de cabeçalho De em seus emails de confirmação. Esse valor pode ser igual ao <span class="wintitle"> valor CC</span> . </td> 
   </tr> 
   <tr> 
      <td colname="col1"> CC </td> 
      <td colname="col2"> <p>Opcional. O endereço de email válido da pessoa ou alias que deve receber uma cópia de todas as mensagens relativas a contas de usuário novas e alteradas. Você pode especificar vários endereços de email separando os endereços por vírgulas (sem espaços). </p> <p>Por exemplo: <span class="filepath"> admin@company.com,joemanager@company.com</span></p> <p> <p>Observação:  Os destinatários recebem cópias de e-mails que contêm senhas de usuário. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Assunto </td> 
      <td colname="col2"> O texto que você deseja que seja exibido na linha de cabeçalho Assunto em seus emails de confirmação. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> WebPath </td> 
      <td colname="col2"> <p>O caminho real para o seu portal. </p> <p>Por exemplo: <span class="filepath"> http://portal.omniture.com/Example</span></p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Corpo </td> 
      <td colname="col2"> <p>O texto incluído nos emails gerados automaticamente. </p> <p>Por exemplo, a seguir está o texto padrão incluído nos emails enviados para fornecer informações de logon: 
      <ul id="ul_7FF2E7399AB64D279EC5794AB02C9749">
      <li id="li_7CBCC5CFF9E04776BBC893278785AEE7">As informações de logon do portal da Web são fornecidas abaixo: </li>
      <li id="li_5346F0AB3568444B88117C295D8E99C5"><p>UserName: nome de usuário </p><p>Nova senha: password </p></li>
      <li id="li_B0D1FAE818BA42CF8546796800A1AA08"><p>Você pode acessar o portal usando o seguinte URL: </p><p><span class="filepath"> http://WebPath</span></p></li>
      <li id="li_7CD71EBDFA1D418F960040569CD511EB">Depois de fazer logon no portal, você pode alterar sua senha na guia <span class="wintitle"> Admin</span> . </li>
      </ul></p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Salve e feche o arquivo.
