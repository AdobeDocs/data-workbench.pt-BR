---
description: Procedimento para iniciar o Insight Server e registrá-lo simultaneamente como um Serviço Microsoft Windows.
title: Registrar o servidor Insight como um serviço do Windows
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
exl-id: ba74d4c0-5d99-47a4-8b92-c65d0ec514e2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 3%

---

# Registrar o servidor Insight como um serviço do Windows{#registering-insight-server-as-a-windows-service}

Procedimento para iniciar o Insight Server e registrá-lo simultaneamente como um Serviço Microsoft Windows.

>[!NOTE]
>
>Ao iniciar [!DNL Insight Server] pela primeira vez, ele se conecta automaticamente ao Adobe License Server para registrar seu certificado digital. Para concluir o processo de registro com êxito, a máquina deve estar conectada à Internet ao executar as etapas a seguir.

**Para iniciar  [!DNL Insight Server] e registrá-lo como um Serviço do Windows**

1. Abra um prompt de comando e navegue até o subdiretório bin, na pasta onde você instalou [!DNL Insight Server].

   Exemplo: [!DNL C:\Adobe\Server\bin]

1. No prompt de comando, execute o seguinte comando para iniciar [!DNL Insight Server] e, simultaneamente, registre-o para ser executado como um serviço no Microsoft Windows:

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. Para confirmar que [!DNL Insight Server] está sendo executado corretamente, clique em **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Essa sequência de comandos pode variar dependendo da versão do Windows que você estiver usando.

   1. Na lista de serviços, localize a entrada para **[!DNL Adobe Insight Server]** e confirme se seu status é Iniciado e se seu tipo de inicialização é Automático.
   1. Feche o painel de controle Serviços .

1. Para verificar se [!DNL Insight Server] teve erros durante a inicialização, clique em **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Essa sequência de comandos pode variar dependendo da versão do Windows que você estiver usando.

   1. No painel esquerdo da janela [!DNL Event Viewer], selecione o log **[!UICONTROL Application]**.
   1. No painel direito, procure por eventos com &quot;Adobe&quot; na coluna [!DNL Source] .
   1. Se você encontrar um erro de &quot;Adobe&quot;, clique duas vezes no erro para exibir a janela [!DNL Event Properties]. Esta janela fornece informações detalhadas sobre o erro.

1. Quando terminar de examinar o log [!DNL Applications], feche o Visualizador de Eventos.

Você concluiu a instalação de [!DNL Insight Server]. [!DNL Insight Server] foi concebido para funcionar continuamente. Se você reiniciar a máquina, [!DNL Insight Server] será reiniciado automaticamente. Se você precisar iniciar e parar [!DNL Insight Server] manualmente, poderá fazer isso usando o Painel de controle dos Serviços no Windows. Conforme descrito na seção a seguir, você pode opcionalmente configurar o serviço [!DNL Insight Server] para reiniciar automaticamente periodicamente.

## Configurar o serviço para reiniciar automaticamente {#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] foi projetado para continuar a funcionar sem interrupções. Normalmente, ele é interrompido ou iniciado apenas ao executar tarefas pouco frequentes, como atualizações de software ou alterações de certificado, ou no caso de determinados erros do sistema. Não é necessário interromper ou reiniciar o serviço [!DNL Insight Server] durante o funcionamento normal do sistema; no entanto, você pode configurar o serviço para reiniciar periodicamente (diariamente, semanalmente ou mensalmente) para, por exemplo, limpar as mensagens do evento.

**Para configurar o  [!DNL Insight Server] serviço para reiniciar automaticamente**

1. Navegue até a pasta [!DNL Components] no diretório em que você instalou [!DNL Insight Server].

   Exemplo: [!DNL C:\Adobe\Server\Components]

1. Use um editor de texto como o Bloco de notas para criar um novo arquivo chamado [!DNL ScheduledRestart.cfg].
1. Insira o seguinte texto no arquivo [!DNL ScheduledRestart.cfg]:

   ```
   component = ScheduledRestart:  
     Start Time = string: Month DD, YYYY HH:MM:SS TZone 
     Restart Every = string: frequency
   ```

   <table id="table_AC05861E141E4928BE844C8611DEC43D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Para este valor... </th> 
      <th colname="col2" class="entry"> Especificar </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <i>Mês DD, AAAA HH:MM:SS TZone</i> </td> 
      <td colname="col2"> <p>A hora em que você deseja que <span class="keyword"> Servidor Insight </span> seja reiniciado pela primeira vez. </p> <p>Exemplo: 13 de agosto de 2013 22:30:00 EST </p> <p> <p>Observação:  Você deve especificar um fuso horário. O fuso horário não é padrão para a hora do sistema, caso não seja especificado. Se quiser implementar o Horário de verão ou uma política de mudança de relógio semelhante, salve o arquivo <span class="filepath"> .dst </span> contendo as regras apropriadas na máquina Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server </span>. Para obter uma lista de abreviações de fuso horário compatíveis e informações sobre a implementação do Horário de verão, consulte <a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Códigos de fuso horário </a>. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>frequência</i> </td> 
      <td colname="col2"> <p>Um dos seguintes valores: 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">mês </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C">semana </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">dia </li> 
       </ul> </p> <p>Para indicar a frequência na qual você deseja que <span class="keyword"> Servidor Insight </span> seja reiniciado após o tempo inicial especificado em Hora de início. </p> <p>Por exemplo, se você quiser que <span class="keyword"> Servidor Insight </span> seja reiniciado uma vez por semana, defina esse valor como "semana". </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Salve o arquivo [!DNL ScheduledRestart.cfg].

   Verifique se o arquivo [!DNL ScheduledRestart.cfg] está na pasta [!DNL Components] no diretório em que você instalou [!DNL Insight Server].
