---
description: Informações sobre monitoramento do espaço de dados do evento e alteração do diretório de log para dados do sensor.
solution: Insight
title: Monitorando o espaço de dados do evento
uuid: e514e8fb-e735-4003-ab21-17470c73af37
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# Monitorando o espaço de dados do evento{#monitoring-event-data-space}

Informações sobre monitoramento do espaço de dados do evento e alteração do diretório de log para dados do sensor.

**Frequência recomendada:** A cada 5 a 10 minutos

[!DNL Insight Server] armazena um arquivo de log por [!DNL Sensor] dia na Unidade de processamento de dados ou na Unidade de servidor de arquivos, dependendo da configuração. O tamanho dos arquivos de log e a quantidade de espaço de armazenamento de dados necessários para eles dependem de muitas variáveis, incluindo, por exemplo, o número de sites que estão sendo registrados e o número de solicitações que seus servidores da Web recebem por segundo.

Uma instalação típica de [!DNL Insight Server] (ou um [!DNL Insight Server] cluster) é capaz de armazenar vários terabytes de dados, desde que a implementação use o hardware recomendado pela Adobe para as [!DNL Insight Server] máquinas.

Normalmente, todos os dados de log permanecem presentes no [!DNL Insight Server] computador. Se for necessário disponibilizar mais espaço de armazenamento de dados na máquina, você poderá mover todos os arquivos de registro do dia mais recentes para outra máquina ou mídia de armazenamento de dados (unidade zip, fita e assim por diante). Mover os dados não exige que você pare [!DNL Insight Server]e não afeta a funcionalidade disponível em qualquer [!DNL Insights] que possa estar conectado [!DNL Insight Server] e trabalhando com dados contínuos. Desde que você não processe ou reprocesse um conjunto de dados de análise, manterá o acesso a todos os dados anteriores e os novos dados continuarão disponíveis em [!DNL Insight]. Se você processar ou reprocessar um conjunto de dados de análise, não poderá acessar os dados até que o processamento seja concluído.

Por padrão, os dados de evento produzidos por [!DNL Sensor] e transmitidos para [!DNL Insight Server] são armazenados na [!DNL Logs] pasta dentro do diretório de [!DNL Insight Server] instalação. O arquivo de configuração Comunicações, [!DNL Communications.cfg], especifica o local dos arquivos de log de dados de eventos que são lidos por [!DNL Insight Server].

**Alteração do diretório de log para[!DNL Sensor]dados**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a área de trabalho do Gerenciador de servidores.
1. Clique com o botão direito do mouse no ícone do [!DNL Insight Server] que deseja configurar e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para exibir o conteúdo. O [!DNL Communications.cfg] arquivo está localizado dentro deste diretório.
1. Clique com o botão direito do mouse na marca de seleção na coluna de nome *do* servidor para [!DNL Communications.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção é exibida na [!DNL Temp] coluna para [!DNL Communications.cfg].
1. Clique com o botão direito do mouse na marca de seleção recém-criada na [!DNL Temp] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Na [!DNL Communications.cfg] janela, clique **[!UICONTROL component]** para exibir seu conteúdo.
1. Na [!DNL Communications.cfg] janela, clique **[!UICONTROL Servers]** para exibir seu conteúdo. Vários tipos de servidores podem ser exibidos: Servidores de arquivos, servidores de registro, servidores de inicialização, servidores de status, servidores de envio ou servidores de replicação.
1. Localize o LoggingServer, que é o local onde [!DNL Sensor] grava seus arquivos de log a serem processados [!DNL Insight Server]e clique em seu número para exibir o menu.

   ![Informações da etapa](assets/cfg_communications_examplevalues_logging.png)

   O diretório de log padrão é a [!DNL Logs] pasta no diretório de [!DNL Insight Server] instalação.

1. Edite o parâmetro Diretório de log para refletir o local desejado dos arquivos de log.

   >[!NOTE]
   >
   >Não modifique nenhum outro parâmetro para o LoggingServer.

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   Vários FileServers podem estar listados no nó Servidores, portanto, talvez seja necessário exibir o conteúdo de muitos deles (clicando em seus números na [!DNL Servers] lista) para localizar o servidor com um Caminho local de registros\ a ser modificado.

1. Edite o Caminho local para refletir o local desejado dos [!DNL .vsl] arquivos.

   >[!NOTE]
   >
   >Não modifique nenhum outro parâmetro para o FileServer.

   Embora o local dos arquivos de log tenha sido alterado no [!DNL Communications.cfg] arquivo, é possível mapear esses arquivos para o diretório Logs do [!DNL Server Files Manager] especificando /Logs/ como o URI do FileServer.

1. Salve as alterações no servidor da seguinte maneira:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Na [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL Temp] coluna e selecione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

