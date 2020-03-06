---
description: O arquivo data workbenchTransform.cfg contém os parâmetros que definem as fontes de log, as transformações de dados e os exportadores.
solution: Analytics
title: O arquivo Transform.cfg
topic: Data workbench
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# O arquivo Transform.cfg{#the-transform-cfg-file}

O arquivo data workbenchTransform.cfg contém os parâmetros que definem as fontes de log, as transformações de dados e os exportadores.

As transformações que você define manipulam dados brutos coletados por Sensores ( [!DNL .vsl] arquivos) ou contidos em arquivos de texto, arquivos XML ou bancos de dados compatíveis com ODBC e os realizam em campos existentes, substituindo os dados atuais ou em campos recém-definidos.

Para configurar a funcionalidade de transformação, edite o arquivo da análise de big data na pasta Conjunto de dados para o perfil para o qual deseja exportar os dados do evento. [!DNL Transform.cfg] Normalmente, esse perfil é dedicado à funcionalidade de transformação (ou seja, você não executa outro processamento de dados além do que é definido no arquivo da análise de big data [!DNL Transform.cfg] ). É importante observar que quaisquer instruções de processamento especificadas nos [!DNL Log Processing Dataset Include] arquivos para qualquer perfil herdado são aplicadas além daquelas especificadas no arquivo da análise de big data [!DNL Transform.cfg] .

Para obter informações sobre arquivos de inclusão de conjuntos de dados, consulte [Arquivos](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)de inclusão de conjuntos de dados.

Se os dados que você deseja exportar forem processados por um cluster de servidores de análise de big data, cada um dos servidores de processamento (DPUs) no cluster processará os dados, mas somente a primeira DPU (servidor de processamento nº 0 no [!DNL profile.cfg] arquivo) gravará os dados de saída em seu sistema de arquivos local.

**Para editar o arquivo Transform.cfg da análise de big data**

1. Ao trabalhar no perfil para o qual você deseja exportar dados, abra o arquivo [!DNL Profile Manager] e clique em **[!UICONTROL Dataset]** para mostrar o conteúdo do diretório.
1. Clique com o botão direito do mouse na marca de seleção ao lado da análise de big data [!DNL Transform.cfg]e clique em **[!UICONTROL Make Local]**. Uma marca de seleção para este arquivo é exibida na [!DNL User] coluna.
1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. A janela da análise de big data [!DNL Transform.cfg] é exibida.
1. Edite os parâmetros no arquivo de configuração usando a tabela abaixo como guia:

