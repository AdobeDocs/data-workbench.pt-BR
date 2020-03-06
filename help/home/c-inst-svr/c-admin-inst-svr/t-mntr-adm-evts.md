---
description: Você deve monitorar regularmente seus arquivos de log de eventos para rastrear mensagens de evento do sistema do Insight Server, que são registradas nos arquivos <AAAMMDD>-event.txt localizados por padrão na pasta Eventos dentro do diretório de instalação do Insight Server.
solution: Insight
title: Monitoramento de eventos administrativos
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Monitoramento de eventos administrativos{#monitoring-administrative-events}

Você deve monitorar regularmente seus arquivos de registro de eventos para rastrear mensagens de evento do sistema do Insight Server, que são registradas nos `<YYYYMMDD>-event.txt` arquivos localizados por padrão na pasta Eventos dentro do diretório de instalação do Insight Server.

**Frequência recomendada:** A cada 5 a 10 minutos

Você pode monitorar esses eventos usando o [!DNL Server Files Manager] em, sua ferramenta de gerenciamento automatizado, os [!DNL Insight][!DNL *-event.txt] arquivos ou o Visualizador de eventos do Windows.

>[!NOTE]
>
>Os Registros de eventos administrativos são completamente separados do seu Registro de eventos do Windows, mas contêm alguns dos mesmos eventos. Os Logs de eventos administrativos contêm informações somente sobre [!DNL Insight Server] eventos.

**Para exibir os arquivos events.txt por meio do[!DNL Server Files Manager]**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a área de trabalho do Gerenciador de servidores.
1. Clique com o botão direito do mouse no ícone de um ativo [!DNL Insight Server] e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique em **[!UICONTROL Events]** para exibir o conteúdo.
1. Clique com o botão direito do mouse na marca de seleção na coluna nome *do* servidor ao lado do arquivo desejado e clique em **[!UICONTROL Make Local]**. Uma marca de seleção é exibida ao lado do nome do arquivo na [!DNL Temp] coluna.
1. Clique com o botão direito do mouse na marca de seleção na [!DNL Temp] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O arquivo de evento é exibido em uma nova janela do Bloco de notas do Microsoft Windows.

   ![Informações da etapa](assets/vis_FileManager_eventfile.png)

   O [!DNL Server.log] arquivo na [!DNL Trace] pasta no diretório de [!DNL Insight Server] instalação contém informações de registro mais detalhadas.

**Para exibir eventos por meio do Visualizador de eventos do Windows**

* Clique em **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**Para alterar o diretório Log de eventos administrativos**

O arquivo de configuração Logs de eventos administrativos, [!DNL Administrative Events Log.cfg], especifica o diretório para o qual o registro de eventos é gerado.

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a área de trabalho do Gerenciador de servidores.

1. Clique com o botão direito do mouse no ícone do [!DNL Insight Server] que deseja configurar e clique em **[!UICONTROL Server Files]**.

1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para exibir o conteúdo. O [!DNL Administrative Event Logs.cfg] arquivo está localizado dentro deste diretório.

1. Clique com o botão direito do mouse na marca de seleção na coluna de nome *do* servidor para [!DNL Administrative Event Logs.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção é exibida na [!DNL Temp] coluna para [!DNL Administrative Event Logs.cfg].

1. Clique com o botão direito do mouse na marca de seleção recém-criada na [!DNL Temp] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Na [!DNL Administrative Event Logs.cfg] janela, clique **[!UICONTROL component]** para exibir seu conteúdo. O caminho padrão é a [!DNL Events] pasta no diretório de [!DNL Insight Server] instalação.

   ![](assets/cfg_adminevents_examplevalues.png)

1. No parâmetro Caminho, digite o nome do diretório no qual você deseja exibir os dados de registro do evento.
1. Salve as alterações no servidor da seguinte maneira:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
   1. Na [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL Temp] coluna e selecione **[!UICONTROL Save to]** > **[!UICONTROL server name]**.

