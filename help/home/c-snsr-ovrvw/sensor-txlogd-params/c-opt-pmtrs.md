---
description: Informações sobre parâmetros de arquivo opcionais do Sensor txlogd.conf.
title: Parâmetros opcionais
uuid: 8515a571-93ce-49cd-9ded-c9273259d0ee
exl-id: 5141f215-979c-4eb8-8c2c-94eef5815743
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1484'
ht-degree: 1%

---

# Parâmetros opcionais{#optional-parameters}

Informações sobre parâmetros de arquivo opcionais do Sensor txlogd.conf.

<table id="table_5FF491A7A6C24E43A06A5C344BF05430"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> AddressFilter </td> 
   <td colname="col2"> <p>Permite filtrar endereços IP especificados. </p> <p>Ao filtrar um endereço específico, um "pacote" não é registrado. Esse recurso elimina agentes internos ou monitorados antes do processamento de log, aumentando assim a velocidade do processamento de log e reduzindo os requisitos de armazenamento de dados. Você pode usar curingas ao especificar endereços. </p> <p>Exemplo: <span class="filepath"> AddressFilter 10.0.0.000</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ContentFilterInclude </p> <p>ContentFilterExclude </p> </td> 
   <td colname="col2"> <p>Especifique se deseja incluir ou excluir determinados tipos de conteúdo do log. </p> <p>Os valores de parâmetro são correspondência de prefixo em relação ao tipo de conteúdo da resposta. </p> <p>Por exemplo, "image/" corresponde a todos os tipos de conteúdo de imagem, enquanto "image/gif" corresponde somente a esse tipo. Quando ocorrem várias correspondências para um determinado tipo de conteúdo, a correspondência mais específica é usada. Portanto, você pode colocar "image/gif" no parâmetro ContentFilterInclude e "image/" no parâmetro ContentFilterExclude e as respostas "image/gif" são permitidas, mas todos os outros tipos de imagem são filtrados. </p> <p>Exemplo: <span class="filepath"> ContentFilterInclude *</span> </p> <p>Exemplo: <span class="filepath"> ContentFilterExclude image/,text/css,application/x-javascript</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DebugLogPath </td> 
   <td colname="col2"> <p>Defina esse parâmetro somente ao trabalhar com os Serviços de consultoria do Adobe. </p> <p>Ativa o log de depuração para o módulo da Web e o transmissor. </p> <p>Use esse parâmetro quando o <span class="wintitle"> Sensor</span> não estiver funcionando corretamente. Depois que este parâmetro for definido, você deve criar um arquivo vazio no local do caminho especificado e conceder direitos de "gravação" a ele para todos os usuários. Por exemplo (dentro de um shell unix no servidor da Web): 
     <ul id="ul_7A067014A78048BF9D2F23DC66FF9E24"> 
      <li id="li_11C51EB9B9CC431585ECE9E8648F6122"><span class="filepath"> % cd /var/log</span> </li> 
      <li id="li_C56B2B5D49A543DBB258C5DE099B4AE5"><span class="filepath"> % touch vslog.txt</span> </li> 
      <li id="li_DA914383F813453AB6EF4F89279FD786"><span class="filepath"> % chmod a+w vslog.txt</span> </li> 
     </ul> </p> <p>Você deve ativar o log de depuração por apenas um curto período de tempo, depois o arquivo de log deve ser enviado para os Serviços de consultoria do Adobe para análise. </p> <p>Exemplo: <span class="filepath"> DebugLogPath /var/log/vslog.txt</span> </p> <p>O Adobe recomenda que esse parâmetro seja definido primeiro em um ambiente de teste para determinar o efeito no sistema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DisableField </td> 
   <td colname="col2"> <p>Desativa o campo especificado </p> <p>Os usuários podem eliminar campos que não usam ou que não desejam armazenar. Se o campo receber valores de string, desativá-lo passará uma string em branco. Se o campo receber valores numéricos, desativá-lo passará o número zero (0). Você pode desativar os seguintes campos: 
     <ul id="ul_4537B345EFAE449A9946DA0B52EA5C43"> 
      <li id="li_D674BC1982344C49B25A73EFF095C34A">sc-status </li> 
      <li id="li_6D647C845EB54B1B84C756DCDD7DD4CC">x-new-visitor </li> 
      <li id="li_65EB695B223040BCB9888375354B6E8B">x-trackingid </li> 
      <li id="li_41197A9CB961496B9CD26AA8457233FD">sc-bytes </li> 
      <li id="li_DCD45D7E21964B959299494FA719F453">c-ip </li> 
      <li id="li_7650796C6246484C8267ED9923596AFB">cs-method </li> 
      <li id="li_8941FCBBAA5E42EA9F04DA06EB91CAC5">cs-uri-stem </li> 
      <li id="li_A10438D2DEBB4ADFB574BF7094F9F0C4">cs-uri-query </li> 
      <li id="li_1D83BA59AC8543319D1966BB8ED1D931">s-dns </li> 
      <li id="li_34A23CE1944F4AEFBE7D74E8D6D5BEE6">cs(referrer) </li> 
      <li id="li_B85D93C381BD440F82C711C9A6D56CE9">cs(cookie) </li> 
      <li id="li_18D9C084450149D6A8713EBDA0C02E5B">cs(user-agent) </li> 
      <li id="li_A175CAF03E51473E990BE4F31F198B42">cs(useragent) </li> 
      <li id="li_ED38ED31B2644F2FA1C86FF93ADB9CEF">sc(content-type) </li> 
      <li id="li_1173C0027C8A4638BDF35E9719CD9D4C">experimento com x </li> 
     </ul> </p> <p>Exemplo: <span class="filepath"> DisableField x-trackingid</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpFile </td> 
   <td colname="col2"> <p>Caminho para o arquivo de configuração de Experimento controlado. </p> <p>Exemplo: <span class="filepath"> ExpFile C:\VisualSensor\experiment.txt</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpCookieURL </td> 
   <td colname="col2"> <p>Recurso que, quando solicitado, faz com que uma nova ID de rastreamento seja gerada e o usuário seja colocado em um grupo de experimentos. </p> <p> <p>Observação:  Esse recurso não precisa existir fisicamente no servidor da Web. </p> </p> <p>Exemplo: <span class="filepath"> ExpCookieURL /setcookie.htm</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpPartialMatch </td> 
   <td colname="col2"> <p>Se você quiser permitir que seus experimentos controlados remapeiem todo o site ou um subdiretório inteiro do site para outro local, defina este parâmetro como "ativado". O padrão é "off". </p> <p>Exemplo: <span class="filepath"> ExpPartialMatch off</span> </p> <p> <p>Observação:  Tenha muito cuidado ao definir este parâmetro como "ativado". </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LogAllNewUsers </td> 
   <td colname="col2"> <p>Determina se o primeiro clique de cada novo usuário é registrado mesmo se o usuário solicitar um tipo de documento filtrado pelo parâmetro ContentFilterExclude . </p> <p>O padrão é "não". </p> <p>Normalmente, os arquivos de imagem são filtrados pelo parâmetro ContentFilterExclude . Se LogAllNewUsers estiver definido como "yes" e o primeiro documento que um novo usuário obtém do servidor for uma imagem, essa solicitação será registrada. Se o parâmetro LogAllNewUsers estiver definido como "não" ou não estiver definido (e supondo que as imagens sejam filtradas pelo parâmetro ContentFilterExclude ) e o primeiro documento que um novo usuário obtém do servidor for uma imagem, essa solicitação não será registrada. </p> <p>Exemplo: <span class="filepath"> LogAllNewUsers no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> MaxPageLoadTime </td> 
   <td colname="col2"> <p>O tempo em segundos que o transmissor aguarda para enviar o próximo lote de pacotes. </p> <p>O padrão é 15. </p> <p>Exemplo: <span class="filepath"> MaxPageLoadTime 15</span> </p> <p> <p>Observação:  Não altere esse valor de parâmetro sem entrar em contato primeiro com os Serviços de consultoria do Adobe. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> PrivacyID </td> 
   <td colname="col2"> <p>Permite desativar o rastreamento de visitantes, que pode ser usado para estar em conformidade com as políticas de não participação. </p> <p>Quando ativado, o <span class="wintitle"> Sensor</span> não registra um "pacote" para qualquer visitante cujo cookie V1st esteja definido como PrivacyID especificado. Como nenhuma informação é registrada para esses visitantes, nenhuma informação sobre esses visitantes é enviada para o <span class="keyword"> servidor do Data Workbench</span> para processamento. </p> <p>Para ativar esse recurso, você deve concluir as seguintes etapas: 
     <ol id="ol_5D658C5E4AB14F419029E0FFC52F1310"> 
      <li id="li_BF056439F92148169BF592731264C3CD"> PrivacyID deve ser definido com um valor de 0 (zero) no arquivo <span class="filepath"> txlogd.conf</span> do Sensor <span class="wintitle"></span>. <p>Exemplo: <span class="filepath"> PrivacyID 0</span> </p> </li> 
      <li id="li_3E20F068C2F94512A92F284C80273B1C">Os proprietários do site devem gravar o código para definir cookies de visitante (V1st) de modo que o valor da ID de cookie corresponda ao valor da ID de privacidade definido por "<span class="filepath"> txlogd.conf</span>". </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SiteTest </td> 
   <td colname="col2"> <p>Local para o qual o transmissor (txlogd) envia periodicamente solicitações para ver se o site está funcionando corretamente. </p> <p>Observe que a localização é especificada no seguinte formato, não como URL: </p> <p>http,<i>serverAddress,port,/resource</i> </p> <p>onde <i>serverAddress</i> é o nome do servidor ou endereço IP, <i>port</i> é a porta de escuta HTTP do servidor e <i>resource</i> é o recurso específico a ser solicitado (pode incluir uma cadeia de consulta). </p> <p>Você pode especificar várias linhas do SiteTest . </p> <p>Exemplo: <span class="filepath"> SiteTest http,localhost,80,/test.html</span> </p> <p> <p>Observação:  Somente http é compatível no momento. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackingCookie </td> 
   <td colname="col2"> <p>O nome do cookie definido no navegador do visitante. </p> <p>O padrão é "v1st". </p> <p>Exemplo: <span class="filepath"> TrackingCookie v1st</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VerifyCertName </td> 
   <td colname="col2"> <p>Indica se o servidor deve ser validado em relação ao parâmetro CertName </p> <p>O padrão é "on". </p> <p>Exemplo: <span class="filepath"> VerifyCertName em</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_598C3CDA5AA440228AF88C3BE4A8F77C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> IISCaptureBytesSent </td> 
   <td colname="col2"> <p>Defina esse parâmetro somente ao trabalhar com os Serviços de consultoria do Adobe. </p> <p>Informa ao Sensor <span class="wintitle"> do IIS</span> qual de dois possíveis "ganchos" de registro deve ser usado para registrar um pacote </p> <p>Use esse parâmetro quando o Sensor do IIS <span class="wintitle"></span> não estiver registrando pacotes corretamente. Esse parâmetro seria definido como "off" se o gancho de log padrão não estivesse funcionando corretamente. O padrão é "on". </p> <p>Exemplo: <span class="filepath"> IISCaptureBytesEnviados em</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IISUseAlternateHandler </td> 
   <td colname="col2"> <p>Defina esse parâmetro somente ao trabalhar com os Serviços de consultoria do Adobe. </p> <p>Informa ao <span class="wintitle"> Sensor</span> qual de dois "ganchos" possíveis deve ser usado para definir o cookie v1st. </p> <p>Você usa esse parâmetro quando o Sensor do IIS <span class="wintitle"></span> não está configurando o cookie v1st corretamente. Esse parâmetro seria definido como "sim" se o gancho padrão não estivesse configurando o cookie v1st corretamente. O padrão é "não". </p> <p>Exemplo: <span class="filepath"> IISUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>Por padrão, <span class="wintitle"> Sensor</span> envia cabeçalhos de resposta de controle de cache em cada solicitação. Quando o recurso de controle de cache está ativado, o <span class="wintitle"> Sensor</span> envia um cabeçalho Expires com um valor Thu, 01 de dezembro de 1994 16:00:00 GMT para o navegador. </p> <p>Você pode modificar as cadeias de caracteres de resposta conforme desejado editando as duas linhas a seguir no arquivo <span class="filepath"> txlogd.conf</span>: </p> <p> <span class="filepath"> </span> <i>&lt;&gt; NewUserCacheControlstring1</span>&gt;</i><span class="filepath"> </span></p> <p> <span class="filepath"> </span> <i>&lt;&gt; CacheControlstring2</span>&gt;</i><span class="filepath"> </span></p> <p>Exemplo: </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl private,max-age=0,must-revalidate</span> </p> <p>Para desativar o envio de cabeçalhos de resposta de controle de cache, digite um hífen para cada linha, como mostrado abaixo: </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_88696CCA93874BB683538BD614E07890"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Neste Parâmetro... </th> 
   <th colname="col2" class="entry"> Especificar... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>Defina esse parâmetro somente ao trabalhar com os Serviços de consultoria do Adobe. </p> <p>Informa ao <span class="wintitle"> Sensor</span> qual de dois "ganchos" possíveis deve ser usado para definir o cookie v1st. </p> <p>Use esse parâmetro quando o Apache <span class="wintitle"> Sensor</span> não estiver configurando o cookie v1st corretamente. Esse parâmetro seria definido como "sim" se o gancho padrão não estivesse configurando o cookie v1st corretamente. O padrão é "não". </p> <p>Exemplo: <span class="filepath"> ApacheUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseAmbosHandlers </td> 
   <td colname="col2"> <p>Defina esse parâmetro somente ao trabalhar com os Serviços de consultoria do Adobe. </p> <p>Instrui o <span class="wintitle"> Sensor</span> a tentar definir o cookie v1st em ambos os ganchos. </p> <p>Use esse parâmetro quando o Apache <span class="wintitle"> Sensor</span> não estiver configurando o cookie v1st corretamente. O padrão é "sim". </p> <p>Se definido como "sim" e o cookie v1st não estiver definido corretamente no primeiro gancho, o segundo gancho será usado. Se definido como "não", você definiria o parâmetro ApacheUseAlternateHandler para indicar qual gancho usar para definir o cookie v1st. </p> <p>Exemplo: <span class="filepath"> ApacheUseAmbosHandlers yes</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>Por padrão, <span class="wintitle"> Sensor</span> envia cabeçalhos de resposta de controle de cache em cada solicitação. Quando o recurso de controle de cache está ativado, o <span class="wintitle"> Sensor</span> envia um cabeçalho Expires com um valor Thu, 01 de dezembro de 1994 16:00:00 GMT para o navegador. </p> <p>Você pode modificar as cadeias de caracteres de resposta conforme desejado editando as duas linhas a seguir no arquivo <span class="filepath"> txlogd.conf</span>: </p> <p> <span class="filepath"> </span> <i>&lt;&gt; NewUserCacheControlstring1</span>&gt;</i><span class="filepath"> </span></p> <p> <span class="filepath"> </span> <i>&lt;&gt; CacheControlstring2</span>&gt;</i><span class="filepath"> </span></p> <p>Exemplo: </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl private,max-age=0,must-revalidate</span> </p> <p>Para desativar o envio de cabeçalhos de resposta de controle de cache, digite um hífen para cada linha, como mostrado abaixo: </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> <p> <p>Observação:  O Adobe recomenda que você não desative esse recurso. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_BF01F6265B8544DA9D9AD2C80A64C0F3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Neste Parâmetro... </th> 
   <th colname="col2" class="entry"> Especificar... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>Defina esse parâmetro somente ao trabalhar com os Serviços de consultoria do Adobe. </p> <p>Informa ao <span class="wintitle"> Sensor</span> qual de dois "ganchos" possíveis deve ser usado para definir o cookie v1st. </p> <p>Use esse parâmetro quando o Apache <span class="wintitle"> Sensor</span> não estiver configurando o cookie v1st corretamente. Esse parâmetro seria definido como "sim" se o gancho padrão não estivesse configurando o cookie v1st corretamente. O padrão é "não". </p> <p>Exemplo: <span class="filepath"> ApacheUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseAmbosHandlers </td> 
   <td colname="col2"> <p>Defina esse parâmetro somente ao trabalhar com os Serviços de consultoria do Adobe. </p> <p>Instrui o <span class="wintitle"> Sensor</span> a tentar definir o cookie v1st em ambos os ganchos. </p> <p>Use esse parâmetro quando o Apache <span class="wintitle"> Sensor</span> não estiver configurando o cookie v1st corretamente. O padrão é "sim". </p> <p>Se definido como "sim" e o cookie v1st não estiver definido corretamente no primeiro gancho, o segundo gancho será usado. Se definido como "não", você definiria o parâmetro ApacheUseAlternateHandler para indicar qual gancho usar para definir o cookie v1st. </p> <p>Exemplo: <span class="filepath"> ApacheUseAmbosHandlers yes</span> </p> </td> 
  </tr> 
 </tbody> 
</table>
