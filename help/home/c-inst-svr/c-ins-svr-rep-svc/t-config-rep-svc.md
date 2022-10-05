---
description: Você deve configurar o(s) servidor(es) Insight de destino para recuperar dados do Repetidor no qual os dados do evento original são armazenados.
title: Configurar o serviço de replicação
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
exl-id: ae189089-fd5d-41cb-ad10-2b8c2032dafc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 1%

---

# Configurar o serviço de replicação{#configuring-the-replication-service}

{{eol}}

Você deve configurar o(s) servidor(es) Insight de destino para recuperar dados do Repetidor no qual os dados do evento original são armazenados.

Para configurar a recuperação de dados de um [!DNL Repeater] para um target [!DNL Insight Server], você deve editar o [!DNL Replicate.cfg] do [!DNL Components] pasta no target [!DNL Insight Server(s)] conforme descrito no seguinte procedimento:

**Para configurar o [!DNL Replication Service] na máquina de destino**

1. Em [!DNL Insight], no [!DNL Admin] > [!DNL Dataset and Profile] clique no botão **[!UICONTROL Servers Manager]** miniatura para abrir o espaço de trabalho do Gerenciador de Servidores.
1. Clique com o botão direito do mouse no ícone do público-alvo [!DNL Insight Server] você deseja configurar e clicar em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para visualizar seu conteúdo. O [!DNL Replicate.cfg] O arquivo está localizado dentro desse diretório.
1. Clique com o botão direito do mouse na marca de seleção no *nome do servidor* coluna para [!DNL Replicate.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece no [!DNL Temp] coluna para [!DNL Replicate.cfg].
1. Clique com o botão direito do mouse na marca de seleção recém-criada na [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. O [!DNL Replicate.cfg] será aberta.
1. No [!DNL Replicate.cfg] , clique em **[!UICONTROL Replicate.cfg]**, em seguida **[!UICONTROL component]** para visualizar seu conteúdo.
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
      <td colname="col2"> <p>Os diretórios na <span class="wintitle"> Repetidor</span> que devem ser copiadas (replicadas) para o target <span class="keyword"> Servidor Insight</span>. O <span class="wintitle"> Serviço de replicação</span> permite a replicação de vários diretórios a partir de um único <span class="wintitle"> Repetidor</span>. </p> <p>Para adicionar um novo diretório, clique com o botão direito do mouse <span class="uicontrol"> Diretórios</span> e clique em <span class="uicontrol"> Adicionar novo</span> &gt; <span class="uicontrol"> Diretório</span>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Caminhos de Nivelamento </td> 
      <td colname="col2"> <p>Verdadeiro ou falso. A ação definida pela configuração desse parâmetro depende da configuração do parâmetro Recursivo neste arquivo: 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Se Recursivo for falso, Caminhos de Nivelamento não terá efeito. Somente os arquivos no nível superior do diretório especificado pelo parâmetro URI Remoto são replicados. </li>
      <li id="li_8FDB351102344E3995035557445354BB">Se Recursivo for verdadeiro e Caminhos de Nivelamento for falso, a estrutura de diretório do remoto (<span class="wintitle"> Repetidor</span>) é duplicado exatamente no caminho local no destino <span class="keyword"> Servidor Insight</span>. </li>
      <li id="li_3114B191C73744658799E112C61AB004">Se os Caminhos Recorrentes e de Nivelamento forem verdadeiros, nenhum subdiretório será criado no caminho local. Em vez disso, todos os arquivos da árvore de diretório remoto são colocados no nível superior do diretório local. </li>
      </ul></p> <p> <p>Observação: Se os Caminhos de Nivelamento e o Recursivo forem verdadeiros e os arquivos nos vários subdiretórios no computador remoto compartilharem o mesmo nome, a variável <span class="wintitle"> Serviço de replicação</span> pode parar ou pode ocorrer outro comportamento indefinido. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Caminho local </td> 
      <td colname="col2">O local de armazenamento dos arquivos recuperados de <span class="wintitle"> Repetidor</span>. O caminho é relativo ao <span class="keyword"> Servidor Insight</span> diretório de instalação. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Recursivo </td> 
      <td colname="col2"> Verdadeiro ou falso. Se for falso, somente os arquivos no nível superior do diretório especificado pelo parâmetro URI remoto serão replicados. Consulte Nivelar caminhos nesta tabela. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> URI remoto </td> 
      <td colname="col2">O URI, incluindo uma máscara de arquivo, para acessar o <span class="wintitle"> do repetidor</span> armazenamento de arquivos. O <span class="filepath"> Communications.cfg</span> no <span class="wintitle"> Repetidor</span> deve ser configurado para que os dados do evento possam ser acessados usando esse URI. Consulte <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> Monitorar o espaço de dados do evento</a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Servidor </td> 
      <td colname="col2">Parâmetros para o <span class="wintitle"> Repetidor</span> do qual o target <span class="keyword"> Servidor Insight</span> recupera arquivos de dados do evento. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nome </td> 
      <td colname="col2">Opcional. O nome para identificar a variável <span class="wintitle"> Repetidor</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nome comum do servidor SSL </td> 
      <td colname="col2">Obrigatório somente se Usar SSL estiver definido como verdadeiro. Nome comum da <span class="wintitle"> Repetidor</span> em que os dados do evento são armazenados. Esse nome deve corresponder ao nome comum listado no certificado de comunicação da máquina. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Endereço </td> 
      <td colname="col2">Nome do host ou endereço IP numérico da <span class="wintitle"> Repetidor</span> em que os dados do evento são armazenados. O nome comum do servidor não é uma entrada válida. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Port </td> 
      <td colname="col2"> Porta utilizada para transmissão de dados. A porta padrão é 80. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Certificado de cliente SSL </td> 
      <td colname="col2">Obrigatório somente se Usar SSL estiver definido como verdadeiro. Nome do certificado de licença utilizado para ligar à <span class="wintitle"> Repetidor</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Usar SSL </td> 
      <td colname="col2"> <p>Determina se o SSL é usado para a transmissão de dados. As opções são true ou false e o valor padrão é false. </p> <p> <p>Observação: Não é recomendado usar SSL porque pode afetar negativamente o desempenho. Observe que o SSL não é necessário a menos que a rede que conecta o <span class="wintitle"> Repetidor</span> para as máquinas-alvo é inseguro. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hora de Término, Hora de Início </td> 
      <td colname="col2"> <p>(Opcional) Limita o conjunto de arquivos de dados de evento copiados para o público-alvo <span class="keyword"> Servidor Insight</span> para aqueles que contêm dados no intervalo definido pela Hora inicial e Hora final. Se a Hora de início for definida, os arquivos de dados do evento nos quais todas as entradas de log são anteriores à hora de início especificada não serão copiados. Se a Hora de término for definida, os arquivos de dados do evento nos quais todas as entradas de log da hora especificada ou posterior não serão copiados. Se apenas parte dos dados em um arquivo estiver no intervalo especificado, o arquivo inteiro será copiado para o computador de destino. </p> <p>O Adobe recomenda usar um dos seguintes formatos para o momento: 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">1 de janeiro de 2013 HH:MM:EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">1 de janeiro de 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>Observação: Você deve especificar um fuso horário. O fuso horário não é padrão para a hora do sistema, caso não seja especificado. Se quiser implementar o Horário de verão ou uma política de mudança de relógio semelhante, salve o <span class="filepath"> .dst</span> arquivo contendo as regras apropriadas no diretório Base\Conjunto de Dados\Fuso Horário no <span class="keyword"> Servidor Insight</span> máquina. Para obter uma lista de abreviações de fuso horário suportadas e informações sobre a implementação do Horário de verão, consulte <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Códigos de fuso horário</a>. </p> </p> <p> <p>Observação: Para usar essas configurações, os nomes dos arquivos de dados do evento devem começar com uma data ISO (AAAAMMDD) e cada arquivo deve conter dados para o período de 24 horas, começando às 12h GMT dessa data. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Salve as alterações no servidor fazendo o seguinte:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
   1. No [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo no [!DNL Temp] e selecione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

Este exemplo ilustra como os arquivos são copiados se os parâmetros Caminhos de Nivelamento e Recursivos estiverem definidos como verdadeiros.

Suponha que o URI remoto esteja [!DNL /RemoteRoot/] e Caminho local é [!DNL E:\LocalRoot\]. No controle remoto ( [!DNL Repeater]), os arquivos são organizados da seguinte maneira:

* [!DNL /RemoteRoot/fileA.txt]
* [!DNL /RemoteRoot/Dir1/fileB.txt]
* [!DNL /RemoteRoot/Dir2/Subdir3/fileC.txt]

Quando a replicação é concluída, o diretório local tem os seguintes arquivos:

* [!DNL E:\LocalRoot\fileA.txt]
* [!DNL E:\LocalRoot\fileB.txt]
* [!DNL E:\LocalRoot\fileC.txt]

No diretório local, nenhum subdiretório é criado e todos os arquivos da árvore de diretório remoto são colocados no nível superior do diretório local.

>[!NOTE]
>
>Se os arquivos nos vários subdiretórios na máquina remota compartilharem o mesmo nome, a variável [!DNL Replication Service] pode parar ou pode ocorrer outro comportamento indefinido.
