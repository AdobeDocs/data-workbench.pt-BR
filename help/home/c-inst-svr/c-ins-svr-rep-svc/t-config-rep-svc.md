---
description: Você deve configurar os Servidores de público alvo Insight para recuperar dados do Repetidor no qual os dados originais do evento são armazenados.
solution: Analytics
title: Configurar o serviço de replicação
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 1%

---


# Configurar o serviço de replicação{#configuring-the-replication-service}

Você deve configurar os Servidores de público alvo Insight para recuperar dados do Repetidor no qual os dados originais do evento são armazenados.

Para configurar a recuperação de dados de um público alvo [!DNL Repeater] para um  [!DNL Insight Server], edite o arquivo [!DNL Replicate.cfg] fornecido na [!DNL Components] pasta do público alvo [!DNL Insight Server(s)] conforme descrito no seguinte procedimento:

**Para configurar o[!DNL Replication Service]no computador público alvo**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a área de trabalho do Gerenciador de servidores.
1. Clique com o botão direito do mouse no ícone do público alvo [!DNL Insight Server] que deseja configurar e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique **[!UICONTROL Components]** para visualização do conteúdo. O [!DNL Replicate.cfg] arquivo está localizado dentro deste diretório.
1. Clique com o botão direito do mouse na marca de seleção na coluna de nome *do* servidor para [!DNL Replicate.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção é exibida na [!DNL Temp] coluna para [!DNL Replicate.cfg].
1. Clique com o botão direito do mouse na marca de seleção recém-criada na [!DNL Temp] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. A [!DNL Replicate.cfg] janela é aberta.
1. Na [!DNL Replicate.cfg] janela, clique em **[!UICONTROL Replicate.cfg]**, em seguida, **[!UICONTROL component]** para visualização de seu conteúdo.
1. Edite os parâmetros usando o exemplo e a tabela a seguir como guias:

   ![Informações da etapa](assets/cfg_ReplicateFile.png)

   <table id="table_F32D4BFA2D834BBB81DF8F84417CA969"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Para este parâmetro... </th> 
      <th colname="col2" class="entry"> Especificar... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Diretórios </td> 
      <td colname="col2"> <p>Os diretórios no <span class="wintitle"> Repetidor</span> que devem ser copiados (replicados) no público alvo <span class="keyword"> Insight Server</span>. O <span class="wintitle"> Replication Service</span> permite a replicação de vários diretórios a partir de um único <span class="wintitle"> Repeater</span>. </p> <p>Para adicionar um novo diretório, clique com o botão direito do mouse em <span class="uicontrol"> Diretórios</span> e clique em <span class="uicontrol"> Adicionar novo</span> &gt; <span class="uicontrol"> Diretório</span>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nivelar caminhos </td> 
      <td colname="col2"> <p>Verdadeiro ou falso. A ação definida pela configuração deste parâmetro depende da configuração do parâmetro Recursive neste arquivo: 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Se Recursivo for falso, Nivelar caminhos não terá efeito. Somente os arquivos no nível superior do diretório especificado pelo parâmetro URI remoto são replicados. </li>
      <li id="li_8FDB351102344E3995035557445354BB">Se Recursivo for verdadeiro e Nivelar caminhos for falso, a estrutura de diretório do diretório remoto (Repetidor<span class="wintitle"> ) será duplicada exatamente no caminho local no público alvo</span>Insight Server <span class="keyword"></span>. </li>
      <li id="li_3114B191C73744658799E112C61AB004">Se os Caminhos Recorrentes e Nivelados forem verdadeiros, nenhum subdiretório será criado no caminho local. Em vez disso, todos os arquivos da árvore de diretório remoto são colocados no nível superior do diretório local. </li>
      </ul></p> <p> <p>Observação: Se os Caminhos de Nivelamento e os Recursivos forem verdadeiros e os arquivos nos vários subdiretórios no computador remoto compartilharem os mesmos nomes, o Serviço <span class="wintitle"> de</span> Replicação pode interromper ou ocorrer outro comportamento indefinido. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Caminho local </td> 
      <td colname="col2">A localização do armazenamento para os arquivos recuperados do <span class="wintitle"> Repeater</span>. O caminho é relativo ao diretório de instalação do <span class="keyword"> Insight Server</span> . </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Recursivo </td> 
      <td colname="col2"> Verdadeiro ou falso. Se falso, somente os arquivos no nível superior do diretório especificado pelo parâmetro URI remoto serão replicados. Consulte Nivelar caminhos nesta tabela. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> URI remoto </td> 
      <td colname="col2">O URI, incluindo uma máscara de arquivo, para acessar o armazenamento de arquivos do <span class="wintitle"> Repeater</span> . O arquivo <span class="filepath"> Communications.cfg</span> no <span class="wintitle"> Repeater</span> deve ser configurado para que os dados do evento possam ser acessados usando este URI. See <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> Monitoring Event Data Space</a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Servidor </td> 
      <td colname="col2">Parâmetros para o Repetidor <span class="wintitle"> a partir do qual o público alvo</span> Insight Server <span class="keyword"></span> recupera arquivos de dados do evento. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nome </td> 
      <td colname="col2">Opcional. O nome para identificar o <span class="wintitle"> Repetidor</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nome comum do servidor SSL </td> 
      <td colname="col2">Obrigatório somente se Usar SSL estiver definido como verdadeiro. Nome comum do Repetidor <span class="wintitle"> no qual os dados do evento são armazenados</span> . Esse nome deve corresponder ao nome comum listado no certificado de comunicação do computador. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Endereço </td> 
      <td colname="col2">Nome do host ou endereço IP numérico do <span class="wintitle"> Repetidor</span> no qual os dados do evento são armazenados. O nome comum do servidor não é uma entrada válida. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Porta </td> 
      <td colname="col2"> Porta usada para transmissão de dados. A porta padrão é 80. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Certificado de cliente SSL </td> 
      <td colname="col2">Obrigatório somente se Usar SSL estiver definido como verdadeiro. Nome do certificado de licença usado para conexão com o <span class="wintitle"> Repetidor</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Usar SSL </td> 
      <td colname="col2"> <p>Determina se o SSL é usado para a transmissão de dados. As opções são true ou false, e o valor padrão é false. </p> <p> <p>Observação: O uso do SSL não é recomendado porque pode afetar negativamente o desempenho. Observe que o SSL não é necessário, a menos que a rede que conecta o <span class="wintitle"> Repetidor</span> às máquinas de público alvo esteja insegura. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hora de término, Hora do Start </td> 
      <td colname="col2"> <p>(Opcional) Limita o conjunto de arquivos de dados de evento copiados para o público alvo <span class="keyword"> Insight Server</span> àqueles que contêm dados no intervalo definido pela Hora do Start e Hora de término. Se a Hora do Start estiver definida, os arquivos de dados do evento nos quais todas as entradas do registro são anteriores à hora do start especificada não serão copiados. Se a Hora de término estiver definida, os arquivos de dados de evento nos quais todas as entradas de log do horário especificado ou posterior não serão copiados. Se apenas parte dos dados em um arquivo estiver no intervalo especificado, o arquivo inteiro será copiado para a máquina do público alvo. </p> <p>O Adobe recomenda usar um dos seguintes formatos para o horário: 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">1 de janeiro de 2013 HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">Jan 1 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>Observação: Você deve especificar um fuso horário. O fuso horário não assumirá a hora padrão do sistema se não for especificado. Se desejar implementar o Horário de verão ou uma política de mudança de relógio semelhante, salve o arquivo <span class="filepath"> .dst</span> contendo as regras apropriadas na máquina Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server</span> . Para obter uma lista de abreviações de fuso horário compatíveis e informações sobre a implementação do Horário de verão, consulte <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Códigos</a>de fuso horário. </p> </p> <p> <p>Observação:  Para usar essas configurações, os nomes dos arquivos de dados do evento devem começar com uma data ISO (AAAMMDD), e cada arquivo deve conter dados para o período de 24 horas, começando às 12h GMT dessa data. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Salve as alterações no servidor da seguinte maneira:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
   1. Na [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL Temp] coluna e selecione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

Este exemplo ilustra como os arquivos são copiados se os parâmetros Nivelar caminhos e Recursivo estiverem definidos como true.

Suponha que o URI remoto seja [!DNL /RemoteRoot/] e que o Caminho local seja [!DNL E:\LocalRoot\]. Na máquina remota ( [!DNL Repeater]), os arquivos são organizados da seguinte forma:

* [!DNL /RemoteRoot/fileA.txt]
* [!DNL /RemoteRoot/Dir1/fileB.txt]
* [!DNL /RemoteRoot/Dir2/Subdir3/fileC.txt]

Quando a replicação for concluída, o diretório local terá os seguintes arquivos:

* [!DNL E:\LocalRoot\fileA.txt]
* [!DNL E:\LocalRoot\fileB.txt]
* [!DNL E:\LocalRoot\fileC.txt]

No diretório local, nenhum subdiretório é criado e todos os arquivos da árvore de diretório remoto são colocados no nível superior do diretório local.

>[!NOTE]
>
>Se os arquivos nos vários subdiretórios no computador remoto compartilharem os mesmos nomes, os arquivos [!DNL Replication Service] poderão parar ou ocorrer outros comportamentos indefinidos.