<table id="table_91D9C4C1BE2E43158D9D06C6284EE3C7"> 
  <thead> 
    <tr> 
    <th colname="col1" class="entry"> Parâmetro </th> 
    <th colname="col2" class="entry"> Descrição </th> 
    </tr> 
  </thead>
  <tbody> 
    <tr> 
    <td colname="col1"> Hora de término </td> 
    <td colname="col2"> <p>Opcional. Filtre os dados para incluir entradas de log com carimbos de data e hora até, mas não incluindo, desta vez. A Adobe recomenda usar um dos seguintes formatos para o tempo: 
      <ul id="ul_C8C7F0F631594F7095CB83EF54E7CD0E"> 
       <li id="li_77AB6EEE8EEC4698AA886DE8BB0E2783"> 1 de janeiro de 2013HH:MM:SS EDT </li> 
       <li id="li_33806070F991476BB986906876CAF7F1"> Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Por exemplo, especificar 29 de julho de 2013 00:00:00 EDT como a Hora de <span class="wintitle"> Término </span> inclui dados até 28 de julho de 2013, às 11:59:59 EDT. </p> <p> Você deve especificar um fuso horário. O fuso horário não assumirá GMT como padrão se não for especificado. Para obter uma lista de abreviações de fuso horário suportadas pelo servidor da análise de big data, consulte <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de fuso horário </a>. </p> <p> O parâmetro Use Start/End Times para Sensor e fontes de arquivos de log está relacionado a esse parâmetro. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Exportadores </td> 
    <td colname="col2"> <p>Os subcampos de um exportador especificam como os dados de saída são processados e/ou formatados. É possível definir vários exportadores para um conjunto de fontes de log. Cada tipo de exportador cria uma produção independente. </p> <p> Existem três tipos de exportadores: 
      <ul id="ul_C3C39F6DF3DC4F4CA2161EDB69599642"> 
       <li id="li_635FB271D0544D52B1C31740442D2E08"> ExportTextFile </li> 
       <li id="li_D496194848B44823A58890E03FFDD18E"> ExportDelimitedTextFile </li> 
       <li id="li_AEE9AA87076141FC91330D3FCFAB2101"> ExportVSLFile </li> 
      </ul> </p> <p> Para obter mais informações sobre tipos de exportadores, consulte <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-def-exp.md#task-900c40d1914347f288587bf0ca394ff2"> Definindo Exportadores </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Limite de hash </td> 
    <td colname="col2"> Opcional. Um fator de amostragem para a subamostragem aleatória de linhas. Se definido como um número n, somente uma de cada n IDs de rastreamento é selecionada para exportação, reduzindo o número total de linhas exportadas por um fator de n. Para exportar todas as linhas, defina o Limite de hash como 1. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Condição de entrada do registro </td> 
    <td colname="col2"> Opcional. Define as regras pelas quais as entradas de log são consideradas para exportação. Para obter mais informações sobre a Condição de entrada do <span class="wintitle"> registro </span>, consulte Arquivo de configuração <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> de processamento de log </a>. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Fontes de registro </td> 
    <td colname="col2"> <p>As fontes de dados. <span class="wintitle"> As fontes de log </span> podem ser arquivos <span class="filepath"> </span> .vsl, arquivos de log ou arquivos XML ou dados de bancos de dados compatíveis com ODBC. Para obter informações sobre fontes <span class="wintitle"> de log, consulte Arquivo de configuração </span>de processamento de log <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> </a>. </p> <p> <span class="wintitle"> A Transform </span> espera que todos os dados de origem estejam em ordem cronológica nos arquivos de entrada lexicograficamente ordenados. Se este requisito não for cumprido, os cálculos A partir de estão incorretos e os dados de entrada adicionais podem ser processados depois de os arquivos de saída serem fechados. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Modo offline </td> 
    <td colname="col2"> <p>Opcional. Verdadeiro ou falso. Se verdadeiro, <span class="wintitle"> a Transform </span> assume que todos os arquivos de entrada estejam presentes quando iniciar o processamento dos dados. Quando todos os dados de entrada forem lidos, <span class="wintitle"> a Transformação </span> fechará todos os arquivos de saída sem esperar que dados adicionais sejam recebidos. O valor padrão é false. </p> <p> <p>Observação:  Se <span class="wintitle"> o Modo offline </span> estiver definido como true, <span class="wintitle"> o Transform </span> espera que todos os dados de origem estejam presentes antes do início do processamento. Uma mensagem de aviso é gerada no arquivo <span class="filepath"> VisualServer.log </span> se dados adicionais forem recebidos depois que os arquivos de saída forem fechados. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Reprocessar </td> 
    <td colname="col2"> <p>Opcional. Qualquer caractere ou combinação de caracteres pode ser inserida aqui. Alterar esse parâmetro e salvar o arquivo na máquina <span class="wintitle"> Transformar </span> inicia o reprocessamento de dados. </p> <p> Para obter informações sobre como reprocessar seus dados, consulte <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocessamento e Retransformação </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Estágios </td> 
    <td colname="col2"> <p>Opcional. Os nomes dos estágios de processamento que podem ser usados no Conjunto de Dados de Processamento de <span class="wintitle"> Log incluem </span> arquivos que são executados além do arquivo <span class="filepath"> Transform.cfg da análise de big data </span> . As etapas de processamento fornecem uma maneira de solicitar as transformações definidas nos arquivos Incluir conjuntos de dados de processamento de <span class="wintitle"> </span> log. Esse parâmetro é muito útil se você tiver definido uma ou mais transformações em vários arquivos Incluir conjuntos de dados de processamento de <span class="wintitle"> </span> log e desejar que transformações específicas sejam executadas em pontos específicos durante o processo de exportação. </p> <p> A ordem em que você lista os estágios aqui determina a ordem em que as transformações nos arquivos Incluir do Conjunto de Dados de Processamento de <span class="wintitle"> </span> Log são executadas durante a exportação de dados. <span class="wintitle"> O pré-processamento </span> e o <span class="wintitle"> pós-processamento </span> são fases integradas; <span class="wintitle"> O pré-processamento </span> é sempre o primeiro estágio, e o <span class="wintitle"> pós-processamento </span> é sempre o último estágio. Por padrão, há uma etapa nomeada chamada <span class="wintitle"> Padrão </span>. </p> <p> <b>Para adicionar uma nova etapa de processamento</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> Na janela <span class="filepath"> Transform.cfg da análise de big data, clique com o botão direito do mouse em </span> Estágios <span class="uicontrol"> e, em seguida, clique em </span>Adicionar novo <span class="uicontrol"> &gt; </span> Palco <span class="uicontrol"> </span>. </li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> Insira um nome para o novo estágio. </li> 
      </ul> <p> <b>Para excluir um estágio de processamento existente</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> Clique com o botão direito do mouse no número correspondente ao estágio que deseja excluir e clique em <span class="uicontrol"> Remover </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> <p> <p>Observação:  Quando você especifica um Palco em um arquivo Incluir de Conjunto de Dados de Processamento de <span class="wintitle"> </span> Log, o nome do estágio deve corresponder exatamente ao nome inserido aqui. Para obter mais informações sobre o conjunto de dados incluir arquivos, consulte <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Conjunto de dados Incluir arquivos </a>. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Hora inicial </td> 
    <td colname="col2"> <p>Opcional. Filtre os dados para incluir entradas de log com carimbos de data e hora nesse momento ou depois dele. A Adobe recomenda usar um dos seguintes formatos para o tempo: </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> 1 de janeiro de 2013 HH:MM:SS EDT </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> <p> Por exemplo, especificar 29 de julho de 2013 00:00:00 EDT como Hora de início inclui dados que começam a partir de 29 de julho de 2013, às 12:00:00 EDT. </p> <p> Você deve especificar um fuso horário. O fuso horário não assumirá GMT como padrão se não for especificado. Para obter uma lista de abreviações de fuso horário suportadas pelo servidor da análise de big data, consulte <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de fuso horário </a>. </p> <p> <p>Observação:  O parâmetro Use Start/End Times para Sensor e fontes de arquivos de log está relacionado a esse parâmetro. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Transformações </td> 
    <td colname="col2"> <p>Opcional. Define as transformações que devem ser aplicadas aos dados. Para obter informações sobre os tipos de transformação disponíveis, consulte <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformações de dados </a>. </p> <p> <p>Observação:  Os seguintes tipos de transformação não funcionam quando definidos no arquivo <span class="filepath"> Transform.cfg da análise de big data </span> : </p> </p> 
      <ul id="ul_B091DFBD1C33471BBC01AEC7E92FC8CC"> 
       <li id="li_660EBECFC407488199CCCC886326806D"> AppendURI </li> 
       <li id="li_56BCEBE4A2D044AE87F5B747C6501817"> CrossRows </li> 
       <li id="li_B23B4E81B37942DCA55FEC1A6239C5FA"> ODBCLookup </li> 
       <li id="li_EF0AFF13C40D4AB49EAB4EF1691F8FA4"> Sessionize </li> 
      </ul> </td> 
    </tr> 
  </tbody> 
  </table>

