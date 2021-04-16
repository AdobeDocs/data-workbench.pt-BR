---
description: As fontes de log são arquivos que contêm os dados a serem usados para criar um conjunto de dados.
title: Fontes de log
uuid: ea21c3d7-9188-4ba8-bacd-052d678bd799
exl-id: 36e0799b-197d-4c59-84ae-7a4350584ab1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '3664'
ht-degree: 1%

---

# Fontes de log{#log-sources}

As fontes de log são arquivos que contêm os dados a serem usados para criar um conjunto de dados.

Os dados disponíveis nas fontes de log são chamados de dados de evento porque cada registro de dados representa um registro de transação ou uma única instância de um evento. O servidor do Data Workbench pode processar fontes de log derivadas de dados coletados por [!DNL Sensors] ou extraídos de outras fontes de dados.

* **Dados coletados por [!DNL Sensors]: ** Os dados coletados por [!DNL Sensors] de HTTP e servidores de aplicativos são transmitidos para servidores do Data Workbench, que convertem os dados em arquivos de log altamente compactados ( [!DNL .vsl]). Consulte [Arquivos do sensor](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009).

* **Dados extraídos pelo servidor Insight:** o servidor do Data Workbench lê os dados do evento contidos em arquivos simples, arquivos XML ou bancos de dados compatíveis com ODBC e usa seus decodificadores para extrair os elementos desejados dos dados. Esses dados de evento não precisam ser residentes na memória, mas os registros que contêm os dados devem incluir uma ID de rastreamento. Consulte [Arquivos de Log](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e), [Fontes de Log XML](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887) e [Fontes de Dados ODBC](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

**Para adicionar uma fonte de log**

1. Abra [!DNL Log Processing.cfg] no Data Workbench.
1. Clique com o botão direito do mouse em **[!UICONTROL Log Sources]** e depois clique em **[!UICONTROL Add New]**.

1. Selecione uma das opções a seguir:

   * **[!UICONTROL Sensor]**
   * **[!UICONTROL Log File]**
   * **[!UICONTROL XML Log Source]**
   * **[!UICONTROL ODBC Data Source]**

1. Os parâmetros específicos usados para definir um conjunto de dados variam com base no tipo de fonte de log a ser usada no processo de configuração do conjunto de dados. Especifique os parâmetros conforme indicado na seção correspondente à fonte de log apropriada:

   * [Arquivos do sensor](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009)
   * [Arquivos de registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)
   * [Fontes de log XML](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)
   * [Fontes de dados ODBC](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)

1. Depois de definir sua fonte de log (e fazer alterações em outros parâmetros) no arquivo [!DNL Log Processing.cfg], salve o arquivo localmente e salve-o no perfil do conjunto de dados no servidor do Data Workbench.

   >[!NOTE]
   >
   >Um servidor do Data Workbench [!DNL File Server Unit] pode receber e armazenar arquivos [!DNL Sensor], arquivos de log e arquivos XML e enviá-los para o [!DNL Data Processing Units] do servidor do Data Workbench que constrói o conjunto de dados. Consulte [Configurando uma unidade de servidor de arquivos do servidor Insight](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d).

   Você pode abrir a configuração de qualquer fonte de log a partir de um [!DNL Transformation Dependency Map]. Para obter informações sobre [!DNL Transformation Dependency Map], consulte [Ferramentas de Configuração do Conjunto de Dados](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

<!--
c_sensor_files.xml
-->

## Requisitos {#section-d5901a4872774ad5bd01a18db114f1f2}

Os dados do evento coletados por [!DNL Sensors] de HTTP e servidores de aplicativos são transmitidos para servidores do Data Workbench, que convertem os dados em arquivos de log altamente compactados ( [!DNL .vsl]). O formato de arquivo [!DNL .vsl] é gerenciado pelo servidor do Data Workbench e cada arquivo tem um nome do formato:

AAAAMMDD-*SENSORID*.VSL

onde AAAMMDD é a data do arquivo, e *SENSORID* é o nome (atribuído pela organização) que indica qual [!DNL Sensor] coletou e transmitiu os dados ao servidor do Data Workbench.

## Parâmetros {#section-5c3f1e341c284486aeba3452057da7f3}

Para arquivos [!DNL Sensor], os seguintes parâmetros estão disponíveis:

<table id="table_F583B475600041AFA3B9399AE0592146"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Caminhos de registro </td> 
   <td colname="col2"> <p>Os diretórios onde os arquivos <span class="filepath"> .vsl</span> são armazenados. O local padrão é o diretório Logs . Um caminho relativo refere-se ao diretório de instalação do servidor do Data Workbench. </p> <p>Você pode usar caracteres curingas para especificar quais arquivos <span class="filepath"> .vsl</span> processar: 
     <ul id="ul_AE144ED0FAB94FE8B32599A058659DE1"> 
      <li id="li_1E4E4CFD72C34B5EB71A3C59877950A9"> * corresponde a qualquer número de caracteres </li> 
      <li id="li_4664400FC12E44B39B28438B85D20ED8"> ? corresponde a um único caractere </li> 
     </ul> </p> <p> Por exemplo, o caminho de log <span class="filepath"> Logs\*.vsl</span> corresponde a qualquer arquivo no diretório Logs que termina em <span class="filepath"> .vsl</span>. O caminho de log <span class="filepath"> Logs\*-SENSOR?.vsl</span> corresponde arquivos no diretório Logs com qualquer data (AAAAMMDD) e um único caractere após SENSOR, como em SENSOR1. </p> <p> Se quiser pesquisar todos os subdiretórios do caminho especificado, defina o parâmetro Recursive como true. </p> <p> <p>Observação: Se os arquivos devem ser lidos a partir de uma <span class="wintitle"> Unidade de Servidor de Arquivos</span> do servidor do Data Workbench, você deve inserir os URIs apropriados no parâmetro Caminhos de Log. Por exemplo, o <span class="filepath"> URI /Logs/*-*.vsl</span> corresponde a qualquer arquivo <span class="filepath"> .vsl</span> no diretório Logs . Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurando uma unidade de servidor de arquivos do servidor Insight</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor de registro </td> 
   <td colname="col2">Informações (Endereço, Nome, Porta, etc.) necessárias para se conectar a um servidor de arquivos. Se houver uma entrada no parâmetro Servidor de Log, os <span class="wintitle"> Caminhos de Log</span> serão interpretados como URIs. Caso contrário, serão interpretados como caminhos locais. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurando uma unidade de servidor de arquivos do servidor Insight</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID da Fonte de Log </td> 
   <td colname="col2"> <p>O valor desse parâmetro pode ser qualquer string. Se um valor for especificado, esse parâmetro permitirá diferenciar entradas de log de diferentes fontes de log para identificação de origem ou processamento direcionado. O campo x-log-source-id é preenchido com um valor que identifica a origem do log para cada entrada de log. Por exemplo, se você deseja identificar entradas de log de um <span class="wintitle"> Sensor</span> chamado VSensor01, você pode digitar <span class="filepath"> de VSensor01</span>, e essa sequência seria passada para o campo x-log-source-id para cada entrada de log dessa origem. </p> <p> Para obter informações sobre o campo x-log-source-id, consulte <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Campos de registro de dados do evento</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recursivo </td> 
   <td colname="col2"> Verdadeiro ou falso. Se definido como true, todos os subdiretórios de cada caminho especificados em <span class="wintitle"> Caminhos de Log</span> serão pesquisados para procurar arquivos correspondentes ao nome de arquivo especificado ou padrão curinga. O valor padrão é false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar Tempos de Início/Término </td> 
   <td colname="col2"> <p>Verdadeiro ou falso. Se definido como true e a Hora de início ou Hora de término for especificada, todos os arquivos para essa fonte de log deverão ter nomes de arquivo começando com datas no formato ISO (AAAMMDD). Pressupõe-se que cada arquivo contenha dados para um dia GMT (por exemplo, o intervalo de tempo que começa em 0000 GMT em um dia e termina em 0000 GMT no dia seguinte). Se os arquivos de fontes de log contiverem dados que não correspondem a um dia GMT, esse parâmetro deverá ser definido como false para evitar resultados incorretos. </p> <p> <p>Observação: Por padrão, os arquivos <span class="filepath"> .vsl </span>contendo dados coletados pelo <span class="wintitle"> Sensor</span> atendem automaticamente aos requisitos de nomenclatura e intervalo de tempo descritos acima. Se você definir esse parâmetro como true, o servidor do Data Workbench sempre processará dados de arquivos cujos nomes incluem datas ISO que estão entre a Hora de início e a Hora de término especificadas. Se você definir esse parâmetro como falso, o servidor do Data Workbench lê todos os arquivos <span class="filepath"> .vsl</span> durante o processamento do log para determinar quais arquivos contêm dados no intervalo de Hora de início e Hora de término. </p> </p> <p> Para obter informações sobre os parâmetros Hora de início e Hora de término, consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de dados</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Não use os parâmetros de configuração para fontes de dados [!DNL Sensor] para determinar quais entradas de log dentro de um arquivo de log devem ser incluídas em um conjunto de dados. Em vez disso, configure a fonte de dados para apontar para todos os arquivos de log em um diretório. Em seguida, use os parâmetros Hora de início e Hora de término de [!DNL Log Processing.cfg] para determinar quais entradas de log devem ser usadas na construção do conjunto de dados. Consulte [Filtros de dados](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d).

<!--
c_log_files.xml
-->

O arquivo que contém os dados do evento deve atender aos seguintes requisitos:

* Cada registro de dados de evento no arquivo deve ser representado por uma linha.
* Os campos em um registro devem ser separados, vazios ou não, por um delimitador ASCII. O servidor do Data Workbench não requer que você use um delimitador específico. Você pode usar qualquer caractere que não seja um caractere final de linha e não apareça em nenhum lugar dentro dos próprios dados do evento.
* Cada registro no arquivo deve conter:

   * Uma ID de rastreamento
   * Um carimbo de data/hora

* Para especificar horas de início e término para o processamento de dados, cada nome de arquivo deve ser do formulário:

   * [!DNL YYYYMMDD-SOURCE.log]

   onde *AAAAMMDD* é o dia da Hora Média de Greenwich (GMT) de todos os dados no arquivo, e *SOURCE* é uma variável que identifica a fonte dos dados contidos no arquivo.

   >[!NOTE]
   >
   >Entre em contato com os Serviços de consultoria da Adobe para obter uma análise dos arquivos de log que você planeja incorporar ao conjunto de dados.

## Parâmetros {#section-83a861ac24954d54bbb9530e4d8bf23c}

Para origens de log de arquivos de log, os parâmetros na tabela a seguir estão disponíveis.

>[!NOTE]
>
>O processamento de fontes de log do arquivo de log requer parâmetros adicionais que são definidos em um arquivo [!DNL Log Processing Dataset Include], que contém um subconjunto dos parâmetros incluídos em um arquivo [!DNL Log Processing.cfg], bem como parâmetros especiais para definir decodificadores para extrair dados do arquivo de log. Para obter informações sobre como definir decodificadores para fontes de log do arquivo de log, consulte [Grupos do decodificador de arquivos de texto](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd).

<table id="table_F33735B5B90A48B0B21FA02D9198CCA9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> O identificador da origem do arquivo de log. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Caminhos de registro </td> 
   <td colname="col2"> <p>Os diretórios onde os arquivos de log são armazenados. O local padrão é o diretório Logs . Um caminho relativo refere-se ao diretório de instalação do servidor do Data Workbench. </p> <p> Você pode usar caracteres curingas para especificar quais arquivos de log processar: 
     <ul id="ul_1F02D26A08D846E2A3114E5C33F60ECF"> 
      <li id="li_ECAE1C03A1C448A1B86AE00B3A955708"> * corresponde a qualquer número de caracteres. </li> 
      <li id="li_24FDB500C5934CAAA4124C435DF4B290"> ? corresponde a um único caractere. </li> 
     </ul> </p> <p> Por exemplo, o caminho de log <span class="filepath"> Logs\*.log</span> corresponde a qualquer arquivo no diretório Logs que termina em <span class="filepath"> .log</span>. </p> <p> Se quiser pesquisar todos os subdiretórios do caminho especificado, defina o parâmetro Recursive como true. </p> <p> Se os arquivos devem ser lidos a partir de uma <span class="wintitle"> Unidade de Servidor de Arquivos</span> do servidor do Data Workbench, você deve inserir os URIs apropriados no parâmetro Caminhos de Log. Por exemplo, o <span class="filepath"> URI/Logs/*.log</span> corresponde a qualquer arquivo <span class="filepath"> .log</span> no diretório Logs . Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurando uma unidade de servidor de arquivos do servidor Insight</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor de registro </td> 
   <td colname="col2"> Informações (Endereço, Nome, Porta, etc.) necessárias para se conectar a um servidor de arquivos. Se houver uma entrada no parâmetro Servidor de Log, os <span class="wintitle"> Caminhos de Log</span> serão interpretados como URIs. Caso contrário, serão interpretados como caminhos locais. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurando uma unidade de servidor de arquivos do servidor Insight</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comprimido </td> 
   <td colname="col2"> Verdadeiro ou falso. Esse valor deve ser definido como true se os arquivos de log a serem lidos pelo servidor do Data Workbench forem arquivos gzip compactados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Grupo decodificador </td> 
   <td colname="col2"> O nome do grupo do decodificador de arquivos de texto a ser aplicado à fonte de log do arquivo de log. Esse nome deve corresponder exatamente ao nome do grupo do decodificador de arquivos de texto correspondente especificado no arquivo <span class="wintitle"> Log Processing Dataset Include</span> . Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Grupos do decodificador de arquivos de texto</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID da Fonte de Log </td> 
   <td colname="col2"> <p>O valor desse parâmetro pode ser qualquer string. Se um valor for especificado, esse parâmetro permitirá diferenciar entradas de log de diferentes fontes de log para identificação de origem ou processamento direcionado. O campo x-log-source-id é preenchido com um valor que identifica a origem do log para cada entrada de log. Por exemplo, se você deseja identificar entradas de log de uma fonte de arquivo de log chamada LogFile01, você pode digitar <span class="filepath"> de LogFile01</span>, e essa sequência seria passada para o campo x-log-source-id para cada entrada de log dessa fonte. </p> <p> Para obter informações sobre o campo x-log-source-id, consulte <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Campos de registro de dados do evento</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Padrão da máscara </td> 
   <td colname="col2"> <p>Uma expressão regular com um subpadrão de captura único que extrai um nome consistente usado para identificar a origem de uma série de arquivos de log. Somente o nome do arquivo é considerado. O caminho e a extensão não são considerados para a correspondência de expressões regulares. Se você não especificar um <span class="wintitle"> padrão de máscara</span>, uma máscara será gerada automaticamente. </p> <p> Para os arquivos <span class="filepath"> Logs\010105server1.log</span> e <span class="filepath"> Logs\010105server2.log</span>, o <span class="wintitle"> padrão de máscara</span> seria <code>[0-9]{6}(.*)</code>. Esse padrão extrai a string "server1" ou "server2" dos nomes de arquivos acima. </p> <p> Consulte <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> Expressões regulares</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recursivo </td> 
   <td colname="col2"> Verdadeiro ou falso. Se este parâmetro for definido como true, todos os subdiretórios de cada caminho especificados em <span class="wintitle"> Caminhos de Log</span> serão pesquisados para procurar arquivos correspondentes ao nome de arquivo especificado ou padrão curinga. O valor padrão é false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rejeitar arquivo </td> 
   <td colname="col2"> O caminho e o nome do arquivo que contém as entradas de log que não atendem às condições do decodificador. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar Tempos de Início/Término </td> 
   <td colname="col2"> <p>Verdadeiro ou falso. Se este parâmetro for definido como true e a Hora de início ou Hora de término for especificada, todos os arquivos para essa fonte de log deverão ter nomes de arquivo começando com datas no formato ISO (AAAAMMDD). Pressupõe-se que cada arquivo contenha dados para um dia GMT (por exemplo, o intervalo de tempo que começa em 0000 GMT em um dia e termina em 0000 GMT no dia seguinte). Se os nomes de arquivos das fontes de log não começarem com datas ISO ou se os arquivos contiverem dados que não correspondem a um dia GMT, esse parâmetro deverá ser definido como false para evitar resultados incorretos. </p> <p> <p>Observação:  Se os requisitos de nomenclatura e intervalo de tempo descritos acima forem cumpridos para os arquivos de log e você definir esse parâmetro como true, o grupo do decodificador de arquivos de texto especificado limitará os arquivos lidos àqueles cujos nomes têm datas ISO que estão entre a Hora de início e a Hora de término especificadas. Se você definir esse parâmetro como falso, o servidor do Data Workbench lê todos os arquivos de log durante o processamento do log para determinar quais arquivos contêm dados no intervalo de Hora de início e Hora de término. </p> </p> <p> Para obter informações sobre os parâmetros Hora de início e Hora de término, consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de dados</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

Neste exemplo, o conjunto de dados é construído a partir de dois tipos de fontes de log.

A Fonte de Log 0 especifica arquivos de log gerados a partir de dados de evento capturados por [!DNL Sensor]. Essa fonte de dados aponta para um diretório chamado Logs e para todos os arquivos nesse diretório com uma extensão [!DNL .vsl] de nome de arquivo.

A Fonte de Log 1 aponta para todos os arquivos no diretório Logs com uma extensão de nome de arquivo [!DNL .txt]. O grupo decodificador para essa fonte de log é chamado de &quot;Logs de Texto&quot;.

![](assets/cfg_LogProcessing_LogSources.png)

Você não deve excluir ou mover arquivos de log depois que as fontes de dados de um conjunto de dados tiverem sido definidas. Somente os arquivos de log recém-criados devem ser adicionados ao diretório das fontes de dados.

<!--
c_xml_log_sources.xml
-->

O arquivo que contém os dados do evento deve atender aos seguintes requisitos:

* Os dados do evento devem ser incluídos em um arquivo XML corretamente formatado com relações pai-filho apropriadas.
* Um grupo decodificador exclusivo deve existir para cada formato de arquivo XML. Para obter informações sobre como construir um grupo decodificador, consulte [Grupos do decodificador de XML](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).
* Cada registro de visitante no arquivo deve conter:

   * Uma ID de rastreamento
   * Um carimbo de data/hora

* Para especificar horas de início e término para o processamento de dados, cada nome de arquivo deve ser do formulário

[!DNL YYYYMMDD-SOURCE.log]

onde *AAAAMMDD* é o dia da Hora Média de Greenwich (GMT) de todos os dados no arquivo, e *SOURCE* é uma variável que identifica a fonte dos dados contidos no arquivo.

Para obter um exemplo de um arquivo XML que atende a esses requisitos, consulte [Grupos do decodificador de XML](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).

>[!NOTE]
>
>Entre em contato com o Adobe Consulting Services para obter uma análise dos arquivos de log XML que você planeja incorporar ao conjunto de dados.

## Parâmetros {#section-d07b96d7f6ad4affb9cc0a0bc1b88c4d}

Para fontes de log XML, os parâmetros na tabela a seguir estão disponíveis.

>[!NOTE]
>
>O processamento de fontes de log XML requer parâmetros adicionais definidos em um arquivo [!DNL Log Processing Dataset Include], que contém um subconjunto de parâmetros incluídos em um arquivo [!DNL Log Processing.cfg], bem como parâmetros especiais para definir decodificadores para extrair dados do arquivo XML. Para obter informações sobre como definir decodificadores para fontes de log XML, consulte [Grupos do decodificador de XML](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).

<table id="table_86B849F379CF4FEBA9294ACEF8F55184"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> O identificador da fonte de log XML. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Caminhos de registro </td> 
   <td colname="col2"> <p>Os diretórios onde as fontes de log XML são armazenadas. O local padrão é o diretório Logs . Um caminho relativo refere-se ao diretório de instalação do servidor do Data Workbench. </p> <p> Você pode usar caracteres curingas para especificar quais fontes de log XML processar: 
     <ul id="ul_0AE5D0ADE0F64CFAA856492A49239F58"> 
      <li id="li_4CBC0D1733F04258B3A55CC6FA714538 "> * corresponde a qualquer número de caracteres </li> 
      <li id="li_81B597436A1241FF94E73C18A0ABBFA1"> ? corresponde a um único caractere </li> 
     </ul> </p> <p>Por exemplo, o caminho de log <span class="filepath"> Logs\*.xml</span> corresponde a qualquer arquivo no diretório Logs que termina em <span class="filepath"> .xml</span>. </p> <p> Se quiser pesquisar todos os subdiretórios do caminho especificado, defina o campo <span class="wintitle"> Recursive</span> como true. </p> <p> <p>Observação: Se os arquivos devem ser lidos a partir de uma <span class="wintitle"> Unidade de Servidor de Arquivos</span> do servidor do Data Workbench, você deve inserir os URIs apropriados no campo <span class="wintitle"> Caminhos de Log</span>. Por exemplo, o <span class="filepath"> URI/Logs/*.xml</span> corresponde a qualquer arquivo <span class="filepath"> .xml</span> no diretório Logs. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurando uma unidade de servidor de arquivos do servidor Insight</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor de registro </td> 
   <td colname="col2"> Informações (Endereço, Nome, Porta, etc.) necessárias para se conectar a um servidor de arquivos. Se houver uma entrada no campo <span class="wintitle"> Servidor de Log</span>, os <span class="wintitle"> Caminhos de Log</span> serão interpretados como URIs. Caso contrário, serão interpretados como caminhos locais. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurando uma unidade de servidor de arquivos do servidor Insight</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comprimido </td> 
   <td colname="col2"> Verdadeiro ou falso. Esse valor deve ser definido como true se as fontes de log XML que serão lidas pelo servidor do Data Workbench forem arquivos gzip compactados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Grupo decodificador </td> 
   <td colname="col2"> O nome do grupo do decodificador de XML a ser aplicado à fonte de log XML. Esse nome deve corresponder exatamente ao nome do grupo do decodificador de XML correspondente especificado no arquivo <span class="wintitle"> Log Processing Dataset Include</span> . Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> Grupos do decodificador de XML</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID da Fonte de Log </td> 
   <td colname="col2"> <p>O valor desse campo pode ser qualquer string. Se um valor for especificado, esse campo permitirá que você diferencie entradas de log de diferentes fontes de log para identificação de origem ou processamento direcionado. O campo x-log-source-id é preenchido com um valor que identifica a origem do log para cada entrada de log. Por exemplo, se você deseja identificar entradas de log de uma fonte de arquivo de log chamada XMLFile01, você pode digitar <span class="filepath"> de XMLFile01</span>, e essa sequência seria passada para o campo x-log-source-id para cada entrada de log dessa fonte. </p> <p> Para obter informações sobre o campo x-log-source-id, consulte <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Campos de registro de dados do evento</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Padrão da máscara </td> 
   <td colname="col2"> <p>Uma expressão regular com um subpadrão de captura único que extrai um nome consistente usado para identificar a origem de uma série de arquivos de log. Somente o nome do arquivo é considerado. O caminho e a extensão não são considerados para a correspondência de expressões regulares. Se você não especificar um <span class="wintitle"> padrão de máscara</span>, uma máscara será gerada automaticamente. </p> <p> Para os arquivos <span class="filepath"> Logs\010105server1.xml</span> e <span class="filepath"> Logs\010105server2.xml</span>, o padrão de máscara seria <code>[0-9]{6}(.*)</code>. Esse padrão extrai a string "server1" ou "server2" dos nomes de arquivos acima. </p> <p> Consulte <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> Expressões regulares</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recursivo </td> 
   <td colname="col2"> Verdadeiro ou falso. Se este parâmetro for definido como true, todos os subdiretórios de cada caminho especificados em <span class="wintitle"> Caminhos de Log</span> serão pesquisados para procurar arquivos correspondentes ao nome de arquivo especificado ou padrão curinga. O valor padrão é false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rejeitar arquivo </td> 
   <td colname="col2"> O caminho e o nome do arquivo que contém as entradas de log que não atendem às condições do decodificador. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar Tempos de Início/Término </td> 
   <td colname="col2"> <p>Verdadeiro ou falso. Se este parâmetro for definido como true e a Hora de início ou Hora de término for especificada, todos os arquivos para essa fonte de log deverão ter nomes de arquivo começando com datas no formato ISO (AAAAMMDD). Pressupõe-se que cada arquivo contenha dados para um dia GMT (por exemplo, o intervalo de tempo que começa em 0000 GMT em um dia e termina em 0000 GMT no dia seguinte). Se os nomes de arquivos das fontes de log não começarem com datas ISO ou se os arquivos contiverem dados que não correspondem a um dia GMT, esse parâmetro deverá ser definido como false para evitar resultados incorretos. </p> <p> <p>Observação:  Se os requisitos de nomeação e intervalo de tempo descritos acima forem cumpridos para os arquivos XML e você definir esse parâmetro como true, o grupo decodificador de XML especificado limitará os arquivos lidos àqueles cujos nomes têm datas ISO que estejam entre a Hora de Início e a Hora de Término especificadas. Se você definir esse parâmetro como falso, o servidor do Data Workbench lê todos os arquivos XML durante o processamento do log para determinar quais arquivos contêm dados no intervalo de Hora inicial e Hora final. </p> </p> <p> Para obter informações sobre os parâmetros Hora de início e Hora de término, consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de dados</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Você não deve excluir ou mover fontes de log XML depois que as fontes de dados de um conjunto de dados tiverem sido definidas. Somente os arquivos XML recém-criados devem ser adicionados ao diretório das fontes de dados.

<!--
AVRO-log-file.xml
-->

O feed de dados Avro fornece uma maneira mais eficiente de integrar os dados ao Data Workbench:

<!-- <a id="section_45E3105B971C4220AE9CF573BEBF6080"></a> -->

* Avro fornece um formato de fonte única para dados de tráfego e comércio.
* O feed Avro é composto de dados compactados de várias fontes fornecidas por dia. Ele fornece apenas campos preenchidos e oferece recursos de monitoramento e notificação, acesso a dados históricos e recuperação automática.
* O schema, um layout autodefinidor de arquivos de log Avro, é incluído no início de cada arquivo.
* Novos campos são adicionados com informações de suporte para assimilar dados de Data Workbench sem qualquer alteração necessária ao decodificador. Dentre eles:

   * Evars: 1-250 (anteriormente 1-75)
   * Eventos personalizados: 1-1000 (versus 1-100)
   * Acesso às variáveis da solução para dados móveis, sociais e de vídeo

>[!NOTE]
>
>Além disso, o uso do feed Avro permite acesso imediato a quaisquer novos campos no feed sem um desligamento, permitindo que os campos sejam atualizados sem requisitos de hora de serviço.

O feed de dados Avro é configurado em arquivos separados:

* Um **Arquivo Avro Log**: Este é o formato de log Avro gerado pelo decodificador para formatar dados de tráfego e comércio.
* Um arquivo **Avro Decoder**: Esse arquivo permite mapear valores para o novo formato Avro. Você pode configurar o decodificador usando o Assistente do decodificador de avro.

## Assistente do Decodificador de Avro {#section-9a824b4c3d5549e7952a7111232035b2}

Este assistente configura o arquivo de log do decodificador de Avro.

Para abrir, clique com o botão direito do mouse em um espaço de trabalho e selecione **Admin** > **Assistentes** > **Assistente do decodificador de avro**.

**Etapa 1:** **selecione um arquivo de log Avro**.

Nesta etapa, você pode selecionar um arquivo de origem para o esquema Avro. Os esquemas podem ser acessados de um arquivo de log (.log) ou de um arquivo decodificador existente (.avro). Os esquemas podem ser extraídos de qualquer arquivo.

| **Arquivo de log Avro ** | Clique em para abrir um arquivo de log (.log) para exibir o esquema na parte superior do arquivo de log e gerar o arquivo decodificador . |
|---|---|
| **Arquivo do Decodificador Avro** | Clique em para abrir e editar o esquema de um arquivo decodificador (.avro) existente. |

**Etapa 2: Selecione Campos** de entrada.

Selecione os campos de entrada a serem usados no conjunto de dados para passar pelo processamento de log. Todos os campos no arquivo serão exibidos, permitindo selecionar campos para o feed.

>[!NOTE]
>
>Um campo [!DNL x-product(Generates row)] é fornecido se uma matriz for encontrada nos dados. Esse campo gera novas linhas para os dados aninhados em uma matriz como campos de entrada. Por exemplo, se você tiver uma linha de Ocorrência com muitos valores de Produto em uma matriz, as linhas serão geradas no arquivo de entrada para cada produto.

| **Selecionar padrões** | Selecione os campos a serem identificados como um conjunto padrão de campos padrão . |
|---|---|
| **Selecionar Todas** | Selecione todos os campos no arquivo . |
| **Desmarcar tudo** | Limpe todos os campos no arquivo . |

**Etapa 3: Selecione os campos que são copiados para gerar linhas.**

Como novas linhas podem ser criadas a partir de valores aninhados em uma matriz, cada nova linha criada deve ter uma ID de rastreamento e um carimbo de data e hora. Essa etapa permite selecionar os campos a serem copiados para linhas do registro pai, como uma ID de rastreamento e um carimbo de data e hora. Você também pode selecionar outros valores que deseja adicionar a cada linha.

| **Selecionar padrões** | Selecione um conjunto padrão de campos padrão que exigem novos valores de coluna adicionados a cada linha, como ID de rastreamento e carimbo de data e hora. Por exemplo, um campo [!DNL hit_source] é um valor padrão que deve ser adicionado a cada nova linha (é definido como um valor padrão na lista). Você pode adicionar outros valores de coluna a cada linha, conforme necessário. |
|---|---|
| **Selecionar Todas** | Selecione todos os campos no arquivo . |
| **Desmarcar tudo** | Limpe todos os campos no arquivo . |

Use a caixa **Pesquisar** para localizar valores na lista.

**Etapa 4: especifique o nome do decodificador**

Atribua um nome ao grupo de campos e salve como um arquivo decodificador. O nome deve corresponder ao nome do grupo Decodificador especificado na fonte de log.

**Etapa 5: Salve o arquivo decodificador.**

O menu de arquivo será aberto para nomear o arquivo decodificador e salvar como um arquivo [!DNL .cfg] na pasta **Logs**.
