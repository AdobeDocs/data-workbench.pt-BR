---
description: Antes de gerar relatórios e alertas, você deve configurar o Servidor de relatórios para especificar o endereço do servidor Insight e identificar os perfis para os quais deseja criar relatórios.
title: Configuração da conexão com o servidor Insight
uuid: 2018b67e-90a6-41d7-b628-4b463869df6e
exl-id: a398a665-fe09-448a-977c-b0f9de4add09
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 7%

---

# Configuração da conexão com o servidor Insight{#configuring-the-connection-to-the-insight-server}

Antes de gerar relatórios e alertas, você deve configurar o Servidor de relatórios para especificar o endereço do servidor Insight e identificar os perfis para os quais deseja criar relatórios.

>[!NOTE]
>
>Até configurar o Servidor de relatórios conforme descrito abaixo, você não poderá executar o Servidor de relatórios com êxito. Se você tentar executar o Report Server com o arquivo não configurado que está instalado com o programa, o Report Server produzirá um fluxo de erros.

**Configurar o servidor de relatórios**

1. Com o Windows Explorer, navegue até o diretório onde você instalou o Report Server.
1. Abra o arquivo [!DNL ReportServer.cfg] no Bloco de notas e modifique o arquivo conforme desejado.

   A amostra a seguir [!DNL Report Server.cfg] contém apenas os parâmetros incluídos no arquivo [!DNL Report Server.cfg] por padrão (e destaca as configurações de parâmetro necessárias). Se você entrar em contato com o Adobe License Server por meio de um servidor proxy, será necessário adicionar o vetor de Licenciamento e seus parâmetros. Consulte [Parâmetros do Report Server.cfg](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-svr-param.md#concept-53359b328fd140d593c3f2fc0031be06) para obter uma descrição detalhada.

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
