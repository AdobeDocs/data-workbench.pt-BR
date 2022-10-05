---
description: O arquivo data workbenchTransform.cfg contém os parâmetros que definem as fontes de log, as transformações de dados e os exportadores.
title: O arquivo Transform.cfg
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
exl-id: e84f2536-cb22-4c47-a7a8-270b3c37ece6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1332'
ht-degree: 2%

---

# O arquivo Transform.cfg{#the-transform-cfg-file}

{{eol}}

O arquivo data workbenchTransform.cfg contém os parâmetros que definem as fontes de log, as transformações de dados e os exportadores.

As transformações que você define manipulam dados brutos coletados pelos Sensores ( [!DNL .vsl] arquivos) ou contidos em arquivos de texto, arquivos XML ou bancos de dados compatíveis com ODBC e os enviam para campos existentes, substituindo os dados atuais ou para campos recém-definidos.

Para configurar a funcionalidade de transformação, edite o Data Workbench [!DNL Transform.cfg] na pasta Conjunto de dados do perfil para o qual deseja exportar dados do evento. Normalmente, esse perfil é dedicado à funcionalidade de transformação (ou seja, você não executa outro processamento de dados diferente do que é definido no Data Workbench [!DNL Transform.cfg] arquivo ). É importante observar que as instruções de processamento especificadas no [!DNL Log Processing Dataset Include] os arquivos para qualquer perfil herdado são aplicados além daqueles especificados no Data Workbench [!DNL Transform.cfg] arquivo.

