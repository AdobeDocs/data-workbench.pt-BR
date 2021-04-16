---
description: Você deve monitorar regularmente seus arquivos de log de eventos para rastrear mensagens de evento do sistema do Insight Server, que são registradas nos arquivos <AAAAMMDD>-event.txt localizados por padrão na pasta Eventos no diretório de instalação do Insight Server.
title: Monitorar eventos administrativos
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
exl-id: e468a7d0-ed09-4367-88ce-b68964511e76
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 2%

---

# Monitorar eventos administrativos{#monitoring-administrative-events}

Você deve monitorar regularmente seus arquivos de log de eventos para rastrear mensagens de evento do sistema do Insight Server, que são registradas nos arquivos `<YYYYMMDD>-event.txt` localizados por padrão na pasta Eventos no diretório de instalação do Insight Server.

**Frequência recomendada:** a cada 5-10 minutos

Você pode monitorar esses eventos usando o [!DNL Server Files Manager] em [!DNL Insight], sua ferramenta de gerenciamento automatizado, os arquivos [!DNL *-event.txt] ou o Visualizador de Eventos do Windows.

>[!NOTE]
>
>Os Logs de evento administrativos são completamente separados do seu Registro de eventos do Windows, mas contêm alguns dos mesmos eventos. Os Logs de evento administrativos contêm informações somente sobre eventos [!DNL Insight Server].

**Para exibir os arquivos events.txt por meio da[!DNL Server Files Manager]**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile], clique na miniatura **[!UICONTROL Servers Manager]** para abrir o espaço de trabalho do Gerenciador de Servidores.
1. Clique com o botão direito do mouse no ícone de um [!DNL Insight Server] ativo e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique em **[!UICONTROL Events]** para visualizar seu conteúdo.
1. Clique com o botão direito do mouse na marca de seleção na coluna *server name* ao lado do arquivo desejado e clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece ao lado do nome do arquivo na coluna [!DNL Temp].
1. Clique com o botão direito do mouse na marca de seleção na coluna [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O arquivo de evento é exibido em uma nova janela do Bloco de Notas do Microsoft Windows.

   ![Informações da etapa](assets/vis_FileManager_eventfile.png)

   O arquivo [!DNL Server.log] na pasta [!DNL Trace] no diretório de instalação [!DNL Insight Server] contém informações de registro mais detalhadas.

**Para visualizar eventos através do Visualizador de eventos do Windows**

* Clique em **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**Para alterar o diretório Log de Eventos Administrativos**

O arquivo de configuração Logs de evento administrativos, [!DNL Administrative Events Log.cfg], especifica o diretório para o qual o registro de eventos é emitido.

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile], clique na miniatura **[!UICONTROL Servers Manager]** para abrir o espaço de trabalho do Gerenciador de Servidores.

1. Clique com o botão direito do mouse no ícone do [!DNL Insight Server] que deseja configurar e clique em **[!UICONTROL Server Files]**.

1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para visualizar seu conteúdo. O arquivo [!DNL Administrative Event Logs.cfg] está localizado dentro desse diretório.

1. Clique com o botão direito do mouse na marca de seleção na coluna *server name* para [!DNL Administrative Event Logs.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece na coluna [!DNL Temp] para [!DNL Administrative Event Logs.cfg].

1. Clique com o botão direito do mouse na marca de seleção recém-criada na coluna [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Na janela [!DNL Administrative Event Logs.cfg], clique em **[!UICONTROL component]** para visualizar seu conteúdo. O caminho padrão é a pasta [!DNL Events] no diretório de instalação [!DNL Insight Server].

   ![](assets/cfg_adminevents_examplevalues.png)

1. No parâmetro Path , digite o nome do diretório no qual deseja exibir os dados de registro do evento.
1. Salve as alterações no servidor fazendo o seguinte:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
   1. No [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na coluna [!DNL Temp] e selecione **[!UICONTROL Save to]** > **[!UICONTROL server name]**.
