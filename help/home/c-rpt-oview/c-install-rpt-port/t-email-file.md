---
description: O acesso a permissões e no Portal de relatórios é controlado usando contas de usuário e grupo individuais.
title: Editar o arquivo Email.asp
uuid: 18251170-0317-4a32-b9e1-4ebf2d7ad123
exl-id: e984f12f-362a-4dee-9af3-6d7a38a178a4
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 2%

---

# Editar o arquivo Email.asp{#edit-the-email-asp-file}

O acesso a permissões e no Portal de relatórios é controlado usando contas de usuário e grupo individuais.

Cada vez que você adiciona uma nova conta ou edita uma conta existente, um email de confirmação pode ser enviado para o endereço de email especificado para essa conta (consulte [Trabalhar com contas](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)) e copiado para os endereços de email especificados no arquivo [!DNL email.asp].

>[!NOTE]
>
>Os emails de notificação são enviados para usuários da conta somente quando você especifica um endereço de email para a conta e configura corretamente o arquivo [!DNL email.asp]. Se não quiser que emails de notificação sejam enviados para uma conta, deixe o campo de email da conta em branco.

Este arquivo reside na pasta `\*PortalName*\PortalASP`.

1. Na máquina em que o IIS está sendo executado, abra o arquivo [!DNL email.asp] em um editor de texto, como o Bloco de notas.
1. Defina as seguintes variáveis:

<table id="table_44F52DA266364DF993C40678A28E0F0D">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Para essa variável . . . </th>
   <th colname="col2" class="entry"> Forneça essas informações . . . </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> smtpserver </td>
   <td colname="col2"> <p>Nome DNS ou endereço IP do servidor SMTP pelo qual as mensagens são enviadas. </p> <p>Por exemplo: <span class="filepath"> mail.hq.omniture.com</span></p> </td>
  </tr>
  <tr>
   <td colname="col1"> smtpserverport </td>
   <td colname="col2"> A porta na qual o servidor SMTP escuta as conexões. Normalmente, é a porta 25. </td>
  </tr>
  <tr>
   <td colname="col1"> uso </td>
   <td colname="col2"> <p>Indica como a mensagem deve ser enviada. Os valores são: </p> <p>1 - Enviar mensagens usando o serviço SMTP instalado localmente. Use esse valor se o serviço SMTP estiver instalado no computador em que o script estiver sendo executado. </p> <p>2 - Enviar mensagens usando o serviço SMTP na rede. Use esse valor se o serviço SMTP não estiver instalado no computador em que o script estiver sendo executado. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> smtpconnectiontimeout </td>
   <td colname="col2">O tempo que <span class="wintitle"> Relatório</span> deve aguardar uma resposta do servidor SMTP antes de expirar a conexão. </td>
  </tr>
 </tbody>
</table>

1. Para as funções [!DNL NewUserEmail()] e [!DNL UpdateUserEmail()], defina as seguintes variáveis:

   <table id="table_91C5E36B84A94C4097EE5993592BE587">
   <thead>
   <tr>
      <th colname="col1" class="entry"> Para essa variável . . . </th>
      <th colname="col2" class="entry"> Forneça essas informações . . . </th>
   </tr>
   </thead>
   <tbody>
   <tr>
      <td colname="col1"> De </td>
      <td colname="col2">O texto que você deseja que apareça na linha de cabeçalho De nos emails de confirmação. Esse valor pode ser o mesmo do valor <span class="wintitle"> CC</span>. </td>
   </tr>
   <tr>
      <td colname="col1"> CC </td>
      <td colname="col2"> <p>Opcional. O endereço de email válido da pessoa ou alias que deve receber uma cópia de todas as mensagens relacionadas às contas de usuário novas e alteradas. Você pode especificar vários endereços de email separando os endereços com vírgulas (sem espaços). </p> <p>Por exemplo: <span class="filepath"> admin@company.com,joemanager@company.com</span></p> <p> <p>Observação:  Os recipients recebem cópias de emails que contêm senhas de usuário. </p> </p> </td>
   </tr>
   <tr>
      <td colname="col1"> Assunto </td>
      <td colname="col2"> O texto que você deseja que apareça na linha de cabeçalho Assunto nos emails de confirmação. </td>
   </tr>
   <tr>
      <td colname="col1"> WebPath </td>
      <td colname="col2"> <p>O caminho real para o portal. </p> <p>Por exemplo: <span class="filepath"> https://portal.omniture.com/Example</span></p> </td>
   </tr>
   <tr>
      <td colname="col1"> Corpo </td>
      <td colname="col2"> <p>O texto incluído nos emails gerados automaticamente. </p> <p>Por exemplo, a seguir está o texto padrão incluído nos emails enviados para fornecer informações de logon:
      <ul id="ul_7FF2E7399AB64D279EC5794AB02C9749">
      <li id="li_7CBCC5CFF9E04776BBC893278785AEE7">As informações de logon do portal da Web são fornecidas abaixo: </li>
      <li id="li_5346F0AB3568444B88117C295D8E99C5"><p>UserName: username </p><p>Nova senha: senha </p></li>
      <li id="li_B0D1FAE818BA42CF8546796800A1AA08"><p>Você pode acessar o portal usando o seguinte URL: </p><p><span class="filepath"> https://WebPath</span></p></li>
      <li id="li_7CD71EBDFA1D418F960040569CD511EB">Depois de fazer logon no portal, você pode alterar sua senha na guia <span class="wintitle"> Admin</span>. </li>
      </ul></p> </td>
   </tr>
   </tbody>
   </table>

1. Salve e feche o arquivo.