Para obter informações sobre arquivos de inclusão do conjunto de dados, consulte [Arquivos de inclusão do conjunto de dados](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

Se os dados que você deseja exportar forem processados por um cluster de servidores do Data Workbench, cada um dos servidores de processamento (DPUs) no cluster processará os dados, mas somente a primeira DPU (servidor de processamento #0 no [!DNL profile.cfg] ) gravará os dados de saída em seu sistema de arquivos local.

**Para editar o arquivo Transform.cfg do Data Workbench**

1. Ao trabalhar no perfil para o qual deseja exportar dados, abra o [!DNL Profile Manager] e clique em **[!UICONTROL Dataset]** para mostrar o conteúdo do diretório.
1. Clique com o botão direito do mouse na marca de seleção ao lado do Data Workbench [!DNL Transform.cfg], depois clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece no [!DNL User] coluna.
1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. O Data Workbench [!DNL Transform.cfg] será exibida.
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
    <td colname="col1"> Hora de Término </td> 
    <td colname="col2"> <p>Opcional. Filtre os dados para incluir entradas de log com carimbos de data e hora atualizados, mas não incluídos desta vez. O Adobe recomenda usar um dos seguintes formatos para o momento: 
      <ul id="ul_C8C7F0F631594F7095CB83EF54E7CD0E"> 
       <li id="li_77AB6EEE8EEC4698AA886DE8BB0E2783"> 1° De Janeiro De 2013HH:MM:EDT </li> 
       <li id="li_33806070F991476BB986906876CAF7F1"> 1 de janeiro de 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Por exemplo, especificando 29 de julho de 2013 00:00:00 EDT como <span class="wintitle"> Hora de Término </span> O inclui dados até 28 de julho de 2013, em 11:59:17:00 EDT </p> <p> Você deve especificar um fuso horário. O fuso horário não assume GMT como padrão se não estiver especificado. Para obter uma lista de abreviações de fuso horário compatíveis com o servidor do Data Workbench, consulte <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de fuso horário </a>. </p> <p> O parâmetro Usar Tempos de Início/Término para Sensor e fontes de arquivo de log está relacionado a esse parâmetro. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Exportadores </td> 
    <td colname="col2"> <p>Os subcampos de um exportador especificam como os dados de saída são processados e/ou formatados. Você pode definir vários exportadores para um conjunto de fontes de log. Cada tipo de exportador cria uma produção independente. </p> <p> Existem três tipos de exportadores: 
      <ul id="ul_C3C39F6DF3DC4F4CA2161EDB69599642"> 
       <li id="li_635FB271D0544D52B1C31740442D2E08"> ExportarArquivoDeTexto </li> 
       <li id="li_D496194848B44823A58890E03FFDD18E"> ExportDelimitedTextFile </li> 
       <li id="li_AEE9AA87076141FC91330D3FCFAB2101"> ExportVSLFile </li> 
      </ul> </p> <p> Para obter mais informações sobre tipos de exportadores, consulte <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-def-exp.md#task-900c40d1914347f288587bf0ca394ff2"> Definir exportadores </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Limite de hash </td> 
    <td colname="col2"> Opcional. Fator de amostragem para a subamostragem aleatória de linhas. Se definido como um número n, então apenas uma de cada n IDs de rastreamento é selecionada para exportação, reduzindo o número total de linhas exportadas por um fator de n. Para exportar todas as linhas, defina o Limite de hash como 1. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Condição de entrada de log </td> 
    <td colname="col2"> Opcional. Define as regras pelas quais as entradas de log são consideradas para exportação. Para obter mais informações sobre o <span class="wintitle"> Condição de entrada de log </span>, consulte <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Arquivo de configuração de processamento de log </a>. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Fontes de log </td> 
    <td colname="col2"> <p>As fontes de dados. <span class="wintitle"> Fontes de log </span> pode ser <span class="filepath"> .vsl </span> arquivos, arquivos de log ou arquivos XML ou dados de bancos de dados compatíveis com ODBC. Para obter informações sobre <span class="wintitle"> fontes de log </span>, consulte <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Arquivo de configuração de processamento de log </a>. </p> <p> <span class="wintitle"> Transformar </span> espera que todos os dados de origem estejam em ordem cronológica dentro de arquivos de entrada ordenados lexicograficamente. Se este requisito não for satisfeito, Como os cálculos estão incorretos, e os dados de entrada adicionais podem ser processados após o fechamento dos arquivos de saída. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Modo offline </td> 
    <td colname="col2"> <p>Opcional. Verdadeiro ou falso. Se verdadeiro, <span class="wintitle"> Transformar </span> O parte do princípio de que todos os arquivos de entrada estão presentes ao iniciar o processamento dos dados. Quando todos os dados de entrada forem lidos, <span class="wintitle"> Transformar </span> fecha todos os arquivos de saída sem esperar que dados adicionais sejam recebidos. O valor padrão é false. </p> <p> <p>Observação: If <span class="wintitle"> Modo offline </span> está definido como verdadeiro, <span class="wintitle"> Transformar </span> O espera que todos os dados de origem estejam presentes antes do início do processamento. Uma mensagem de aviso é gerada na variável <span class="filepath"> VisualServer.log </span> se dados adicionais forem recebidos após o fechamento dos arquivos de saída. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Reprocessar </td> 
    <td colname="col2"> <p>Opcional. Qualquer caractere ou combinação de caracteres pode ser inserida aqui. Alterar esse parâmetro e salvar o arquivo no <span class="wintitle"> Transformar </span> computador inicia o reprocessamento de dados. </p> <p> Para obter informações sobre como reprocessar seus dados, consulte <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocessamento e retransformação </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Estágios </td> 
    <td colname="col2"> <p>Opcional. Os nomes dos estágios de processamento que podem ser usados em <span class="wintitle"> Inclusão do conjunto de dados de processamento de log </span> arquivos que são executados além do Data Workbench <span class="filepath"> Transform.cfg </span> arquivo. As etapas de processamento fornecem uma maneira de ordenar as transformações definidas em <span class="wintitle"> Inclusão do conjunto de dados de processamento de log </span> arquivos. Esse parâmetro é muito útil se você tiver definido uma ou mais transformações em várias <span class="wintitle"> Inclusão do conjunto de dados de processamento de log </span> e desejar que transformações específicas sejam executadas em pontos específicos durante o processo de exportação. </p> <p> A ordem em que você relaciona os estágios aqui determina a ordem em que as transformações no <span class="wintitle"> Inclusão do conjunto de dados de processamento de log </span> os arquivos são executados durante a exportação de dados. <span class="wintitle"> Pré-processamento </span> e <span class="wintitle"> Pós-processamento </span> sejam fases integradas; <span class="wintitle"> Pré-processamento </span> é sempre o primeiro estágio, e <span class="wintitle"> Pós-processamento </span> é sempre o último estágio. Por padrão, há um estágio nomeado chamado <span class="wintitle"> Padrão </span>. </p> <p> <b>Para adicionar uma nova etapa de processamento</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> No Data Workbench <span class="filepath"> Transform.cfg </span> , clique com o botão direito do mouse <span class="uicontrol"> Estágios </span>, depois clique em <span class="uicontrol"> Adicionar novo </span> &gt; <span class="uicontrol"> Fase </span>. </li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> Insira um nome para o novo estágio. </li> 
      </ul> <p> <b>Para excluir uma etapa de processamento existente</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> Clique com o botão direito do mouse no número correspondente ao estágio que deseja excluir e clique em <span class="uicontrol"> Remover </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> <p> <p>Observação: Quando você especifica um Estágio em um <span class="wintitle"> Inclusão do conjunto de dados de processamento de log </span> o nome do palco deve corresponder exatamente ao nome inserido aqui. Para obter mais informações sobre arquivos de inclusão do conjunto de dados, consulte <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Arquivos de inclusão do conjunto de dados </a>. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Hora inicial </td> 
    <td colname="col2"> <p>Opcional. Filtre os dados para incluir entradas de log com carimbos de data e hora nesse momento ou depois dele. O Adobe recomenda usar um dos seguintes formatos para o momento: </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> 1 de janeiro de 2013 HH:MM:EDT </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> 1 de janeiro de 2013 HH:MM:SS GMT </li> 
      </ul> <p> Por exemplo, especificando 29 de julho de 2013 00:00:00 EDT, pois a Hora de início inclui dados a partir de 29 de julho de 2013, às 12:00:00 AM EDT. </p> <p> Você deve especificar um fuso horário. O fuso horário não assume GMT como padrão se não estiver especificado. Para obter uma lista de abreviações de fuso horário compatíveis com o servidor do Data Workbench, consulte <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de fuso horário </a>. </p> <p> <p>Observação: O parâmetro Usar Tempos de Início/Término para Sensor e fontes de arquivo de log está relacionado a esse parâmetro. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Transformações </td> 
    <td colname="col2"> <p>Opcional. Define as transformações a serem aplicadas aos dados. Para obter informações sobre os tipos de transformação disponíveis, consulte <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformações de dados </a>. </p> <p> <p>Observação: Os seguintes tipos de transformação não funcionam quando definidos no Data Workbench <span class="filepath"> Transform.cfg </span> arquivo: </p> </p> 
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
>Se dados adicionais forem recebidos após o fechamento dos arquivos de saída (consulte [!DNL Log Sources] e [!DNL Offline Mode] no quadro anterior), [!DNL Transform] O cria novos arquivos de saída com os dados adicionais. Os nomes dos novos arquivos de saída são gerados a partir do nome do arquivo de saída original com a adição de um número de versão entre parênteses logo antes da extensão. Por exemplo, se o arquivo de saída original for [!DNL 20070701-ABC.vsl], as versões subsequentes deste arquivo serão nomeadas [!DNL 20070701-ABC(1).vsl], [!DNL 20070701-ABC(2).vsl]e assim por diante. Observe que usar os arquivos com versão como entrada no servidor do Data Workbench pode resultar em erros de processamento.
>
>
>O Adobe recomenda evitar a criação de arquivos de saída com versão, certificando-se de que todos os dados de origem estejam em ordem cronológica dentro de arquivos de entrada ordenados lexicograficamente e, se [!DNL Offline Mode] for definido como true, todos os dados de origem estarão presentes antes do início do processamento. Para obter mais informações, consulte o [!DNL Log Sources] e [!DNL Offline Mode] entradas na tabela anterior.

1. Adicionar transformações clicando com o botão direito do mouse **[!UICONTROL Transformations]** e clicando em **[!UICONTROL Add new]** > **[!UICONTROL Transformation type]**. Preencha os campos de transformação.

   Consulte [Transformações de dados](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md) para obter descrições e exemplos das transformações que podem ser usadas com a funcionalidade de transformação.

1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela, em seguida, clique em **[!UICONTROL Save]**.
1. Para que as alterações feitas localmente entrem em vigor, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do Data Workbench [!DNL Transform.cfg] no [!DNL User] e, em seguida, clique em **[!UICONTROL Save to]** >  **[!UICONTROL profile name]**, onde nome do perfil é o nome do perfil para o qual você está exportando dados. O reprocessamento dos dados começa após a sincronização do perfil.

   >[!NOTE]
   >
   >Para obter informações sobre como reprocessar seus dados para exportação, consulte [Reprocessamento e retransformação](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
