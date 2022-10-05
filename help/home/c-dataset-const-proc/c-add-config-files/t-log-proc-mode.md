---
description: O arquivo de configuração Log Processing Mode.cfg permite pausar o processamento de dados em um conjunto de dados, especificar fontes offline ou especificar a frequência na qual o servidor do Data Workbench salva seus arquivos de estado.
title: Log Processing Mode.cfg
uuid: 1f1e5d8b-80e7-4423-bb03-56e706a1b7b4
exl-id: e252b815-e691-490d-9ac9-88bb1fd2c64d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 3%

---

# Log Processing Mode.cfg{#log-processing-mode-cfg}

{{eol}}

O arquivo de configuração Log Processing Mode.cfg permite pausar o processamento de dados em um conjunto de dados, especificar fontes offline ou especificar a frequência na qual o servidor do Data Workbench salva seus arquivos de estado.

Fazer alterações no [!DNL Log Processing Mode.cfg] , incluindo a adição ou remoção de fontes, não causa o reprocessamento dos dados.

**Para editar o arquivo Log Processing Mode.cfg para um perfil de conjunto de dados**

1. Ao trabalhar no perfil do conjunto de dados, abra o [!DNL Profile Manager] e clique em **[!UICONTROL Dataset]** para mostrar seu conteúdo.

   >[!NOTE]
   >
   >Se a variável [!DNL Log Processing Mode.cfg] não estiver localizado no diretório do perfil desejado, é necessário copiar esse arquivo do diretório Base na máquina do servidor do Data Workbench para o diretório do perfil.

   Para obter informações sobre como abrir e trabalhar com a [!DNL Profile Manager,] consulte o *Guia do usuário do Data Workbench*.

