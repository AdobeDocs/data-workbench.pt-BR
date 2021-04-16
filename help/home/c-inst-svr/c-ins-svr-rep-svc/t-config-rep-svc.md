---
description: Você deve configurar o(s) servidor(es) Insight de destino para recuperar dados do Repetidor no qual os dados do evento original são armazenados.
title: Configurar o serviço de replicação
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
exl-id: ae189089-fd5d-41cb-ad10-2b8c2032dafc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 2%

---

# Configurar o serviço de replicação{#configuring-the-replication-service}

Você deve configurar o(s) servidor(es) Insight de destino para recuperar dados do Repetidor no qual os dados do evento original são armazenados.

Para configurar a recuperação de dados de um [!DNL Repeater] para um destino [!DNL Insight Server], você deve editar o arquivo [!DNL Replicate.cfg] fornecido na pasta [!DNL Components] no destino [!DNL Insight Server(s)], conforme descrito no seguinte procedimento:

**Para configurar o  [!DNL Replication Service] no computador de destino**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile], clique na miniatura **[!UICONTROL Servers Manager]** para abrir o espaço de trabalho do Gerenciador de Servidores.
1. Clique com o botão direito do mouse no ícone do destino [!DNL Insight Server] que deseja configurar e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para visualizar seu conteúdo. O arquivo [!DNL Replicate.cfg] está localizado dentro desse diretório.
1. Clique com o botão direito do mouse na marca de seleção na coluna *server name* para [!DNL Replicate.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece na coluna [!DNL Temp] para [!DNL Replicate.cfg].
1. Clique com o botão direito do mouse na marca de seleção recém-criada na coluna [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. A janela [!DNL Replicate.cfg] é aberta.
1. Na janela [!DNL Replicate.cfg], clique em **[!UICONTROL Replicate.cfg]** e em **[!UICONTROL component]** para visualizar seu conteúdo.
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
      <td colname="col2"> <p>Os diretórios no <span class="wintitle"> Repetidor</span> que devem ser copiados (replicados) para o <span class="keyword"> Servidor Insight</span> de destino. O <span class="wintitle"> Serviço de Replicação</span> permite a replicação de vários diretórios a partir de um único <span class="wintitle"> Repetidor</span>. </p> <p>Para adicionar um novo diretório, clique com o botão direito do mouse em <span class="uicontrol"> Diretórios</span> e clique em <span class="uicontrol"> Adicionar novo</span> &gt; <span class="uicontrol"> Diretório</span>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Caminhos de Nivelamento </td> 
      <td colname="col2"> <p>Verdadeiro ou falso. A ação definida pela configuração desse parâmetro depende da configuração do parâmetro Recursivo neste arquivo: 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Se Recursivo for falso, Caminhos de Nivelamento não terá efeito. Somente os arquivos no nível superior do diretório especificado pelo parâmetro URI Remoto são replicados. </li>
      <li id="li_8FDB351102344E3995035557445354BB">Se Recursive for true e Flatten Paths for false, a estrutura de diretório do diretório remoto (<span class="wintitle"> Repeater</span>) será duplicada exatamente no caminho local no <span class="keyword"> Insight Server</span> de destino. </li>
      <li id="li_3114B191C73744658799E112C61AB004">Se os Caminhos Recorrentes e de Nivelamento forem verdadeiros, nenhum subdiretório será criado no caminho local. Em vez disso, todos os arquivos da árvore de diretório remoto são colocados no nível superior do diretório local. </li>
      </ul></p> <p> <p>Observação: Se Caminhos de Nivelamento e Recursivos forem verdadeiros e os arquivos nos vários subdiretórios na máquina remota compartilharem o mesmo nome, o <span class="wintitle"> Serviço de Replicação</span> poderá parar ou poderá ocorrer outro comportamento indefinido. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Caminho local </td> 
      <td colname="col2">O local de armazenamento dos arquivos recuperados de <span class="wintitle"> Repetidor</span>. O caminho é relativo ao diretório de instalação do <span class="keyword"> Insight Server</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Recursivo </td> 
      <td colname="col2"> Verdadeiro ou falso. Se for falso, somente os arquivos no nível superior do diretório especificado pelo parâmetro URI remoto serão replicados. Consulte Nivelar caminhos nesta tabela. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> URI remoto </td> 
      <td colname="col2">O URI, incluindo uma máscara de arquivo, para acessar o armazenamento de arquivos <span class="wintitle"> do Repetidor</span>. O arquivo <span class="filepath"> Communications.cfg</span> no <span class="wintitle"> Repetidor</span> deve ser configurado para que os dados do evento possam ser acessados usando esse URI. Consulte <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> Monitorar o espaço de dados do evento</a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Servidor </td> 
      <td colname="col2">Parâmetros para o <span class="wintitle"> Repetidor</span> a partir do qual o destino <span class="keyword"> Servidor Insight</span> recupera arquivos de dados do evento. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nome </td> 
      <td colname="col2">Opcional. O nome para identificar o <span class="wintitle"> Repetidor</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nome comum do servidor SSL </td> 
      <td colname="col2">Obrigatório somente se Usar SSL estiver definido como verdadeiro. Nome comum do <span class="wintitle"> Repetidor</span> no qual os dados do evento são armazenados. Esse nome deve corresponder ao nome comum listado no certificado de comunicação da máquina. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Endereço </td> 
      <td colname="col2">Nome do host ou endereço IP numérico do repetidor <span class="wintitle"></span> no qual os dados do evento são armazenados. O nome comum do servidor não é uma entrada válida. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Porta </td> 
      <td colname="col2"> Porta utilizada para transmissão de dados. A porta padrão é 80. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Certificado de cliente SSL </td> 
      <td colname="col2">Obrigatório somente se Usar SSL estiver definido como verdadeiro. Nome do certificado de licença usado para se conectar ao repetidor <span class="wintitle"></span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Usar SSL </td> 
      <td colname="col2"> <p>Determina se o SSL é usado para a transmissão de dados. As opções são true ou false e o valor padrão é false. </p> <p> <p>Observação: Não é recomendado usar SSL porque pode afetar negativamente o desempenho. Observe que o SSL não é necessário a menos que a rede que conecta o <span class="wintitle"> Repetidor</span> às máquinas de destino não seja segura. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hora de Término, Hora de Início </td> 
      <td colname="col2"> <p>(Opcional) Limita o conjunto de arquivos de dados de evento copiados para o <span class="keyword"> Servidor Insight</span> de destino àqueles que contêm dados no intervalo definido pela Hora de início e Hora de término. Se a Hora de início for definida, os arquivos de dados do evento nos quais todas as entradas de log são anteriores à hora de início especificada não serão copiados. Se a Hora de término for definida, os arquivos de dados do evento nos quais todas as entradas de log da hora especificada ou posterior não serão copiados. Se apenas parte dos dados em um arquivo estiver no intervalo especificado, o arquivo inteiro será copiado para o computador de destino. </p> <p>O Adobe recomenda usar um dos seguintes formatos para o momento: 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">1 de janeiro de 2013 HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">1 de janeiro de 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>Observação: Você deve especificar um fuso horário. O fuso horário não é padrão para a hora do sistema, caso não seja especificado. Se desejar implementar o Horário de verão ou uma política de mudança de relógio semelhante, você deve salvar o arquivo <span class="filepath"> .dst</span> contendo as regras apropriadas na máquina Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server</span>. Para obter uma lista de abreviações de fuso horário compatíveis e informações sobre a implementação do Horário de verão, consulte <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Códigos de fuso horário</a>. </p> </p> <p> <p>Observação:  Para usar essas configurações, os nomes dos arquivos de dados do evento devem começar com uma data ISO (AAAAMMDD) e cada arquivo deve conter dados para o período de 24 horas, começando às 12h GMT dessa data. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Salve as alterações no servidor fazendo o seguinte:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
   1. No [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na coluna [!DNL Temp] e selecione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

Este exemplo ilustra como os arquivos são copiados se os parâmetros Caminhos de Nivelamento e Recursivos estiverem definidos como verdadeiros.

Suponha que o URI remoto seja [!DNL /RemoteRoot/] e que o Caminho local seja [!DNL E:\LocalRoot\]. Na máquina remota ( [!DNL Repeater]), os arquivos são organizados da seguinte maneira:

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
>Se os arquivos nos vários subdiretórios na máquina remota compartilharem o mesmo nome, [!DNL Replication Service] pode parar ou ocorrer outro comportamento indefinido.