>[!NOTE]
>
>Se dados adicionais forem recebidos depois que os arquivos de saída forem fechados (consulte [!DNL Log Sources] e [!DNL Offline Mode] na tabela anterior), [!DNL Transform] criará novos arquivos de saída com os dados adicionais. Os nomes dos novos arquivos de saída são gerados a partir do nome do arquivo de saída original com a adição de um número de versão entre parênteses logo antes da extensão. Por exemplo, se o arquivo de saída original for [!DNL 20070701-ABC.vsl], as versões subsequentes desse arquivo serão nomeadas [!DNL 20070701-ABC(1).vsl], [!DNL 20070701-ABC(2).vsl]e assim por diante. Observe que o uso dos arquivos com versão como entrada no servidor da análise de big data pode resultar em erros de processamento.
>
>
>A Adobe recomenda evitar a criação de arquivos de saída com versão, certificando-se de que todos os dados de origem estejam em ordem cronológica dentro de arquivos de entrada ordenados lexicograficamente e, se [!DNL Offline Mode] estiver definido como true, que todos os dados de origem estejam presentes antes do início do processamento. Para obter mais informações, consulte as entradas [!DNL Log Sources] e [!DNL Offline Mode] na tabela anterior.

1. Adicione transformações clicando com o botão direito do mouse **[!UICONTROL Transformations]** e clicando em **[!UICONTROL Add new]** > **[!UICONTROL Transformation type]**. Preencha os campos de transformação.

   Consulte Transformações [de](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md) dados para obter descrições e exemplos das transformações que podem ser usadas com a funcionalidade de transformação.

1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
1. Para que as alterações feitas localmente entrem em vigor, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção da análise de big data [!DNL Transform.cfg] na [!DNL User] coluna, em seguida, clique em **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, onde nome do perfil é o nome do perfil para o qual você está exportando dados. O reprocessamento dos dados começa após a sincronização do perfil.

   >[!NOTE]
   >
   >Para obter informações sobre como reprocessar seus dados para exportação, consulte [Reprocessamento e Retransformação](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
