---
description: Procedimento para iniciar o Insight Server e registrá-lo simultaneamente como um Microsoft Windows Service.
title: Registrar o servidor Insight como um serviço do Windows
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
exl-id: ba74d4c0-5d99-47a4-8b92-c65d0ec514e2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 3%

---

# Registrar o servidor Insight como um serviço do Windows{#registering-insight-server-as-a-windows-service}

{{eol}}

Procedimento para iniciar o Insight Server e registrá-lo simultaneamente como um Microsoft Windows Service.

>[!NOTE]
>
>Ao iniciar [!DNL Insight Server] pela primeira vez, ele se conecta automaticamente ao Adobe License Server para registrar seu certificado digital. Para concluir o processo de registro com êxito, a máquina deve estar conectada à Internet ao executar as etapas a seguir.

**Para começar [!DNL Insight Server] e registrá-lo como um Serviço do Windows**

1. Abra um prompt de comando e navegue até o subdiretório bin, na pasta onde você instalou o [!DNL Insight Server].

   Exemplo: [!DNL C:\Adobe\Server\bin]

1. No prompt de comando, execute o seguinte comando para iniciar [!DNL Insight Server] e registre-o simultaneamente para ser executado como um serviço no Microsoft Windows:

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. Para confirmar que [!DNL Insight Server] estiver sendo executado corretamente, clique em **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Essa sequência de comandos pode variar dependendo da versão do Windows que você estiver usando.

   1. Na lista de serviços, localize a entrada para **[!DNL Adobe Insight Server]** e confirme se o status é Started e se o tipo de inicialização é Automatic.
   1. Feche o painel de controle Serviços .

1. Para verificar se [!DNL Insight Server] ocorreu qualquer erro durante a inicialização, clique em **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Essa sequência de comandos pode variar dependendo da versão do Windows que você estiver usando.

   1. No painel esquerdo do [!DNL Event Viewer] selecione a **[!UICONTROL Application]** log.
   1. No painel direito, procure por eventos com &quot;Adobe&quot; no [!DNL Source] coluna.
   1. Se você encontrar um erro de &quot;Adobe&quot;, clique duas vezes no erro para exibir a variável [!DNL Event Properties] janela. Esta janela fornece informações detalhadas sobre o erro.

1. Quando terminar de examinar a [!DNL Applications] , feche o Visualizador de eventos.

Você concluiu a instalação do [!DNL Insight Server]. [!DNL Insight Server] foi concebido para funcionar continuamente. Se você reiniciar a máquina, [!DNL Insight Server] é reiniciado automaticamente. Se precisar começar e parar [!DNL Insight Server] manualmente, você pode fazer isso usando o painel de controle Serviços no Windows. Conforme descrito na seção a seguir, você pode configurar opcionalmente [!DNL Insight Server] para reiniciar automaticamente periodicamente.

## Configurar o serviço para reiniciar automaticamente {#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] foi projetado para continuar a funcionar sem interrupções. Normalmente, ele é interrompido ou iniciado apenas ao executar tarefas pouco frequentes, como atualizações de software ou alterações de certificado, ou no caso de determinados erros do sistema. Não é necessário interromper ou reiniciar o [!DNL Insight Server] serviço durante o funcionamento normal do sistema; no entanto, você pode configurar o serviço para reiniciar periodicamente (diariamente, semanalmente ou mensalmente) para, por exemplo, limpar as mensagens do evento.

**Para configurar o [!DNL Insight Server] para reiniciar automaticamente**

1. Navegue até o [!DNL Components] no diretório em que você instalou o [!DNL Insight Server].

   Exemplo: [!DNL C:\Adobe\Server\Components]

1. Use um editor de texto como o Bloco de notas para criar um novo arquivo chamado [!DNL ScheduledRestart.cfg].
1. Insira o seguinte texto no [!DNL ScheduledRestart.cfg] arquivo:

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
      <td colname="col1"> <i>Mês DD, AAAA HH:MM:TZone</i> </td> 
      <td colname="col2"> <p>A hora em que você deseja <span class="keyword"> Servidor Insight </span> para ser reiniciado pela primeira vez. </p> <p>Exemplo: 13 de agosto de 2013 22:30:00 EST </p> <p> <p>Observação: Você deve especificar um fuso horário. O fuso horário não é padrão para a hora do sistema, caso não seja especificado. Se quiser implementar o Horário de verão ou uma política de mudança de relógio semelhante, salve o <span class="filepath"> .dst </span> arquivo contendo as regras apropriadas no diretório Base\Conjunto de Dados\Fuso Horário no <span class="keyword"> Servidor Insight </span> máquina. Para obter uma lista de abreviações de fuso horário suportadas e informações sobre a implementação do Horário de verão, consulte <a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Códigos de fuso horário </a>. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>frequência</i> </td> 
      <td colname="col2"> <p>Um dos seguintes valores: 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">mês </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C">semana </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">dia </li> 
       </ul> </p> <p>Para indicar a frequência na qual deseja <span class="keyword"> Servidor Insight </span> a ser reiniciado após a hora inicial especificada em Hora de início. </p> <p>Por exemplo, se você desejar <span class="keyword"> Servidor Insight </span> para reiniciar uma vez por semana, você define esse valor como "semana". </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Salve as [!DNL ScheduledRestart.cfg] arquivo.

   Verifique se a variável [!DNL ScheduledRestart.cfg] está no [!DNL Components] no diretório em que você instalou o [!DNL Insight Server].
