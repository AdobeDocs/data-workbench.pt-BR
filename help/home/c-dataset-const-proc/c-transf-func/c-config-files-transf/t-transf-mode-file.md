---
description: O arquivo de configuração Transform Mode.cfg permite pausar o processamento de dados em um conjunto de dados, especificar fontes offline ou especificar a frequência na qual o servidor do Data Workbench que executa a funcionalidade de transformação salva seus arquivos de estado.
title: O arquivo Transform Mode.cfg
uuid: 6e875d02-341a-414c-90e5-aa7fa910ab81
exl-id: 4faca063-3ca9-4c7c-9f04-ba2dfb647a77
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 4%

---

# O arquivo Transform Mode.cfg{#the-transform-mode-cfg-file}

O arquivo de configuração Transform Mode.cfg permite pausar o processamento de dados em um conjunto de dados, especificar fontes offline ou especificar a frequência na qual o servidor do Data Workbench que executa a funcionalidade de transformação salva seus arquivos de estado.

Fazer alterações no arquivo [!DNL Transform Mode.cfg], incluindo a adição ou remoção de fontes, não causa o reprocessamento dos dados.

**Para editar o arquivo Transform Mode.cfg para um perfil de conjunto de dados**

1. Ao trabalhar no perfil cujos dados você deseja exportar, abra o [!DNL Profile Manager] e clique em **[!UICONTROL Dataset]** para mostrar o conteúdo do diretório.
1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL Transform Mode.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece na coluna [!DNL User].
1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. A janela [!DNL Transform Mode.cfg] é exibida.
1. Edite os parâmetros no arquivo de configuração usando a tabela a seguir como guia:

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
     <li id="li_617C04FE9F1C4E998394F224CFEA21F3"> Clique com o botão direito do mouse em <span class="uicontrol"> Fontes offline</span> e clique em <span class="uicontrol"> Adicionar novo</span> &gt; <span class="uicontrol"> Origem</span>. </li> 
    <li id="li_B263A294D1F14D62BBAA5DBF3B388C38"> No parâmetro para a nova fonte, insira a máscara da sequência de log. Para fontes de log do Sensor com nomes de arquivo do formato <span class="filepath"> AAAAMMDD-SENSORID.vsl</span>, a máscara é <i>SENSORID.SENSORID</i> diferencia maiúsculas de minúsculas. Para fontes de log do arquivo de log, a máscara é a string extraída pelo <span class="wintitle"> Padrão de máscara</span> (consulte <a href="../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Arquivos de Log</a>). </li> 
    </ul> <p> Adicionar ou remover fontes de <span class="wintitle"> Fontes offline</span> não causa o reprocessamento do conjunto de dados. </p> <p> A partir de agora, as medidas são mantidas para o processamento das fontes online do perfil. Quando a fonte offline estiver novamente online, o processamento dos arquivos de log recebidos para essa fonte será retomado. </p> <p> <p>Observação: Sempre que uma fonte voltar a ficar online, você deve removê-la de <span class="wintitle"> Fontes offline</span>. Caso contrário, o servidor do Data Workbench tratará a fonte como uma fonte on-line e atualizará a A partir do tempo, desde que a fonte esteja enviando dados. Se a fonte ficar offline novamente, as medições de tempo de início são interrompidas. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Pausado </td> 
    <td colname="col2"> Verdadeiro ou falso. Se verdadeiro, os novos dados não serão processados no conjunto de dados. O valor padrão é false. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Intervalo de Salvamento (s) </td> 
    <td colname="col2"> <p>Frequência na qual o servidor do Data Workbench no qual a funcionalidade de transformação está em execução salva seus arquivos de estado. O valor padrão é 3600. </p> <p> <p>Observação:  Você não deve alterar esse valor sem consultar o Adobe. </p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   Ao editar o arquivo [!DNL Transform Mode.cfg] em uma janela do Data Workbench, você pode usar teclas de atalho para recursos básicos de edição, incluindo recortar (Ctrl+x ), copiar (Ctrl+c) , colar (Ctrl+v ), desfazer (Ctrl+z ), refazer (Ctrl+Shift+z ), selecionar seção (clicar+arrastar) e selecionar tudo (Ctrl+a ). Além disso, é possível usar os atalhos para copiar e colar o texto de um arquivo de configuração ( [!DNL .cfg]) para outro.

1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
1. Para que as alterações feitas localmente entrem em vigor, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do Data Workbench [!DNL Transform Mode.cfg] na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, onde nome do perfil é o nome do perfil para o qual você está exportando dados. O reprocessamento dos dados começa após a sincronização do perfil.

   Para obter informações sobre como reprocessar seus dados para exportação, consulte [Reprocessando e Retransformação](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
