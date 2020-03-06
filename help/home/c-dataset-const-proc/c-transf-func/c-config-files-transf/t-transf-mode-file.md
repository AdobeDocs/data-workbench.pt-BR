---
description: O arquivo de configuração Transform Mode.cfg permite pausar o processamento de dados em um conjunto de dados, especificar fontes offline ou especificar a frequência na qual o servidor de análise de big data executando a funcionalidade de transformação salva seus arquivos de estado.
solution: Analytics
title: O arquivo Transform Mode.cfg
topic: Data workbench
uuid: 6e875d02-341a-414c-90e5-aa7fa910ab81
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# O arquivo Transform Mode.cfg{#the-transform-mode-cfg-file}

O arquivo de configuração Transform Mode.cfg permite pausar o processamento de dados em um conjunto de dados, especificar fontes offline ou especificar a frequência na qual o servidor de análise de big data executando a funcionalidade de transformação salva seus arquivos de estado.

Fazer alterações no [!DNL Transform Mode.cfg] arquivo, incluindo adicionar ou remover fontes, não causa o reprocessamento dos dados.

**Para editar o arquivo Transform Mode.cfg para um perfil de conjunto de dados**

1. Ao trabalhar no perfil cujos dados você deseja exportar, abra o [!DNL Profile Manager] e clique **[!UICONTROL Dataset]** para mostrar o conteúdo do diretório.
1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL Transform Mode.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção para este arquivo é exibida na [!DNL User] coluna.
1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. A [!DNL Transform Mode.cfg] janela é exibida.
1. Edite os parâmetros no arquivo de configuração usando a seguinte tabela como guia:

   <table id="table_9FC00BD54FD8439DA17AEF61AC2ACD50"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Parâmetro </th> 
    <th colname="col2" class="entry"> Descrição </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> Fontes offline </td> 
    <td colname="col2"> <p>Máscara da fonte de log offline. </p> <p> Para especificar uma fonte offline: </p> 
    <ul id="ul_B93F945A697C4882ADE420438712B0B0"> 
     <li id="li_617C04FE9F1C4E998394F224CFEA21F3"> Clique com o botão direito do mouse em <span class="uicontrol"> Fontes</span> off-line e clique em <span class="uicontrol"> Adicionar novo</span> &gt; <span class="uicontrol"> Fonte</span>. </li> 
    <li id="li_B263A294D1F14D62BBAA5DBF3B388C38"> No parâmetro da nova fonte, insira a máscara da sequência de log. Para fontes de registro de Sensor com nomes de arquivo do formato <span class="filepath"> AAAMMDD-SENSORID.vsl</span>, a máscara é <i>SENSORID.SENSORID</i> diferenciando maiúsculas de minúsculas. Para fontes de log de arquivos de log, a máscara é a string extraída pelo Padrão <span class="wintitle"> de</span> máscara (consulte <a href="../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Arquivos</a>de log). </li> 
    </ul> <p> A adição ou remoção de fontes de <span class="wintitle"> Fontes</span> offline não causa o reprocessamento do conjunto de dados. </p> <p> A partir de agora, as medições são mantidas para o processamento das fontes online do perfil. Quando a fonte offline estiver novamente online, o processamento de arquivos de registro recebidos para essa fonte será retomado. </p> <p> <p>Observação: Sempre que uma fonte retornar on-line, você deve removê-la das Fontes <span class="wintitle"></span>off-line. Se você não fizer isso, o servidor da análise de big data trata a fonte como uma fonte on-line e atualiza o tempo de início, contanto que a fonte envie dados. Se a fonte for colocada off-line novamente, as medições de tempo de início serão interrompidas. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Pausado </td> 
    <td colname="col2"> Verdadeiro ou falso. Se verdadeiro, os novos dados não serão processados no conjunto de dados. O valor padrão é false. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Intervalo de salvamento (s) </td> 
    <td colname="col2"> <p>A frequência na qual o servidor de análise de big data no qual a funcionalidade de transformação está em execução salva seus arquivos de estado. O valor padrão é 3600. </p> <p> <p>Observação:  Você não deve alterar esse valor sem consultar a Adobe. </p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   Ao editar o [!DNL Transform Mode.cfg] arquivo em uma janela de análise de big data, você pode usar teclas de atalho para recursos básicos de edição, incluindo recortar (Ctrl+x ), copiar (Ctrl+c), colar (Ctrl+v ), desfazer (Ctrl+z ), refazer (Ctrl+Shift+z ), selecionar a seção (clique+arrastar) e selecionar tudo (Ctrl+a ). Além disso, você pode usar os atalhos para copiar e colar o texto de um arquivo de configuração ( [!DNL .cfg]) para outro.

1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
1. Para que as alterações feitas localmente entrem em vigor, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção da análise de big data [!DNL Transform Mode.cfg] na [!DNL User] coluna, em seguida, clique em **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, onde nome do perfil é o nome do perfil para o qual você está exportando dados. O reprocessamento dos dados começa após a sincronização do perfil.

   Para obter informações sobre como reprocessar seus dados para exportação, consulte [Reprocessamento e Retransformação](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
