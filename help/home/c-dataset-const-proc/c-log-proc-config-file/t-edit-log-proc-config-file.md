---
description: Etapas para editar o arquivo Log Processing.cfg para um perfil de conjunto de dados.
solution: Analytics
title: Editando o arquivo de configuração de processamento de log
topic: Data workbench
uuid: 2ffae53a-ef2f-4933-821d-13f29dcdb68d
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Editando o arquivo de configuração de processamento de log{#editing-the-log-processing-configuration-file}

Etapas para editar o arquivo Log Processing.cfg para um perfil de conjunto de dados.

1. Ao trabalhar em seu perfil de conjunto de dados, abra o [!DNL Profile Manager] e clique **[!UICONTROL Dataset]** para mostrar seu conteúdo.

   Para obter informações sobre como abrir e trabalhar com o [!DNL Profile Manager], consulte o Guia *do usuário da Análise de* big data.

   >[!NOTE]
   >
   >Pode existir um subdiretório Log Processing no diretório Dataset. Esse subdiretório contém os [!DNL Log Processing Dataset Include] arquivos que foram criados para um ou mais perfis herdados. Consulte Incluir arquivos [do conjunto](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)de dados.

1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL Log Processing.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção para este arquivo é exibida na [!DNL User] coluna.
1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. A [!DNL Log Processing.cfg] janela é exibida.

   Você também pode abrir o [!DNL Log Processing.cfg] arquivo a partir de um [!DNL Transformation Dependency Map]. Para obter informações sobre mapas de dependência de transformação, consulte Ferramentas [de Configuração de](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)Conjunto de Dados.

1. Edite os parâmetros no arquivo de configuração usando a tabela a seguir como guia.

   Ao editar o [!DNL Log Processing.cfg] arquivo em uma janela de análise de big data, você pode usar teclas de atalho para recursos básicos de edição, incluindo recortar ( Ctrl+x ), copiar ( Ctrl+c), colar ( Ctrl+v ), desfazer ( Ctrl+z ), refazer ( Ctrl+Shift+z ), selecionar seção (clique+arrastar) e selecionar tudo ( Ctrl+a ). Você também pode usar os atalhos para copiar e colar o texto de um arquivo de configuração ( [!DNL .cfg]) para outro.

   >[!NOTE]
   >
   >Um [!DNL Log Processing Dataset Include] arquivo para um perfil herdado contém um subconjunto dos parâmetros descritos na tabela a seguir, bem como alguns parâmetros adicionais. Consulte Incluir arquivos [do conjunto](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)de dados.

   <table id="table_BC7D3635C94049A9B608463AC1DBFA69">
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Parâmetro </th> 
      <th colname="col2" class="entry"> Descrição </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Fontes de registro </td> 
      <td colname="col2"> As fontes de dados. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Origens de registro </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hora de término </td> 
      <td colname="col2"> <p>Opcional. Filtre os dados para incluir entradas de log com carimbos de data e hora até, mas não incluindo, desta vez. A Adobe recomenda usar um dos seguintes formatos para o tempo: </p> 
      <ul id="ul_42613B1D2F3A4A6C9563BC9B54BE895E"> 
      <li id="li_BC6E5FC5CA204D89936845BE05DFE6E6">1 de janeiro de 2013 HH:MM:SS EDT </li> 
      <li id="li_18FE1B0417AF4207B02497664F47D23F">Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> <p>Por exemplo, especificar 29 de julho de 2013 00:00:00 EDT como a Hora de término inclui dados até 28 de julho de 2013, às 11:59:59 EDT. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de dados </a>. </p> <p>Você deve especificar um fuso horário. O fuso horário não assumirá GMT como padrão se não for especificado. Para obter uma lista de abreviações de fuso horário suportadas pelo servidor da análise de big data, consulte <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de fuso horário </a>. </p> <p> <p>Observação:  O parâmetro Use Start/End Times para fontes <span class="wintitle"> Sensor, arquivo de log </span>e XML está relacionado a esse parâmetro. Consulte as seções de <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Fontes de registro </a> que discutem esses tipos de origem. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Campos </td> 
      <td colname="col2"> Opcional. A Adobe recomenda definir <span class="wintitle"> Campos </span> em um ou mais <span class="wintitle"> Arquivos de Inclusão de Conjunto de Dados de Processamento de Log </span> . Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Log Processing Dataset Incluir Arquivos </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Número Máximo de Bytes de Chave do Grupo </td> 
      <td colname="col2"> <p>Quantidade máxima de dados de eventos que o Servidor pode processar para uma única ID de rastreamento. Os dados que excedem esse limite são filtrados do processo de construção do conjunto de dados. Esse valor deve ser definido como 2e6 quando a divisão da chave estiver ativa e 1e6 quando a divisão da chave não estiver ativa. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Divisão de </a>chaves. </p> <p> <p>Observação:  Não altere esse valor sem consultar a Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Limite de hash </td> 
      <td colname="col2"> <p>Opcional. Um fator de amostragem para a subamostragem aleatória de linhas. Se definido como um número n, somente uma de cada n IDs de rastreamento informa o conjunto de dados, reduzindo o número total de linhas no conjunto de dados por um fator n. </p> <p>Para criar um conjunto de dados que exija 100% de precisão (ou seja, para incluir todas as linhas), você definiria o Limite de hash como 1. </p> <p>Valores: </p> <span class="filepath"> Limite de hash = 1 </span> (100% dos dados incluindo todas as linhas). <p> <span class="filepath"> Limite de hash = 2 </span> (1/2 de dados e inclui metade das linhas). </p> <p> <span class="filepath"> Limite de hash = 3 </span>(1/3 de dados e inclui uma de três linhas, mas arredonda para 34% na Conclusão da consulta) </p> <p> <span class="filepath"> Limite de hash = 4 </span>(1/4 dos dados e inclui uma em cada quatro linhas.) </p> <p> </p> <p> <p>Observação:  Usar um Limite de <span class="filepath"> Hash = 8 </span> fornece 1/8 dos dados, que são 12,5%. No entanto, o <span class="uicontrol"> valor de Conclusão de consulta </span> é arredondado para 13% para esse valor. Exemplos adicionais incluem um Limite de <span class="filepath"> Hash = 6 </span> que resulta em 17% de resolução de consulta. Um Limite de <span class="filepath"> Hash = 13 </span>resulta em 8% de resolução de consulta. </p> </p> <p>Se o Limite de <span class="wintitle"> Hash </span> for especificado nos arquivos <span class="filepath"> Log Processing.cfg </span> e <span class="filepath"> Transformation.cfg </span> , ele não será aplicado em sequência; o valor máximo definido em qualquer arquivo de configuração se aplica. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de dados </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Condição de entrada do registro </td> 
      <td colname="col2"> Opcional. Define as regras pelas quais as entradas de log são consideradas para inclusão no conjunto de dados. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condição de entrada do registro </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Reprocessar </td> 
      <td colname="col2"> <p>Opcional. Qualquer caractere ou combinação de caracteres pode ser inserida aqui. Alterar esse parâmetro e salvar o arquivo na máquina do servidor do análise de big data inicia o reprocessamento de dados. </p> <p>Consulte <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocessamento e retransformação </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dividir espaço do compartimento de chaves </td> 
      <td colname="col2"> <p>Parâmetro envolvido na divisão da chave. Seu valor deve ser 6e6 quando a divisão da chave estiver ativa. Consulte <a href="/help/home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#key-split"> Divisão de </a>chaves. </p> <p> <p>Observação:  Não altere esse valor sem consultar a Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dividir bytes de chave </td> 
      <td colname="col2"> <p>Parâmetro envolvido na divisão da chave. Seu valor deve ser 1e6 quando a divisão da chave estiver ativa e 0 quando a divisão da chave não estiver ativa. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Divisão de </a>chaves. </p> <p> <p>Observação:  Não altere esse valor sem consultar a Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Proporção de espaço de chave dividida </td> 
      <td colname="col2"> <p>Parâmetro envolvido na divisão da chave. Seu valor deve ser 10 quando a divisão da chave estiver ativa. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Divisão de </a>chaves. </p> <p> <p>Observação:  Não altere esse valor sem consultar a Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Estágios </td> 
      <td colname="col2"> <p>Opcional. Os nomes dos estágios de processamento que podem ser usados nos arquivos de Inclusão do Conjunto de Dados de Processamento de <span class="wintitle"> Log </span> . As etapas de processamento fornecem uma maneira de solicitar as transformações definidas nos arquivos Incluir conjuntos de dados de processamento de <span class="wintitle"> </span> log. Esse parâmetro é muito útil se você tiver definido uma ou mais transformações em vários arquivos de Inclusão do Conjunto de Dados de Processamento de <span class="wintitle"> </span> Log e desejar que transformações específicas sejam executadas em pontos específicos durante o processamento de log. </p> <p>A ordem em que você lista os estágios aqui determina a ordem em que as transformações nos arquivos Incluir do Conjunto de Dados de Processamento de <span class="wintitle"> </span> Log são executadas durante o processamento de log. O pré-processamento e o pós-processamento são estágios integrados. O pré-processamento é sempre o primeiro estágio, e o pós-processamento é sempre o último estágio. Por padrão, há uma etapa nomeada chamada Padrão. </p> <p> <b>Para adicionar uma nova etapa de processamento</b> 
      <ul id="ul_3A49BEAD1C134344999FED379B8CE7A3"> 
         <li id="li_AFC9B2529EC64642AFF98E9D5BA88C71">Na janela <span class="filepath"> Log Processing.cfg </span> , clique com o botão direito do mouse em <span class="uicontrol"> Estágios </span> e clique em <span class="uicontrol"> Adicionar novo </span> &gt; <span class="uicontrol"> Estágio </span>. </li> 
         <li id="li_5731B836658D4E1DB721C57C6275369A">Insira um nome para o novo estágio. </li> 
      </ul> </p> <p> <b>Para excluir um estágio de processamento existente</b> 
      <ul id="ul_BBF4F710A5624C578F1F2A38FE18E9AD"> 
         <li id="li_CF6982C752DE41FFA97759C30CDE6AA0">Clique com o botão direito do mouse no número correspondente ao estágio que deseja excluir e clique em <span class="uicontrol"> Remover </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> </p> <p> <p>Observação:  Quando você especifica um <span class="wintitle"> Palco </span> em um Conjunto de Dados de Processamento de <span class="wintitle"> Log Incluir </span> arquivos, o nome do estágio deve corresponder exatamente ao nome inserido aqui. Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Arquivo de inclusão de conjunto de dados </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hora inicial </td> 
      <td colname="col2"> <p>Opcional. Filtre os dados para incluir entradas de log com carimbos de data e hora nesse momento ou depois dele. A Adobe recomenda usar um dos seguintes formatos para o tempo: </p> <p> 
      <ul id="ul_0774889E22C24A6592809D289D1CBEC5"> 
         <li id="li_CE23541D8B584EA1AC432C5098564E46"> 1 de janeiro de 2013 HH:MM:SS EDT </li> 
         <li id="li_2EB0CF60CF12444BB744E52E9C919152"> Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Por exemplo, especificar "29 de julho de 2013 00:00:00 EDT" como a Hora de início inclui dados que começam a partir de 29 de julho de 2013, às 12:00:00 AM EDT. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de dados </a>. </p> <p> Você deve especificar um fuso horário. O fuso horário não assumirá GMT como padrão se não for especificado. Para obter uma lista de abreviações de fuso horário suportadas pelo servidor da análise de big data, consulte <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de fuso horário </a>. </p> <p> <p>Observação:  O parâmetro Use Start/End Times para fontes <span class="wintitle"> Sensor, arquivo de log </span>e XML está relacionado a esse parâmetro. Consulte as seções de <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Fontes de registro </a> que discutem esses tipos de origem. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fuso Horário </td> 
      <td colname="col2"> <p>Opcional. Fuso horário do servidor da análise de big data usado para conversões de tempo (como a conversão representada pelo campo x-local-timestring) durante o processamento de log. </p> <p> <p>Observação:  Você deve especificar o Fuso horário se desejar acessar o campo de tempo convertido durante a fase de processamento de log da construção do conjunto de dados. Caso contrário, o servidor da análise de big data registrará um erro nos logs de eventos. </p> </p> <p>Consulte <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Fusos horários </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformações </td> 
      <td colname="col2"> Opcional. A Adobe recomenda definir transformações para o processamento de log em um ou mais arquivos de Inclusão de conjuntos de dados <span class="wintitle"> </span> de processamento de log. Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Log Processing Dataset Incluir Arquivos </a>. </td> 
   </tr> 
   </tbody> 
   </table>

1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
1. Na [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção para [!DNL Log Processing.cfg]na [!DNL User] coluna, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>* para que as alterações feitas localmente tenham efeito. O reprocessamento dos dados começa após a sincronização do perfil do conjunto de dados.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pela Adobe, pois suas alterações são substituídas quando você instala atualizações nesses perfis.

   Para obter mais informações sobre como reprocessar seus dados, consulte [Reprocessamento e Retransformação](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
