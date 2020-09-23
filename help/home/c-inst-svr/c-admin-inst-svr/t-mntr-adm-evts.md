---
description: Você deve monitorar regularmente os arquivos de registro de eventos para rastrear as mensagens de evento do sistema do Insight Server, que são registradas nos arquivos <AAAMMDD>-evento.txt localizados por padrão na pasta Eventos no diretório de instalação do Insight Server.
solution: Analytics
title: Monitorar eventos administrativos
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 2%

---


# Monitorar eventos administrativos{#monitoring-administrative-events}

Você deve monitorar regularmente os arquivos de registro de eventos para rastrear as mensagens de evento do sistema do Insight Server, que são registradas nos arquivos localizados por padrão na pasta Eventos no diretório de instalação do Insight Server. `<YYYYMMDD>-event.txt`

**Frequência recomendada:** A cada 5 a 10 minutos

Você pode monitorar esses eventos usando o [!DNL Server Files Manager] In, sua ferramenta de gerenciamento automatizado, os [!DNL Insight][!DNL *-event.txt] arquivos ou o Visualizador de Eventos do Windows.

>[!NOTE]
>
>Os Logs de Eventos administrativos são completamente separados do Registro de Eventos do Windows, mas contêm alguns dos mesmos eventos. Os Logs de Eventos administrativos contêm informações somente sobre [!DNL Insight Server] eventos.

**Para visualização de arquivos eventos.txt por meio do[!DNL Server Files Manager]**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a área de trabalho do Gerenciador de servidores.
1. Clique com o botão direito do mouse no ícone de um ativo [!DNL Insight Server] e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique **[!UICONTROL Events]** para visualização do conteúdo.
1. Clique com o botão direito do mouse na marca de seleção na coluna nome *do* servidor ao lado do arquivo desejado e clique em **[!UICONTROL Make Local]**. Uma marca de seleção é exibida ao lado do nome do arquivo na [!DNL Temp] coluna.
1. Clique com o botão direito do mouse na marca de seleção na [!DNL Temp] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O arquivo de evento é exibido em uma nova janela do Bloco de notas do Microsoft Windows.

   ![Informações da etapa](assets/vis_FileManager_eventfile.png)

   O [!DNL Server.log] arquivo na [!DNL Trace] pasta no diretório de [!DNL Insight Server] instalação contém informações de registro mais detalhadas.

**Para visualização de Eventos pelo Visualizador de Eventos do Windows**

* Clique em **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**Para alterar o diretório Log de Eventos Administrativos**

O arquivo de configuração Logs do Evento Administrativo [!DNL Administrative Events Log.cfg], especifica o diretório para o qual o registro de eventos é gerado.

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a área de trabalho do Gerenciador de servidores.

1. Clique com o botão direito do mouse no ícone do [!DNL Insight Server] que deseja configurar e clique em **[!UICONTROL Server Files]**.

1. No [!DNL Server Files Manager], clique **[!UICONTROL Components]** para visualização do conteúdo. O [!DNL Administrative Event Logs.cfg] arquivo está localizado dentro deste diretório.

1. Clique com o botão direito do mouse na marca de seleção na coluna de nome *do* servidor para [!DNL Administrative Event Logs.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção é exibida na [!DNL Temp] coluna para [!DNL Administrative Event Logs.cfg].

1. Clique com o botão direito do mouse na marca de seleção recém-criada na [!DNL Temp] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Na [!DNL Administrative Event Logs.cfg] janela, clique **[!UICONTROL component]** para visualização do conteúdo. O caminho padrão é a [!DNL Events] pasta no diretório de [!DNL Insight Server] instalação.

   ![](assets/cfg_adminevents_examplevalues.png)

1. No parâmetro Caminho, digite o nome do diretório no qual deseja exibir os dados de registro de eventos.
1. Salve as alterações no servidor da seguinte maneira:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
   1. Na [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL Temp] coluna e selecione **[!UICONTROL Save to]** > **[!UICONTROL server name]**.

