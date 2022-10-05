---
description: Etapas para registrar e executar o Servidor de relatórios.
title: Registrar o servidor de relatórios como um serviço do Windows
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# Registrar o servidor de relatórios como um serviço do Windows{#registering-report-server-as-a-windows-service}

{{eol}}

Etapas para registrar e executar o Servidor de relatórios.

Antes de executar esse procedimento, identifique a conta do Windows sob a qual [!DNL Report Server] será executado. Certifique-se de que esta conta tenha as permissões apropriadas para acessar o local onde os relatórios gerados estão armazenados (ou seja, não use a variável [!DNL Local System Account]).

Use o procedimento abaixo para iniciar [!DNL Report Server]. Ao iniciar [!DNL Report Server] pela primeira vez, ele se registra automaticamente como um serviço do Windows.

Ao iniciar [!DNL Report Server] pela primeira vez, ele se conecta automaticamente ao Adobe License Server para registrar seu certificado digital. Para concluir o processo de registro com êxito, a máquina deve estar conectada à Internet ao executar as etapas a seguir.

1. No Windows, navegue até o diretório onde você instalou o [!DNL Report Server].

   Exemplo: D:\Adobe\Report

1. Clique duas vezes **[!UICONTROL ReportServer.exe]**.
1. Para confirmar que [!DNL Report Server] estiver sendo executado corretamente, clique em **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Essa sequência de comandos pode variar dependendo da versão do Windows que você estiver usando.
1. Na lista de serviços, localize a entrada para [!DNL Report Server] e confirme se o status é Started e se o tipo de inicialização é Automatic.
1. Faça o seguinte para especificar a conta de usuário sob a qual [!DNL Report Server] executará:

   1. Clique duas vezes **[!UICONTROL Report Server]** para abrir o [!DNL Properties] janela.

   1. Selecione o **[!UICONTROL Log On]** guia .
   1. Selecione o **[!UICONTROL This account]** botão de opção.
   1. Digite ou procure o nome da conta. Esta conta deve ter permissão para acessar o local onde os relatórios gerados são armazenados.

      >[!NOTE]
      >
      >If [!DNL Report Server] O distribui relatórios como Microsoft Excel ( [!DNL .xls] ou [!DNL .xlsx]), verifique se a conta também tem permissão para executar o Microsoft Excel.

   1. Digite e confirme a senha da conta.
   1. Clique em **[!UICONTROL OK]**.

1. Clique com o botão direito do mouse no [!DNL Report Server] e selecione **[!UICONTROL Restart]** para reiniciar o serviço na conta especificada.
1. Para verificar se [!DNL Report Server] ocorreu qualquer erro durante a inicialização, clique em **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Essa sequência de comandos pode variar dependendo da versão do Windows que você estiver usando.

   1. No painel esquerdo do [!DNL Event Viewer] selecione o log Aplicativos .
   1. No painel direito, procure por eventos com Adobe no [!DNL Source] coluna.
   1. Se você encontrar um erro do Adobe, clique duas vezes no erro para exibir o [!DNL Event Properties] janela. Esta janela fornece informações detalhadas sobre o erro.

      >[!NOTE]
      >
      >Depois que a variável [!DNL Report Server] o serviço é iniciado, o arquivo [!DNL ReportServer.log] é criado no servidor de relatórios [!DNL Trace] diretório. Esse arquivo também é útil para solucionar problemas com [!DNL Report Server].

Você concluiu a instalação do [!DNL Report Server]. [!DNL Report Server] foi concebido para funcionar continuamente. Se você reiniciar a máquina, [!DNL Report Server] é reiniciado automaticamente. Se precisar começar e parar [!DNL Report Server] manualmente, você pode fazer isso usando o [!DNL Services] painel de controle no Windows.
