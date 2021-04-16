---
description: Informações sobre o monitoramento do espaço de dados do evento e a alteração do diretório de log para dados do Sensor.
title: Monitorar o espaço de dados do evento
uuid: e514e8fb-e735-4003-ab21-17470c73af37
exl-id: 1016d00f-e0a0-47f1-a600-528c4811fcf6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---

# Monitorar o espaço de dados do evento{#monitoring-event-data-space}

Informações sobre o monitoramento do espaço de dados do evento e a alteração do diretório de log para dados do Sensor.

**Frequência recomendada:** a cada 5-10 minutos

[!DNL Insight Server] armazena um arquivo de log por  [!DNL Sensor] dia na unidade de processamento de dados ou na unidade de servidor de arquivos, dependendo da configuração. O tamanho dos arquivos de log e a quantidade de espaço de armazenamento de dados necessário para eles dependem de muitas variáveis, incluindo, por exemplo, o número de sites registrados e o número de solicitações que seus servidores da Web recebem por segundo.

Uma instalação típica de [!DNL Insight Server] (ou um cluster [!DNL Insight Server]) é capaz de armazenar vários terabytes de dados, supondo que a implementação use o hardware recomendado pelo Adobe para a(s) máquina(s) [!DNL Insight Server].

Normalmente, todos os dados de log permanecem presentes na máquina [!DNL Insight Server]. Se for necessário disponibilizar mais espaço de armazenamento de dados na máquina, você poderá mover todos os arquivos de log do dia mais atuais para outra máquina ou meio de armazenamento de dados (unidade zip, fita e assim por diante). Mover os dados não exige que você pare [!DNL Insight Server] e não afeta a funcionalidade disponível em nenhum [!DNL Insights] que possa estar conectado a [!DNL Insight Server] e trabalhar com dados contínuos. Desde que você não processe ou reprocesse um conjunto de dados de análise, mantenha o acesso a todos os dados anteriores e os novos dados continuem disponíveis em [!DNL Insight]. Se você processar ou reprocessar um conjunto de dados de análise, não poderá acessá-los até que o processamento seja concluído.

Por padrão, os dados de evento produzidos por [!DNL Sensor] e transmitidos para [!DNL Insight Server] são armazenados na pasta [!DNL Logs] dentro do diretório de instalação [!DNL Insight Server]. O arquivo de configuração Comunicações, [!DNL Communications.cfg], especifica o local dos arquivos de log de dados do evento que são lidos por [!DNL Insight Server].

**Para alterar o diretório de log para  [!DNL Sensor] dados**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile], clique na miniatura **[!UICONTROL Servers Manager]** para abrir o espaço de trabalho do Gerenciador de Servidores.
1. Clique com o botão direito do mouse no ícone do [!DNL Insight Server] que deseja configurar e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para visualizar seu conteúdo. O arquivo [!DNL Communications.cfg] está localizado dentro desse diretório.
1. Clique com o botão direito do mouse na marca de seleção na coluna *server name* para [!DNL Communications.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece na coluna [!DNL Temp] para [!DNL Communications.cfg].
1. Clique com o botão direito do mouse na marca de seleção recém-criada na coluna [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Na janela [!DNL Communications.cfg], clique em **[!UICONTROL component]** para visualizar seu conteúdo.
1. Na janela [!DNL Communications.cfg], clique em **[!UICONTROL Servers]** para visualizar seu conteúdo. Vários tipos de servidores podem aparecer: Servidores de arquivos, servidores de registro, servidores de inicialização, servidores de status, servidores de envio ou servidores replicados.
1. Encontre o LoggingServer, que é onde [!DNL Sensor] grava seus arquivos de log a serem processados por [!DNL Insight Server], e clique em seu número para exibir o menu.

   ![Informações da etapa](assets/cfg_communications_examplevalues_logging.png)

   O diretório de log padrão é a pasta [!DNL Logs] no diretório de instalação [!DNL Insight Server].

1. Edite o parâmetro Diretório de log para refletir o local desejado dos arquivos de log.

   >[!NOTE]
   >
   >Não modifique outros parâmetros para o LoggingServer.

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   Vários FileServers podem ser listados no nó Servidores, portanto, talvez seja necessário visualizar o conteúdo de muitos deles (clicando em seus números na lista [!DNL Servers]) para localizar o servidor com um Caminho Local de Logs\ a ser modificado.

1. Edite o Caminho local para refletir o local desejado dos arquivos [!DNL .vsl].

   >[!NOTE]
   >
   >Não modifique nenhum outro parâmetro para o FileServer.

   Embora o local dos arquivos de log tenha sido alterado no arquivo [!DNL Communications.cfg], você pode mapear esses arquivos para o diretório Logs do [!DNL Server Files Manager] especificando /Logs/ como o URI do FileServer.

1. Salve as alterações no servidor fazendo o seguinte:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. No [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na coluna [!DNL Temp] e selecione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.
