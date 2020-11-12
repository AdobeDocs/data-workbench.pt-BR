---
description: As fontes de log são arquivos que contêm os dados a serem usados para criar um conjunto de dados.
solution: Analytics
title: Fontes de log
topic: Data workbench
uuid: ea21c3d7-9188-4ba8-bacd-052d678bd799
translation-type: tm+mt
source-git-commit: 0727e5b18c89a22b6ee775b1293d3b68e5cee81c
workflow-type: tm+mt
source-wordcount: '3664'
ht-degree: 1%

---


# Fontes de log{#log-sources}

As fontes de log são arquivos que contêm os dados a serem usados para criar um conjunto de dados.

Os dados disponíveis nas fontes de log são chamados de dados de evento porque cada registro de dados representa um registro de transação ou uma única instância de um evento. O servidor da análise de big data pode processar fontes de log derivadas de dados coletados por [!DNL Sensors] outras fontes de dados ou extraídos delas.

* **Dados coletados por [!DNL Sensors]: ** Os dados coletados por HTTP e servidores de aplicativos são transmitidos para servidores de análise de big data, que convertem os dados em arquivos de log ( [!DNL Sensors] [!DNL .vsl]) altamente compactados. Consulte Arquivos [de sensor](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009).

* **Dados extraídos pelo Insight Server:** O servidor da análise de big data lê os dados do evento contidos em arquivos simples, arquivos XML ou bancos de dados compatíveis com ODBC e usa seus decodificadores para extrair os elementos desejados dos dados. Esses dados de evento não precisam ser residentes na memória, mas os registros que contêm os dados devem incluir uma ID de rastreamento. Consulte Arquivos [de](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)registro, Fontes [de registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)XML e Fontes [de dados](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)ODBC.

**Para adicionar uma fonte de log**

1. Abrir [!DNL Log Processing.cfg] na análise de big data.
1. Clique com o botão direito do mouse **[!UICONTROL Log Sources]** e, em seguida, clique em **[!UICONTROL Add New]**.

1. Selecione uma das opções a seguir:

   * **[!UICONTROL Sensor]**
   * **[!UICONTROL Log File]**
   * **[!UICONTROL XML Log Source]**
   * **[!UICONTROL ODBC Data Source]**

1. Os parâmetros específicos usados para definir um conjunto de dados variam com base no tipo de fonte de log a ser usada no processo de configuração do conjunto de dados. Especifique os parâmetros conforme indicado na seção correspondente à fonte de log apropriada:

   * [Arquivos do sensor](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009)
   * [Arquivos de registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)
   * [Fontes de registro XML](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)
   * [Fontes de dados ODBC](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)

1. Depois de definir sua fonte de log (e fazer alterações em outros parâmetros) no [!DNL Log Processing.cfg] arquivo, salve o arquivo localmente e salve-o no perfil do conjunto de dados no servidor da análise de big data.

   >[!NOTE]
   >
   >Um servidor de análise de big data [!DNL File Server Unit] pode receber e armazenar [!DNL Sensor] arquivos, arquivos de log e arquivos XML e servi-los para o servidor de análise de big data [!DNL Data Processing Units] que constrói o conjunto de dados. Consulte [Configurando uma unidade](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d)do servidor de arquivos do Insight Server.

   É possível abrir a configuração de qualquer fonte de registro a partir de uma [!DNL Transformation Dependency Map]. Para obter informações sobre [!DNL Transformation Dependency Map], consulte Ferramentas [de configuração de](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)conjuntos de dados.

<!--
c_sensor_files.xml
-->

## Requisitos {#section-d5901a4872774ad5bd01a18db114f1f2}

Os dados de evento coletados por HTTP e servidores de aplicativos são transmitidos para servidores de análise de big data, que convertem os dados em arquivos de log ( [!DNL Sensors] [!DNL .vsl]) altamente compactados. O formato de [!DNL .vsl] arquivo é gerenciado pelo servidor da análise de big data e cada arquivo tem um nome do formato:

AAAMMDD-*SENSORID*.VSL

onde AAAMMDD é a data do arquivo, e *SENSORID* é o nome (atribuído pela organização) que indica qual [!DNL Sensor] coletou e transmitiu os dados ao servidor da análise de big data.

## Parâmetros {#section-5c3f1e341c284486aeba3452057da7f3}

Para [!DNL Sensor] arquivos, os seguintes parâmetros estão disponíveis:

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
   <td colname="col2"> <p>Os diretórios nos quais os arquivos <span class="filepath"> .vsl</span> são armazenados. O local padrão é o diretório Logs. Um caminho relativo refere-se ao diretório de instalação do servidor de análise de big data. </p> <p>Você pode usar caracteres curinga para especificar quais arquivos <span class="filepath"> .vsl</span> devem ser processados: 
     <ul id="ul_AE144ED0FAB94FE8B32599A058659DE1"> 
      <li id="li_1E4E4CFD72C34B5EB71A3C59877950A9"> * corresponde a qualquer número de caracteres </li> 
      <li id="li_4664400FC12E44B39B28438B85D20ED8"> ? corresponde a um único caractere </li> 
     </ul> </p> <p> Por exemplo, o caminho de log <span class="filepath"> Logs\*.vsl</span> corresponde a qualquer arquivo no diretório Logs que termina em <span class="filepath"> .vsl</span>. O caminho de log <span class="filepath"> Logs\*-SENSOR?.vsl</span> corresponde arquivos no diretório Logs com qualquer data (AAAMMDD) e um único caractere após SENSOR, como em SENSOR1. </p> <p> Se você quiser pesquisar todos os subdiretórios do caminho especificado, deverá definir o parâmetro Recursive como true. </p> <p> <p>Observação: Se os arquivos forem lidos a partir da Unidade <span class="wintitle"> do Servidor de</span>Arquivos do servidor de análise de big data, você deverá informar os URIs apropriados no parâmetro Caminhos de Log. Por exemplo, o <span class="filepath"> URI /Logs/*-*.vsl</span> corresponde a qualquer arquivo <span class="filepath"> .vsl</span> no diretório Logs. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurando uma unidade</a>do servidor de arquivos do Insight Server. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor de registro </td> 
   <td colname="col2">Informações (Endereço, Nome, Porta etc.) necessárias para se conectar a um servidor de arquivos. Se houver uma entrada no parâmetro Servidor de log, os Caminhos <span class="wintitle"></span> de log serão interpretados como URIs. Caso contrário, serão interpretados como caminhos locais. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurando uma unidade</a>do servidor de arquivos do Insight Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de origem do registro </td> 
   <td colname="col2"> <p>O valor desse parâmetro pode ser qualquer string. Se um valor for especificado, esse parâmetro permitirá que você diferencie entradas de log de diferentes fontes de log para identificação de origem ou processamento direcionado. O campo x-log-source-id é preenchido com um valor que identifica a fonte de log para cada entrada de log. Por exemplo, se você quiser identificar entradas de log de um <span class="wintitle"> Sensor</span> chamado VSensor01, você pode digitar <span class="filepath"> de VSensor01</span>, e essa string será transmitida para o campo x-log-source-id para cada entrada de log dessa fonte. </p> <p> Para obter informações sobre o campo x-log-source-id, consulte Campos <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> de registro de dados do</a>Evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recursivo </td> 
   <td colname="col2"> Verdadeiro ou falso. Se definido como true, todos os subdiretórios de cada caminho especificado em Caminhos <span class="wintitle"> de</span> registro serão pesquisados para localizar arquivos que correspondam ao nome do arquivo especificado ou ao padrão curinga. O valor padrão é false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar Start/hora de término </td> 
   <td colname="col2"> <p>Verdadeiro ou falso. Se definido como true e Hora do Start ou Hora de término for especificado, todos os arquivos para essa fonte de log deverão ter nomes de arquivo começando com datas no formato ISO (AAAMMDD). Pressupõe-se que cada arquivo contenha dados de um dia GMT (por exemplo, o intervalo de tempo que começa em 0000 GMT em um dia e termina em 0000 GMT no dia seguinte). Se os arquivos de fontes de log contiverem dados que não correspondem a um dia GMT, esse parâmetro deverá ser definido como false para evitar resultados incorretos. </p> <p> <p>Observação: Por padrão, <span class="filepath"> os </span>arquivos .vsl que contêm dados coletados pelo <span class="wintitle"> sensor</span> atendem automaticamente aos requisitos de nomeação e intervalo de tempo descritos acima. Se você definir esse parâmetro como true, o servidor da análise de big data sempre processará dados de arquivos cujos nomes incluem datas ISO que se situam entre a Hora do Start e a Hora de término especificados. Se você definir esse parâmetro como falso, o servidor da análise de big data fará a leitura de todos os arquivos <span class="filepath"> .vsl</span> durante o processamento do log para determinar quais arquivos contêm dados dentro do intervalo de Tempo de Start e Hora de término. </p> </p> <p> Para obter informações sobre os parâmetros Hora e Hora de término do Start, consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros</a>de dados. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Não use os parâmetros de configuração para fontes de [!DNL Sensor] dados para determinar quais entradas de log dentro de um arquivo de log devem ser incluídas em um conjunto de dados. Em vez disso, configure a fonte de dados para apontar para todos os arquivos de log dentro de um diretório. Em seguida, use os parâmetros Hora e Hora de término do Start para determinar quais entradas de log devem ser usadas na construção do conjunto de dados. [!DNL Log Processing.cfg] Consulte Filtros [de dados](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d).

<!--
c_log_files.xml
-->

O arquivo que contém os dados do evento deve atender aos seguintes requisitos:

* Cada registro de dados de evento no arquivo deve ser representado por uma linha.
* Os campos em um registro devem ser separados, vazios ou não, por um delimitador ASCII. O servidor da análise de big data não exige o uso de um delimitador específico. Você pode usar qualquer caractere que não seja um caractere final de linha e não apareça em nenhum lugar dentro dos próprios dados do evento.
* Cada registro no arquivo deve conter:

   * Uma ID de rastreamento
   * Um carimbo de data e hora

* Para especificar start e horas de término para o processamento de dados, cada nome de arquivo deve ser do formulário:

   * [!DNL YYYYMMDD-SOURCE.log]

   onde *AAAMMDD* é o dia GMT (Greenwich Mean Time) de todos os dados do arquivo, e *SOURCE* é uma variável que identifica a fonte dos dados contidos no arquivo.

   >[!NOTE]
   >
   >Entre em contato com os Serviços de consultoria da Adobe para obter uma análise dos arquivos de log que você planeja incorporar ao conjunto de dados.

## Parâmetros {#section-83a861ac24954d54bbb9530e4d8bf23c}

Para fontes de log de arquivos de log, os parâmetros na tabela a seguir estão disponíveis.

>[!NOTE]
>
>O processamento das fontes de log do arquivo de log requer parâmetros adicionais definidos em um [!DNL Log Processing Dataset Include] arquivo, que contém um subconjunto dos parâmetros incluídos em um [!DNL Log Processing.cfg] arquivo, bem como parâmetros especiais para a definição de decodificadores para extrair dados do arquivo de log. Para obter informações sobre como definir decodificadores para fontes de log de arquivos, consulte Grupos [do decodificador de arquivos de](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd)texto.

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
   <td colname="col2"> O identificador da fonte do arquivo de log. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Caminhos de registro </td> 
   <td colname="col2"> <p>Os diretórios nos quais os arquivos de log são armazenados. O local padrão é o diretório Logs. Um caminho relativo refere-se ao diretório de instalação do servidor de análise de big data. </p> <p> Você pode usar caracteres curinga para especificar quais arquivos de log processar: 
     <ul id="ul_1F02D26A08D846E2A3114E5C33F60ECF"> 
      <li id="li_ECAE1C03A1C448A1B86AE00B3A955708"> * corresponde a qualquer número de caracteres. </li> 
      <li id="li_24FDB500C5934CAAA4124C435DF4B290"> ? corresponde a um único caractere. </li> 
     </ul> </p> <p> Por exemplo, o caminho de log <span class="filepath"> Logs\*.log</span> corresponde a qualquer arquivo no diretório Logs que termina em <span class="filepath"> .log</span>. </p> <p> Se quiser pesquisar todos os subdiretórios do caminho especificado, você deverá definir o parâmetro Recursive como true. </p> <p> Se os arquivos forem lidos a partir da Unidade <span class="wintitle"> do Servidor de</span>Arquivos do servidor de análise de big data, você deverá informar os URIs apropriados no parâmetro Caminhos de Log. Por exemplo, o <span class="filepath"> URI/Logs/*.log</span> corresponde a qualquer arquivo <span class="filepath"> .log</span> no diretório Logs. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurando uma unidade</a>do servidor de arquivos do Insight Server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor de registro </td> 
   <td colname="col2"> Informações (Endereço, Nome, Porta etc.) necessárias para se conectar a um servidor de arquivos. Se houver uma entrada no parâmetro Servidor de log, os Caminhos <span class="wintitle"></span> de log serão interpretados como URIs. Caso contrário, serão interpretados como caminhos locais. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurando uma unidade</a>do servidor de arquivos do Insight Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compactado </td> 
   <td colname="col2"> Verdadeiro ou falso. Esse valor deve ser definido como true se os arquivos de log a serem lidos pelo servidor de análise de big data forem arquivos gzip compactados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Grupo decodificador </td> 
   <td colname="col2"> O nome do grupo do decodificador de arquivos de texto a ser aplicado à fonte de log do arquivo de log. Esse nome deve corresponder exatamente ao nome do grupo decodificador de arquivos de texto correspondente especificado no arquivo Incluir <span class="wintitle"> Conjunto de Dados de Processamento de</span> Log. See <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Text File Decoder Groups</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de origem do registro </td> 
   <td colname="col2"> <p>O valor desse parâmetro pode ser qualquer string. Se um valor for especificado, esse parâmetro permitirá que você diferencie entradas de log de diferentes fontes de log para identificação de origem ou processamento direcionado. O campo x-log-source-id é preenchido com um valor que identifica a fonte de log para cada entrada de log. Por exemplo, se você deseja identificar entradas de log de uma fonte de arquivo de log chamada LogFile01, você pode digitar <span class="filepath"> de LogFile01</span>, e essa string seria passada para o campo x-log-source-id para cada entrada de log dessa fonte. </p> <p> Para obter informações sobre o campo x-log-source-id, consulte Campos <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> de registro de dados do</a>Evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Padrão de máscara </td> 
   <td colname="col2"> <p>Uma expressão regular com um único subpadrão de captura que extrai um nome consistente usado para identificar a origem de uma série de arquivos de log. Somente o nome do arquivo é considerado. O caminho e a extensão não são considerados para a correspondência regular de expressões. Se você não especificar um padrão <span class="wintitle"> de</span>máscara, uma máscara será gerada automaticamente. </p> <p> Para os arquivos <span class="filepath"> Logs\010105server1.log</span> e <span class="filepath"> Logs\010105server2.log</span>, o padrão <span class="wintitle"> da</span> máscara seria <code>[0-9]{6}(.*)</code>. Este padrão extrai a string "server1" ou "server2" dos nomes de arquivo acima. </p> <p> Consulte <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> Expressões</a>regulares. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recursivo </td> 
   <td colname="col2"> Verdadeiro ou falso. Se esse parâmetro estiver definido como true, todos os subdiretórios de cada caminho especificado em Caminhos <span class="wintitle"> de</span> registro serão pesquisados para localizar arquivos que correspondam ao nome do arquivo especificado ou ao padrão curinga. O valor padrão é false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rejeitar arquivo </td> 
   <td colname="col2"> O caminho e o nome do arquivo que contém as entradas de log que não atendem às condições do decodificador. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar Start/hora de término </td> 
   <td colname="col2"> <p>Verdadeiro ou falso. Se esse parâmetro for definido como true e a Hora ou Hora de término do Start for especificada, todos os arquivos dessa fonte de log deverão ter nomes de arquivo que comecem com datas no formato ISO (AAAMMDD). Pressupõe-se que cada arquivo contenha dados de um dia GMT (por exemplo, o intervalo de tempo que começa em 0000 GMT em um dia e termina em 0000 GMT no dia seguinte). Se os nomes dos arquivos das fontes de log não começarem com datas ISO, ou se os arquivos contiverem dados que não correspondem a um dia GMT, esse parâmetro deverá ser definido como false para evitar resultados incorretos. </p> <p> <p>Observação:  Se os requisitos de nomeação e intervalo de tempo descritos acima forem cumpridos para os arquivos de log e você definir esse parâmetro como true, o grupo decodificador de arquivos de texto especificado limitará os arquivos lidos àqueles cujos nomes têm datas ISO que se situam entre a Hora do Start e a Hora de término especificadas. Se você definir esse parâmetro como falso, o servidor da análise de big data fará a leitura de todos os arquivos de log durante o processamento do log para determinar quais arquivos contêm dados dentro do intervalo de Tempo de Start e Hora de término. </p> </p> <p> Para obter informações sobre os parâmetros Hora e Hora de término do Start, consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros</a>de dados. </p> </td> 
  </tr> 
 </tbody> 
</table>

Neste exemplo, o conjunto de dados é construído a partir de dois tipos de fontes de log.

A Fonte de Log 0 especifica os arquivos de log gerados a partir dos dados de evento capturados por [!DNL Sensor]. Essa fonte de dados aponta para um diretório chamado Logs e para todos os arquivos desse diretório com uma extensão de nome de [!DNL .vsl] arquivo.

A Fonte de registro 1 aponta para todos os arquivos no diretório Logs com uma extensão de nome de [!DNL .txt] arquivo. O grupo decodificador para essa fonte de log é chamado de &quot;Logs de texto&quot;.

![](assets/cfg_LogProcessing_LogSources.png)

Você não deve excluir ou mover arquivos de log depois que as fontes de dados de um conjunto de dados tiverem sido definidas. Somente os arquivos de log recém-criados devem ser adicionados ao diretório das fontes de dados.

<!--
c_xml_log_sources.xml
-->

O arquivo que contém os dados do evento deve atender aos seguintes requisitos:

* Os dados do evento devem ser incluídos em um arquivo XML corretamente formatado com relações pai-filho apropriadas.
* Um grupo decodificador exclusivo deve existir para cada formato de arquivo XML. Para obter informações sobre como criar um grupo de decodificadores, consulte Grupos [de decodificadores](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3)XML.
* Cada registro de visitante no arquivo deve conter:

   * Uma ID de rastreamento
   * Um carimbo de data e hora

* Para especificar start e horas de término para o processamento de dados, cada nome de arquivo deve ser do formulário

[!DNL YYYYMMDD-SOURCE.log]

onde *AAAMMDD* é o dia GMT (Greenwich Mean Time) de todos os dados do arquivo, e *SOURCE* é uma variável que identifica a fonte dos dados contidos no arquivo.

Para obter um exemplo de um arquivo XML que atende a esses requisitos, consulte Grupos [do decodificador de](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3)XML.

>[!NOTE]
>
>Entre em contato com os Serviços de consultoria da Adobe para obter uma análise dos arquivos de registro XML que você planeja incorporar ao conjunto de dados.

## Parâmetros {#section-d07b96d7f6ad4affb9cc0a0bc1b88c4d}

Para fontes de log XML, os parâmetros na tabela a seguir estão disponíveis.

>[!NOTE]
>
>O processamento de fontes de log XML requer parâmetros adicionais definidos em um [!DNL Log Processing Dataset Include] arquivo, que contém um subconjunto dos parâmetros incluídos em um [!DNL Log Processing.cfg] arquivo, bem como parâmetros especiais para a definição de decodificadores para extrair dados do arquivo XML. Para obter informações sobre como definir decodificadores para fontes de log XML, consulte Grupos [do decodificador](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3)XML.

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
   <td colname="col2"> <p>Os diretórios nos quais as fontes de log XML são armazenadas. O local padrão é o diretório Logs. Um caminho relativo refere-se ao diretório de instalação do servidor de análise de big data. </p> <p> Você pode usar caracteres curinga para especificar quais fontes de log XML processar: 
     <ul id="ul_0AE5D0ADE0F64CFAA856492A49239F58"> 
      <li id="li_4CBC0D1733F04258B3A55CC6FA714538 "> * corresponde a qualquer número de caracteres </li> 
      <li id="li_81B597436A1241FF94E73C18A0ABBFA1"> ? corresponde a um único caractere </li> 
     </ul> </p> <p>Por exemplo, o caminho de log <span class="filepath"> Logs\*.xml</span> corresponde a qualquer arquivo no diretório Logs que termina em <span class="filepath"> .xml</span>. </p> <p> Se quiser pesquisar todos os subdiretórios do caminho especificado, defina o campo <span class="wintitle"> Recursivo</span> como verdadeiro. </p> <p> <p>Observação: Se os arquivos forem lidos a partir da Unidade <span class="wintitle"> do Servidor de</span>Arquivos do servidor de análise de big data, você deverá informar os URIs apropriados no campo Caminhos <span class="wintitle"> de</span> Log. Por exemplo, o <span class="filepath"> URI/Logs/*.xml</span> corresponde a qualquer arquivo <span class="filepath"> .xml</span> no diretório Logs. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurando uma unidade</a>do servidor de arquivos do Insight Server. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor de registro </td> 
   <td colname="col2"> Informações (Endereço, Nome, Porta etc.) necessárias para se conectar a um servidor de arquivos. Se houver uma entrada no campo <span class="wintitle"> Servidor</span> de Log, os Caminhos <span class="wintitle"> de</span> Log serão interpretados como URIs. Caso contrário, serão interpretados como caminhos locais. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurando uma unidade</a>do servidor de arquivos do Insight Server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compactado </td> 
   <td colname="col2"> Verdadeiro ou falso. Esse valor deve ser definido como true se as fontes de log XML a serem lidas pelo servidor de análise de big data forem arquivos gzip compactados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Grupo decodificador </td> 
   <td colname="col2"> O nome do grupo decodificador XML a ser aplicado à fonte de log XML. Esse nome deve corresponder exatamente ao nome do grupo decodificador XML correspondente especificado no arquivo de Inclusão <span class="wintitle"> do Conjunto de Dados de Processamento de</span> Log. See <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> XML Decoder Groups</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de origem do registro </td> 
   <td colname="col2"> <p>O valor desse campo pode ser qualquer string. Se um valor for especificado, esse campo permitirá que você diferencie entradas de log de diferentes fontes de log para identificação de origem ou processamento direcionado. O campo x-log-source-id é preenchido com um valor que identifica a fonte de log para cada entrada de log. Por exemplo, se você deseja identificar entradas de log de uma fonte de arquivo de log chamada XMLFile01, você pode digitar <span class="filepath"> de XMLFile01</span>, e essa string seria passada para o campo x-log-source-id para cada entrada de log dessa fonte. </p> <p> Para obter informações sobre o campo x-log-source-id, consulte Campos <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> de registro de dados do</a>Evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Padrão de máscara </td> 
   <td colname="col2"> <p>Uma expressão regular com um único subpadrão de captura que extrai um nome consistente usado para identificar a origem de uma série de arquivos de log. Somente o nome do arquivo é considerado. O caminho e a extensão não são considerados para a correspondência regular de expressões. Se você não especificar um padrão <span class="wintitle"> de</span>máscara, uma máscara será gerada automaticamente. </p> <p> Para os arquivos <span class="filepath"> Logs\010105server1.xml</span> e <span class="filepath"> Logs\010105server2.xml</span>, o padrão de máscara seria <code>[0-9]{6}(.*)</code>. Este padrão extrai a string "server1" ou "server2" dos nomes de arquivo acima. </p> <p> Consulte <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> Expressões</a>regulares. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recursivo </td> 
   <td colname="col2"> Verdadeiro ou falso. Se esse parâmetro estiver definido como true, todos os subdiretórios de cada caminho especificado em Caminhos <span class="wintitle"> de</span> registro serão pesquisados para localizar arquivos que correspondam ao nome do arquivo especificado ou ao padrão curinga. O valor padrão é false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rejeitar arquivo </td> 
   <td colname="col2"> O caminho e o nome do arquivo que contém as entradas de log que não atendem às condições do decodificador. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar Start/hora de término </td> 
   <td colname="col2"> <p>Verdadeiro ou falso. Se esse parâmetro for definido como true e a Hora ou Hora de término do Start for especificada, todos os arquivos dessa fonte de log deverão ter nomes de arquivo que comecem com datas no formato ISO (AAAMMDD). Pressupõe-se que cada arquivo contenha dados de um dia GMT (por exemplo, o intervalo de tempo que começa em 0000 GMT em um dia e termina em 0000 GMT no dia seguinte). Se os nomes dos arquivos das fontes de log não começarem com datas ISO, ou se os arquivos contiverem dados que não correspondem a um dia GMT, esse parâmetro deverá ser definido como false para evitar resultados incorretos. </p> <p> <p>Observação:  Se os requisitos de nomeação e intervalo de tempo descritos acima forem cumpridos para os arquivos XML e você definir esse parâmetro como true, o grupo decodificador XML especificado limita os arquivos lidos àqueles cujos nomes têm datas ISO que se situam entre a Hora do Start e a Hora de término especificadas. Se você definir esse parâmetro como falso, o servidor da análise de big data fará a leitura de todos os arquivos XML durante o processamento do log para determinar quais arquivos contêm dados dentro do intervalo de Tempo de Start e Hora de término. </p> </p> <p> Para obter informações sobre os parâmetros Hora e Hora de término do Start, consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros</a>de dados. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Você não deve excluir ou mover fontes de log XML depois que as fontes de dados de um conjunto de dados forem definidas. Somente os arquivos XML recém-criados devem ser adicionados ao diretório das fontes de dados.

<!--
AVRO-log-file.xml
-->

O feed de dados Avro fornece uma maneira mais eficiente de integrar dados à Data Workbench:

<!-- <a id="section_45E3105B971C4220AE9CF573BEBF6080"></a> -->

* A Avro fornece um formato de fonte única para dados de tráfego e comércio.
* O feed Avro é composto de dados de várias partes de origem fornecidas por dia. Ele fornece apenas campos preenchidos e recursos de monitoramento e notificação, acesso a dados históricos e recuperação automática.
* O schema, um layout autodefinidor de arquivos de log Avro, está incluído no início de cada arquivo.
* Novos campos são adicionados com informações de suporte para assimilar dados de Data Workbench sem quaisquer alterações necessárias no decodificador. Dentre eles:

   * Evars: 1-250 (anteriormente 1-75)
   * Eventos personalizados: 1-1000 (versus 1-100)
   * Acesso a variáveis de solução para dados móveis, sociais e de vídeo

>[!NOTE]
>
>Além disso, o uso do feed Avro permite o acesso imediato a quaisquer novos campos no feed sem um desligamento, permitindo que os campos sejam atualizados sem requisitos de hora de serviço.

O feed de dados Avro é configurado em arquivos separados:

* Um arquivo **de log** Avro: Esse é o formato de log Avro gerado pelo decodificador para formatar dados de tráfego e comércio.
* Um arquivo **Decoder** Avro: Esse arquivo permite mapear valores para o novo formato Avro. Você pode configurar o decodificador usando o Assistente do Decodificador de Avro.

## Assistente do Decodificador de Avro {#section-9a824b4c3d5549e7952a7111232035b2}

Este assistente configura o arquivo de log do decodificador Avro.

Para abrir, clique com o botão direito do mouse em um espaço de trabalho e selecione **Admin** > **Assistentes** > Assistente do **Avro Decoder**.

**Etapa 1:** **Selecione um Arquivo** de Log Avro.

Nesta etapa, você pode selecionar um arquivo de origem para o schema Avro. Os schemas podem ser acessados de um arquivo de log (.log) ou de um arquivo de decodificador existente (.avro). Schemas podem ser extraídos de qualquer um dos arquivos.

| **Arquivo de log Avro ** | Clique para abrir um arquivo de log (.log) para visualização do schema na parte superior do arquivo de log e gerar o arquivo decodificador. |
|---|---|
| **Arquivo Decodificador Avro** | Clique para abrir e editar o schema de um arquivo de decodificador (.avro) existente. |

**Etapa 2: Selecione Campos** de entrada.

Selecione os campos de entrada a serem usados no conjunto de dados para passar pelo processamento de log. Todos os campos no arquivo serão exibidos, permitindo que você selecione os campos para o feed.

>[!NOTE]
>
>Um [!DNL x-product(Generates row)] campo é fornecido se uma matriz for encontrada nos dados. Esse campo gera novas linhas para os dados aninhados em uma matriz como campos de entrada. Por exemplo, se você tiver uma linha Ocorrência com muitos valores de Produto em uma matriz, as linhas serão geradas no arquivo de entrada para cada produto.

| **Selecionar padrões** | Selecione os campos para identificar como um conjunto padrão de campos padrão. |
|---|---|
| **Selecionar Todas** | Selecione todos os campos no arquivo. |
| **Desmarcar tudo** | Limpe todos os campos no arquivo. |

**Etapa 3: Selecione os campos que são copiados para gerar linhas.**

Como novas linhas podem ser criadas a partir de valores aninhados em uma matriz, cada nova linha criada deve ter uma ID de rastreamento e um carimbo de data e hora. Essa etapa permite selecionar os campos a serem copiados para linhas do registro pai, como uma ID de rastreamento e um carimbo de data e hora. Você também pode selecionar outros valores que deseja adicionar a cada linha.

| **Selecionar padrões** | Selecione um conjunto padrão de campos padrão que exigem novos valores de coluna adicionados a cada linha, como uma ID de rastreamento e um carimbo de data e hora. Por exemplo, um [!DNL hit_source] campo é um valor padrão necessário para ser adicionado a cada nova linha (é definido como um valor padrão na lista). Você pode adicionar outros valores de coluna a cada linha, conforme necessário. |
|---|---|
| **Selecionar Todas** | Selecione todos os campos no arquivo. |
| **Desmarcar tudo** | Limpe todos os campos no arquivo. |

Use a caixa **Pesquisar** para localizar valores na lista.

**Etapa 4:Especifique o nome do decodificador**

Atribua um nome ao grupo de campos e salve como um arquivo decodificador. O nome deve corresponder ao nome do grupo Decodificador especificado na sua fonte de log.

**Etapa 5: Salve o arquivo decodificador.**

O menu de arquivos será aberto para nomear o arquivo decodificador e salvar como um [!DNL .cfg] arquivo na pasta **Logs** .
