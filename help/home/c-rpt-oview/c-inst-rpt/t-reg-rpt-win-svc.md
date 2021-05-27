---
description: Etapas para registrar e executar o Servidor de relatórios.
title: Registrar o servidor de relatórios como um serviço do Windows
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# Registrar o servidor de relatórios como um serviço do Windows{#registering-report-server-as-a-windows-service}

Etapas para registrar e executar o Servidor de relatórios.

Antes de executar esse procedimento, identifique a conta do Windows na qual o serviço [!DNL Report Server] será executado. Certifique-se de que esta conta tenha as permissões apropriadas para acessar o local onde os relatórios gerados estão armazenados (ou seja, não use o [!DNL Local System Account]).

Use o procedimento abaixo para iniciar [!DNL Report Server]. Quando você inicia [!DNL Report Server] pela primeira vez, ele se registra automaticamente como um serviço do Windows.

Ao iniciar [!DNL Report Server] pela primeira vez, ele se conecta automaticamente ao Adobe License Server para registrar seu certificado digital. Para concluir o processo de registro com êxito, a máquina deve estar conectada à Internet ao executar as etapas a seguir.

1. No Windows, navegue até o diretório onde você instalou [!DNL Report Server].

   Exemplo: D:\Adobe\Report

1. Clique duas vezes em **[!UICONTROL ReportServer.exe]**.
1. Para confirmar que [!DNL Report Server] está sendo executado corretamente, clique em **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Essa sequência de comandos pode variar dependendo da versão do Windows que você estiver usando.
1. Na lista de serviços, localize a entrada para [!DNL Report Server] e confirme se seu status é Iniciado e se seu tipo de inicialização é Automático.
1. Faça o seguinte para especificar a conta de usuário na qual [!DNL Report Server] será executado:

   1. Clique duas vezes em **[!UICONTROL Report Server]** para abrir a janela [!DNL Properties].

   1. Selecione a guia **[!UICONTROL Log On]**.
   1. Selecione o botão de opção **[!UICONTROL This account]**.
   1. Digite ou procure o nome da conta. Esta conta deve ter permissão para acessar o local onde os relatórios gerados são armazenados.

      >[!NOTE]
      >
      >Se [!DNL Report Server] distribuir relatórios como arquivos do Microsoft Excel ( [!DNL .xls] ou [!DNL .xlsx]), verifique se a conta também tem permissão para executar o Microsoft Excel.

   1. Digite e confirme a senha da conta.
   1. Clique em **[!UICONTROL OK]**.

1. Clique com o botão direito do mouse no serviço [!DNL Report Server] e selecione **[!UICONTROL Restart]** para reiniciar o serviço na conta especificada.
1. Para verificar se [!DNL Report Server] teve erros durante a inicialização, clique em **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Essa sequência de comandos pode variar dependendo da versão do Windows que você estiver usando.

   1. No painel esquerdo da janela [!DNL Event Viewer], selecione o log Aplicativos.
   1. No painel direito, procure por eventos com Adobe na coluna [!DNL Source] .
   1. Se você encontrar um erro do Adobe, clique duas vezes no erro para exibir a janela [!DNL Event Properties]. Esta janela fornece informações detalhadas sobre o erro.

      >[!NOTE]
      >
      >Depois que o serviço [!DNL Report Server] é iniciado, o arquivo [!DNL ReportServer.log] é criado no diretório [!DNL Trace] do Servidor de Relatório. Esse arquivo também é útil para solucionar problemas com [!DNL Report Server].

Você concluiu a instalação de [!DNL Report Server]. [!DNL Report Server] foi concebido para funcionar continuamente. Se você reiniciar a máquina, [!DNL Report Server] será reiniciado automaticamente. Se você precisar iniciar e parar [!DNL Report Server] manualmente, poderá fazer isso usando o [!DNL Services] painel de controle no Windows.
