---
description: Antes de gerar relatórios e alertas, você deve configurar o Servidor de relatórios para especificar o endereço do servidor Insight e identificar os perfis com os quais deseja criar relatórios.
solution: Analytics
title: Configuração da conexão com o servidor Insight
topic: Data workbench
uuid: 2018b67e-90a6-41d7-b628-4b463869df6e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuração da conexão com o servidor Insight{#configuring-the-connection-to-the-insight-server}

Antes de gerar relatórios e alertas, você deve configurar o Servidor de relatórios para especificar o endereço do servidor Insight e identificar os perfis com os quais deseja criar relatórios.

>[!NOTE]
>
>Até configurar o Servidor de relatórios conforme descrito abaixo, você não poderá executar o Servidor de relatórios com êxito. Se você tentar executar o Servidor de relatórios com o arquivo não configurado instalado com o programa, o Servidor de relatórios produzirá um fluxo de erros.

**Para configurar o Servidor de relatórios**

1. Com o Windows Explorer, navegue até o diretório onde você instalou o Servidor de relatórios.
1. Abra o [!DNL ReportServer.cfg] arquivo no Bloco de notas e modifique o arquivo conforme desejado.

   A amostra a seguir [!DNL Report Server.cfg] contém apenas os parâmetros incluídos no [!DNL Report Server.cfg] arquivo por padrão (e destaca as configurações de parâmetro necessárias). Se você entrar em contato com o Adobe License Server por meio de um servidor proxy, precisará adicionar o vetor de licenciamento e seus parâmetros. Consulte Parâmetros [do](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-svr-param.md#concept-53359b328fd140d593c3f2fc0031be06) Report Server.cfg para obter uma descrição detalhada.

   ```
   Fonts = vector: 0 items
   Gamma = float: 1.6
   Network Location = string: NetworkLocationName
   Servers = vector: 1 items
     0 = serverInfo:
       Address = string: ServerIPAddress
       Name = string: 
       Port = int: 443
       Proxy Address = string:
       Proxy Password = string:
       Proxy Port = int: 8080
       Proxy User Name = string:
       SSL Client Certificate = string: ReportCertFileName.pem
       SSL Server Common Name = string: ServerCommonName
       Use SSL = bool: true
   Result Memory Limit (KB) = double: 100000
   Maximum Slice Size = int: 30
   Use OpenGL Hardware Rendering = bool: true
   Reporting = :
     Profiles = vector: 1 items
       0 = ReportProfile:
         Server = string: ServerCommonName
         Profile = string: ProfileName
     Update Interval (minutes) = int: 10
     Completion Message Interval (seconds) = int: 600
     Status interval (seconds) = int: 600
     SMTP Server for Errors = string: SMTPServerHostName
     SMTP Server for Errors Username = string: SMTPServerUsername
     SMTP Server for Errors Password = string: SMTPServerPassword
     SMTP Server for Errors Send From = string: SenderAddress
     SMTP Server for Errors Send To = string: RecipientAddresses
   ```

1. Salve e feche o arquivo.
