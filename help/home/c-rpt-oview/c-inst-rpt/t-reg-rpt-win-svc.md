---
description: Etapas para registrar e executar o Servidor de relatórios.
solution: Analytics
title: Registrando o Servidor de Relatório como um Serviço do Windows
topic: Data workbench
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Registrando o Servidor de Relatório como um Serviço do Windows{#registering-report-server-as-a-windows-service}

Etapas para registrar e executar o Servidor de relatórios.

Antes de executar esse procedimento, identifique a conta do Windows na qual o [!DNL Report Server] serviço será executado. Certifique-se de que essa conta tenha as permissões adequadas para acessar o local onde os relatórios gerados estão armazenados (ou seja, não use o [!DNL Local System Account]).

Use o procedimento abaixo para iniciar [!DNL Report Server]. Quando você inicia [!DNL Report Server] pela primeira vez, ele se registra automaticamente como um serviço do Windows.

Quando você inicia [!DNL Report Server] pela primeira vez, ele se conecta automaticamente ao Adobe License Server para registrar seu certificado digital. Para concluir o processo de registro com êxito, sua máquina deve estar conectada à Internet quando você executar as etapas a seguir.

1. No Windows, navegue até o diretório onde você instalou [!DNL Report Server].

   Exemplo: D:\Adobe\Report

1. Double-click **[!UICONTROL ReportServer.exe]**.
1. Para confirmar que [!DNL Report Server] está sendo executado corretamente, clique em **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Essa sequência de comando pode variar dependendo da versão do Windows que você estiver usando.
1. Na lista de serviços, localize a entrada para [!DNL Report Server] e confirme se seu status é Iniciado e seu tipo de inicialização é Automático.
1. Faça o seguinte para especificar a conta de usuário na qual [!DNL Report Server] será executada:

   1. Clique duas vezes **[!UICONTROL Report Server]** para abrir a [!DNL Properties] janela.

   1. Selecione a **[!UICONTROL Log On]** guia.
   1. Selecione o botão de **[!UICONTROL This account]** opção.
   1. Digite ou procure o nome da conta. Essa conta deve ter permissão para acessar o local onde os relatórios gerados são armazenados.

      >[!NOTE]
      >
      >Se [!DNL Report Server] distribuir relatórios como arquivos do Microsoft Excel ( [!DNL .xls] ou [!DNL .xlsx]), verifique se a conta também tem permissão para executar o Microsoft Excel.

   1. Digite e confirme a senha da conta.
   1. Clique em **[!UICONTROL OK]**.

1. Clique com o botão direito do mouse no [!DNL Report Server] serviço e selecione **[!UICONTROL Restart]** para reiniciar o serviço na conta especificada.
1. Para verificar se [!DNL Report Server] ocorreram erros durante a inicialização, clique em **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Essa sequência de comando pode variar dependendo da versão do Windows que você estiver usando.

   1. No painel esquerdo da [!DNL Event Viewer] janela, selecione o registro Aplicativos.
   1. No painel direito, procure eventos com a Adobe na [!DNL Source] coluna.
   1. Se você encontrar um erro da Adobe, clique duas vezes no erro para exibir a [!DNL Event Properties] janela. Esta janela fornece informações detalhadas sobre o erro.

      >[!NOTE]
      >
      >Depois que o [!DNL Report Server] serviço é iniciado, o arquivo [!DNL ReportServer.log] é criado no diretório do Report Server [!DNL Trace] . Esse arquivo também é útil para solucionar problemas com o [!DNL Report Server].

Você concluiu a instalação do [!DNL Report Server]. [!DNL Report Server] foi projetado para funcionar continuamente. Se você reiniciar o computador, o será [!DNL Report Server] reiniciado automaticamente. Se precisar iniciar e parar [!DNL Report Server] manualmente, você pode fazer isso usando o painel de [!DNL Services] controle no Windows.