1. Clique com o botão direito do mouse na marca de seleção ao lado do nome do arquivo de configuração e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece no [!DNL User] coluna.
1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. A janela de configuração é exibida.
1. Edite os parâmetros no arquivo de configuração usando a tabela a seguir como guia.

   >[!NOTE]
   >
   >Alguns dos parâmetros na [!DNL Log Processing Mode.cfg] arquivo tem nomes que incluem [!DNL Fast Input] ou [!DNL Fast Merge]. [!DNL Fast Input]refere-se à fase de processamento de log da construção do conjunto de dados e é responsável por aproximadamente metade do tempo total de processamento do conjunto de dados. [!DNL Fast Merge] refere-se à fase de transformação da construção do conjunto de dados somente quando precedida pelo processamento de log. [!DNL Fast Merge] não ocorre durante a retransformação que resulta da modificação de um [!DNL Transformation Dataset Configuration] arquivo. Like [!DNL Fast Input], [!DNL Fast Merge] O também é responsável por aproximadamente metade do tempo de processamento do conjunto de dados.

   <table id="table_1BF356E21C0E4119A277F40CEC5D7A21"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Parâmetro </th> 
      <th colname="col2" class="entry"> Descrição </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Bytes da nuvem </td> 
      <td colname="col2"> <p>Um parâmetro de ajuste que afeta a eficiência da transformação de dados. O valor padrão é 128000000. </p> <p> <p>Observação: Você não deve alterar esse valor sem consultar o Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Rácio de decisão de entrada rápida </td> 
      <td colname="col2"> <p>Um parâmetro de ajuste que especifica a proporção do total para bytes de log não lidos em que o sistema insere <span class="wintitle"> Entrada rápida</span> modo (e subsequentemente <span class="wintitle"> Mesclagem rápida</span>) em vez de processar dados em tempo real. </p> <p> O valor padrão é 200, o que significa que o sistema insere <span class="wintitle"> Entrada rápida</span> do modo em tempo real quando os dados de log não lidos estiverem em 1/200º do total de dados. Um maior índice de decisão faz com que o sistema entre <span class="wintitle"> Entrada rápida</span> modo mais fácil, enquanto uma proporção mais baixa torna menos provável que entre <span class="wintitle"> Entrada rápida</span> modo. </p> <p> <p>Observação: Definir o parâmetro como 0 impede que o sistema entre <span class="wintitle"> Entrada rápida</span> de qualquer modo, mesmo para o processamento inicial. Definir o parâmetro para 1.1 permite que o sistema insira <span class="wintitle"> Entrada rápida</span> durante a transformação inicial, mas não para a transformação subsequente. O Adobe não recomenda usar valores entre 0 e 1.1. Para obter mais informações sobre como definir esse parâmetro, entre em contato com o Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Entrada rápida de bytes FIFO </td> 
      <td colname="col2"> <p>Um parâmetro de ajuste que equilibra o uso de memória e o desempenho do sistema durante o processamento de dados. O valor padrão é 120000000. </p> <p> <p>Observação: Você não deve alterar esse valor sem consultar o Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Bytes de Buffer de Mesclagem Rápida </td> 
      <td colname="col2"> <p>Um parâmetro de ajuste que equilibra o uso de memória e o desempenho do sistema durante o processamento de dados. O valor padrão é 128000000. </p> <p> <p>Observação: Você não deve alterar esse valor sem consultar o Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fontes offline </td> 
      <td colname="col2"> <p>Máscara da fonte de log offline. </p> <p> <b> Especificação de uma fonte offline</b> 
      <ul id="ul_569B90E9A85246F88906FA5444F8A93E"> 
       <li id="li_3EF182CEF4A44106B5267175EC62B9AB"> Clique com o botão direito do mouse <span class="uicontrol"> Fontes offline</span>, depois clique em <span class="uicontrol"> Adicionar novo</span> &gt; <span class="uicontrol"> Origem</span>. </li> 
       <li id="li_E8FBA212F4784B1A830745A90BB3AF90"> No parâmetro para a nova fonte, insira a máscara da sequência de log. Para fontes de log do Sensor com nomes de arquivo do formato AAAMMDD-<i>SENSORID</i>.vsl, a máscara é <i>SENSORID.SENSORID</i> diferencia maiúsculas de minúsculas. Para fontes de log do arquivo de log, a máscara é a string extraída pela variável <span class="wintitle"> Padrão da máscara</span>. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Arquivos de registro</a>. </li> 
      </ul> </p> <p> Adicionar ou remover fontes de fontes offline não causa o reprocessamento do conjunto de dados. </p> <p> A partir de agora, as medidas são mantidas para o processamento das fontes online do perfil. Quando a fonte offline estiver novamente online, o processamento dos arquivos de log recebidos para essa fonte será retomado. </p> <p> Sempre que uma fonte voltar a ficar online, você deve removê-la de Fontes offline. Caso contrário, o servidor do Data Workbench tratará a fonte como uma fonte online e atualizará a A partir do tempo, desde que a fonte esteja enviando dados. Se a fonte ficar offline novamente, as medições de tempo de início são interrompidas. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Pausado </td> 
      <td colname="col2"> Verdadeiro ou falso. Se verdadeiro, os novos dados não serão processados no conjunto de dados. O valor padrão é false. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Atraso em tempo real </td> 
      <td colname="col2"> O tempo em segundos que o Servidor do Data Workbench aguarda entre intervalos de dados de processamento no conjunto de dados. Quando esse valor é definido como zero, o sistema tenta acompanhar os dados recebidos em tempo real. O valor padrão é zero (0), mas você pode aumentar esse valor para reduzir a carga da CPU. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Bytes FIFO em Tempo Real </td> 
      <td colname="col2"> <p>A quantidade de memória em bytes usada para armazenar dados que estão aguardando para serem processados no conjunto de dados. Talvez seja necessário alterar esse valor com base na quantidade de segundos especificada para o Atraso em tempo real. O valor padrão é 16000000. </p> <p> <p>Observação: Você não deve alterar esse valor sem consultar o Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Intervalo de Salvamento (s) </td> 
      <td colname="col2"> <p>Frequência na qual o servidor do Data Workbench salva seus arquivos de estado. O valor padrão é 3600. </p> <p> <p>Observação: Você não deve alterar esse valor sem consultar o Adobe. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   Ao editar o [!DNL Log Processing Mode.cfg] em uma janela do Data Workbench, é possível usar teclas de atalho para recursos básicos de edição, incluindo recortar (Ctrl+x ), copiar (Ctrl+c) , colar (Ctrl+v ), desfazer (Ctrl+z ), refazer (Ctrl+Shift+z ), selecionar seção (clicar+arrastar) e selecionar tudo (Ctrl+a ). Além disso, é possível usar os atalhos para copiar e colar o texto de um arquivo de configuração ( [!DNL .cfg]) para outro.

1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
1. No [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo no [!DNL User] e, em seguida, clique em **[!UICONTROL Save to]** > **[!UICONTROL datasetprofile name]**.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pelo Adobe, pois as alterações são substituídas ao instalar atualizações nesses perfis.
