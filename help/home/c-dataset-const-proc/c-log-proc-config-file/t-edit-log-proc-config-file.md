---
description: Etapas para editar o arquivo Log Processing.cfg para um perfil de conjunto de dados.
title: Editar o arquivo de configuração de processamento de log
uuid: 2ffae53a-ef2f-4933-821d-13f29dcdb68d
exl-id: 294063ef-6771-4310-8198-df57fab1e2b4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 2%

---

# Editar o arquivo de configuração de processamento de log{#editing-the-log-processing-configuration-file}

Etapas para editar o arquivo Log Processing.cfg para um perfil de conjunto de dados.

1. Ao trabalhar no perfil do conjunto de dados, abra o [!DNL Profile Manager] e clique em **[!UICONTROL Dataset]** para mostrar seu conteúdo.

   Para obter informações sobre como abrir e trabalhar com o [!DNL Profile Manager], consulte o *Guia do Usuário do Data Workbench*.

   >[!NOTE]
   >
   >Pode existir um subdiretório Log Processing no diretório Dataset. Esse subdiretório contém os arquivos [!DNL Log Processing Dataset Include] que foram criados para um ou mais perfis herdados. Consulte [Arquivos de inclusão do conjunto de dados](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL Log Processing.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece na coluna [!DNL User].
1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. A janela [!DNL Log Processing.cfg] é exibida.

   Você também pode abrir o arquivo [!DNL Log Processing.cfg] de um [!DNL Transformation Dependency Map]. Para obter informações sobre mapas de dependência de transformação, consulte [Ferramentas de Configuração do Conjunto de Dados](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

1. Edite os parâmetros no arquivo de configuração usando a tabela a seguir como guia.

   Ao editar o arquivo [!DNL Log Processing.cfg] em uma janela do Data Workbench, você pode usar teclas de atalho para recursos básicos de edição, incluindo recortar ( Ctrl+x ), copiar ( Ctrl+c) , colar ( Ctrl+v ), desfazer ( Ctrl+z ), refazer ( Ctrl+Shift+z ), selecionar seção (clicar+arrastar) e selecionar tudo ( Ctrl+a ). Também é possível usar os atalhos para copiar e colar o texto de um arquivo de configuração ( [!DNL .cfg]) para outro.

   >[!NOTE]
   >
   >Um arquivo [!DNL Log Processing Dataset Include] para um perfil herdado contém um subconjunto dos parâmetros descritos na tabela a seguir, bem como alguns parâmetros adicionais. Consulte [Arquivos de inclusão do conjunto de dados](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

   <table id="table_BC7D3635C94049A9B608463AC1DBFA69">
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Parâmetro </th> 
      <th colname="col2" class="entry"> Descrição </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Fontes de log </td> 
      <td colname="col2"> As fontes de dados. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Fontes de log </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hora de Término </td> 
      <td colname="col2"> <p>Opcional. Filtre os dados para incluir entradas de log com carimbos de data e hora, incluindo desta vez. O Adobe recomenda usar um dos seguintes formatos para o momento: </p> 
      <ul id="ul_42613B1D2F3A4A6C9563BC9B54BE895E"> 
      <li id="li_BC6E5FC5CA204D89936845BE05DFE6E6">1 de janeiro de 2013 HH:MM:SS EDT </li> 
      <li id="li_18FE1B0417AF4207B02497664F47D23F">1 de janeiro de 2013 HH:MM:SS GMT </li> 
      </ul> <p>Por exemplo, especificar 29 de julho de 2013 00:00:00 EDT como a Hora de término inclui dados até 28 de julho de 2013, às 11:59:59 EDT. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de dados </a>. </p> <p>Você deve especificar um fuso horário. O fuso horário não assume GMT como padrão se não estiver especificado. Para obter uma lista de abreviações de fuso horário compatíveis com o servidor do Data Workbench, consulte <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de fuso horário </a>. </p> <p> <p>Observação:  O parâmetro Usar Tempos de Início/Término para <span class="wintitle"> Sensor </span>, arquivo de log e fontes XML está relacionado a esse parâmetro. Consulte as seções de <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Fontes de log </a> que discutem esses tipos de origem. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Campos </td> 
      <td colname="col2"> Opcional. O Adobe recomenda definir <span class="wintitle"> Campos </span> em um ou mais arquivos <span class="wintitle"> de Inclusão </span> do conjunto de dados de processamento de log. Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Arquivos de inclusão do conjunto de dados de processamento de log </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Bytes de Chave Máximos do Grupo </td> 
      <td colname="col2"> <p>Quantidade máxima de dados de evento que o servidor pode processar para uma única ID de rastreamento. Os dados que excedem esse limite são filtrados do processo de construção do conjunto de dados. Esse valor deve ser definido como 2e6 quando a divisão de chave está ativa e 1e6 quando a divisão de chave não está ativa. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Divisão de chave </a>. </p> <p> <p>Observação:  Não altere esse valor sem consultar o Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Limite de hash </td> 
      <td colname="col2"> <p>Opcional. Fator de amostragem para a subamostragem aleatória de linhas. Se definida como um número n, somente uma de cada IDs de rastreamento n inserirá o conjunto de dados, reduzindo o número total de linhas no conjunto de dados por um fator n. </p> <p>Para criar um conjunto de dados que requer 100% de precisão (ou seja, para incluir todas as linhas), você define o Limite de Hash como 1. </p> <p>Valores: </p> <span class="filepath"> Limite de hash = 1  </span> (100% dos dados incluindo todas as linhas). <p> <span class="filepath"> Limite de hash = 2  </span> (1/2 de dados e inclui metade das linhas). </p> <p> <span class="filepath"> Limite de hash = 3  </span>(1/3 de dados e inclui uma de três linhas, mas é arredondado para 34% em Conclusão de consulta) </p> <p> <span class="filepath"> Limite de hash = 4  </span>(1/4 dos dados e inclui uma de quatro linhas). </p> <p> </p> <p> <p>Observação:  Usar um Limite de hash <span class="filepath"> = 8 </span> fornece 1/8 dos dados, que são 12,5%. No entanto, o valor <span class="uicontrol"> de Conclusão de Consulta </span> é arredondado para 13% para esse valor. Exemplos adicionais incluem um <span class="filepath"> Limite de hash = 6 </span> que resulta em 17% de resolução de consulta. Um <span class="filepath"> Limite de hash = 13 </span>resulta em 8% de resolução de consulta. </p> </p> <p>Se <span class="wintitle"> Limite de Hash </span> for especificado nos arquivos <span class="filepath"> Log Processing.cfg </span> e <span class="filepath"> Transformation.cfg </span>, ele não será aplicado em sequência; o valor máximo definido em qualquer arquivo de configuração se aplica. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de dados </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Condição de entrada de log </td> 
      <td colname="col2"> Opcional. Define as regras pelas quais as entradas de log são consideradas para inclusão no conjunto de dados. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condição de entrada de log </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Reprocessar </td> 
      <td colname="col2"> <p>Opcional. Qualquer caractere ou combinação de caracteres pode ser inserida aqui. Alterar esse parâmetro e salvar o arquivo na máquina do servidor do Data Workbench inicia o reprocessamento de dados. </p> <p>Consulte <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocessando e Retransformação </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dividir espaço do bucket da chave </td> 
      <td colname="col2"> <p>Parâmetro envolvido na divisão de chave. Seu valor deve ser 6e6 quando a divisão de chave estiver ativa. Consulte <a href="/help/home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#key-split"> Divisão de chave </a>. </p> <p> <p>Observação:  Não altere esse valor sem consultar o Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dividir Bytes de Chave </td> 
      <td colname="col2"> <p>Parâmetro envolvido na divisão de chave. Seu valor deve ser 1e6 quando a divisão de chave estiver ativa e 0 quando a divisão de chave não estiver ativa. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Divisão de chave </a>. </p> <p> <p>Observação:  Não altere esse valor sem consultar o Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Proporção de espaço da chave dividida </td> 
      <td colname="col2"> <p>Parâmetro envolvido na divisão de chave. Seu valor deve ser 10 quando a divisão de chave estiver ativa. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Divisão de chave </a>. </p> <p> <p>Observação:  Não altere esse valor sem consultar o Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Estágios </td> 
      <td colname="col2"> <p>Opcional. Os nomes dos estágios de processamento que podem ser usados nos arquivos <span class="wintitle"> do conjunto de dados de processamento de log Incluem </span>. As etapas de processamento fornecem uma maneira de ordenar as transformações definidas nos arquivos <span class="wintitle"> de Inclusão </span> do Conjunto de Dados de Processamento de Log. Esse parâmetro é muito útil se você tiver definido uma ou mais transformações em vários arquivos <span class="wintitle"> de Inclusão </span> do Conjunto de Dados de Processamento de Log e desejar que transformações específicas sejam executadas em pontos específicos durante o processamento do log. </p> <p>A ordem em que você lista os estágios aqui determina a ordem em que as transformações nos arquivos <span class="wintitle"> de Inclusão </span> do Conjunto de Dados de Processamento de Log são executadas durante o processamento de log. O pré-processamento e o pós-processamento são estágios integrados. O pré-processamento é sempre a primeira etapa e o pós-processamento é sempre a última. Por padrão, há um estágio nomeado chamado Padrão. </p> <p> <b>Para adicionar uma nova etapa de processamento</b> 
      <ul id="ul_3A49BEAD1C134344999FED379B8CE7A3"> 
         <li id="li_AFC9B2529EC64642AFF98E9D5BA88C71">Na janela <span class="filepath"> Log Processing.cfg </span>, clique com o botão direito do mouse em <span class="uicontrol"> Estágios </span> e clique em <span class="uicontrol"> Adicionar Novo </span> &gt; <span class="uicontrol"> Estágio </span>. </li> 
         <li id="li_5731B836658D4E1DB721C57C6275369A">Insira um nome para o novo estágio. </li> 
      </ul> </p> <p> <b>Para excluir uma etapa de processamento existente</b> 
      <ul id="ul_BBF4F710A5624C578F1F2A38FE18E9AD"> 
         <li id="li_CF6982C752DE41FFA97759C30CDE6AA0">Clique com o botão direito do mouse no número correspondente ao estágio que deseja excluir e clique em <span class="uicontrol"> Remover </span><i>&lt; <span class="uicontrol"> #stage_number </span></i>. </li> 
      </ul> </p> <p> <p>Observação:  Quando você especifica um <span class="wintitle"> Estágio </span> em arquivos <span class="wintitle"> de Inclusão </span> do Conjunto de Dados de Processamento de Log, o nome do palco deve corresponder exatamente ao nome inserido aqui. Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Arquivos de inclusão do conjunto de dados </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hora inicial </td> 
      <td colname="col2"> <p>Opcional. Filtre os dados para incluir entradas de log com carimbos de data e hora nesse momento ou depois dele. O Adobe recomenda usar um dos seguintes formatos para o momento: </p> <p> 
      <ul id="ul_0774889E22C24A6592809D289D1CBEC5"> 
         <li id="li_CE23541D8B584EA1AC432C5098564E46"> 1 de janeiro de 2013 HH:MM:SS EDT </li> 
         <li id="li_2EB0CF60CF12444BB744E52E9C919152"> 1 de janeiro de 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Por exemplo, especificar "29 de julho de 2013 00:00:00 EDT" como a Hora de início inclui dados a partir de 29 de julho de 2013, às 12:00:00 EDT. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de dados </a>. </p> <p> Você deve especificar um fuso horário. O fuso horário não assume GMT como padrão se não estiver especificado. Para obter uma lista de abreviações de fuso horário compatíveis com o servidor do Data Workbench, consulte <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de fuso horário </a>. </p> <p> <p>Observação:  O parâmetro Usar Tempos de Início/Término para <span class="wintitle"> Sensor </span>, arquivo de log e fontes XML está relacionado a esse parâmetro. Consulte as seções de <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Fontes de log </a> que discutem esses tipos de origem. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fuso horário </td> 
      <td colname="col2"> <p>Opcional. Fuso horário do servidor do Data Workbench usado para conversões de tempo (como a conversão representada pelo campo x-local-timestring) durante o processamento de log. </p> <p> <p>Observação:  Você deve especificar o Fuso Horário se quiser acessar o campo de tempo convertido durante a fase de processamento de log da construção do conjunto de dados. Caso contrário, o servidor do Data Workbench registrará um erro nos logs de eventos. </p> </p> <p>Consulte <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Fusos horários </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformações </td> 
      <td colname="col2"> Opcional. O Adobe recomenda definir transformações para processamento de log em um ou mais arquivos <span class="wintitle"> de Inclusão </span> do Conjunto de Dados de Processamento de Log. Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Arquivos de inclusão do conjunto de dados de processamento de log </a>. </td> 
   </tr> 
   </tbody> 
   </table>

1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
1. No [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção de [!DNL Log Processing.cfg]na coluna [!DNL User], em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]*** para que as alterações feitas localmente tenham efeito. O reprocessamento dos dados começa após a sincronização do perfil do conjunto de dados.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pelo Adobe, pois as alterações são substituídas ao instalar atualizações nesses perfis.

   Para obter mais informações sobre como reprocessar seus dados, consulte [Reprocessando e Retransformação](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
