---
description: A configuração do conjunto de dados refere-se ao processo de edição dos arquivos de configuração cujos parâmetros fornecem as regras para a construção do conjunto de dados.
solution: Analytics
title: Noções Gerais da Configuração do Conjunto de Dados
topic: Data workbench
uuid: 813933d1-f52d-4584-8edd-ce9cd4aed74a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Noções Gerais da Configuração do Conjunto de Dados{#understanding-dataset-configuration}

A configuração do conjunto de dados refere-se ao processo de edição dos arquivos de configuração cujos parâmetros fornecem as regras para a construção do conjunto de dados.

O conjunto de dados construído reside fisicamente no [!DNL temp.db] arquivo armazenado no computador do servidor da análise de big data, mas os arquivos de configuração do conjunto de dados residem em um diretório para um perfil. Um perfil contém um conjunto de arquivos de configuração que constrói um conjunto de dados (incluindo suas dimensões estendidas) para uma finalidade de análise específica. Além disso, um perfil contém as definições de entidades como métricas, dimensões derivadas, espaços de trabalho, relatórios e visualizações que permitem que os analistas interajam com o conjunto de dados e obtenham informações dele.

O perfil cujos arquivos de configuração de conjunto de dados você está editando é chamado de perfil de conjunto de dados. Um perfil de conjunto de dados faz referência a vários perfis herdados, que podem ser qualquer perfil criado e mantido para que você possa configurar seu aplicativo Adobe para melhor atender às suas necessidades de análise. Um perfil de conjunto de dados também pode fazer referência a perfis internos fornecidos com seu aplicativo Adobe para formarem a base de toda a funcionalidade disponível em seu aplicativo.

Para obter mais informações sobre os diferentes tipos de perfis que estão disponíveis com os aplicativos da Adobe, consulte o Guia *do Usuário da Análise de* big data.

<!--
c_req_config_files.xml
-->

Um perfil de conjunto de dados para qualquer aplicativo da Adobe deve conter os seguintes arquivos de configuração na máquina do Insight Server:

* **Profile.cfg:** Lista os perfis herdados e os servidores de processamento do perfil. Os servidores de processamento são as DPUs do Insight Server que processam os dados do perfil. Se você tiver instalado um cluster do Insight Server, poderá especificar vários computadores do Insight Server para executar um único perfil.

   Para obter instruções para adicionar perfis herdados ao arquivo do perfil de um conjunto de dados, consulte o Guia [!DNL Profile.cfg] de Instalação e Administração de Produtos ** do Servidor. Para obter informações sobre como instalar um cluster do Insight Server ou configurar um perfil de conjunto de dados para execução em um cluster do Insight Server, consulte o Guia *de Instalação e Administração de Produtos para* Servidor.

* **Dataset\Log Processing.cfg:** Controla a fase de processamento de log do processo de construção do conjunto de dados. Consulte Processamento [de log](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-8a63892878004dc389c7dad784fcb061). Para obter mais informações sobre o [!DNL Log Processing.cfg] arquivo, consulte Arquivo [de configuração de processamento de](../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)log.

* **Conjunto de dados\Transformation.cfg:** Controla a fase de transformação do processo de construção do conjunto de dados. Consulte [Transformação](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-88f72e0897a744b5bc03df5039264dda). O [!DNL Transformation.cfg] arquivo normalmente configura o conjunto de dados para análise específica do perfil. Para obter mais informações sobre o [!DNL Transformation.cfg] arquivo, consulte Arquivo [de configuração de](../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md)transformação.

* **O Conjunto De Dados Inclui Arquivos:** Um [!DNL dataset include] arquivo contém um subconjunto dos parâmetros contidos no arquivo [!DNL Log Processing.cfg] ou [!DNL Transformation.cfg] para o perfil do conjunto de dados, mas é armazenado e gerenciado dentro de um perfil herdado. [!DNL Dataset include] os arquivos complementam os arquivos de configuração do conjunto de dados principal. Para obter mais informações, consulte Incluir arquivos [do](../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)conjunto de dados.

O perfil de conjunto de dados fornecido a você durante a implementação do aplicativo Adobe contém um conjunto de arquivos de configuração de conjunto de dados que você pode abrir, editar e salvar usando o [!DNL Profile Manager].

Para obter informações sobre o [!DNL Profile Manager], consulte o Guia *do Usuário do* Insight.

<!--
c_addl_config_files.xml
-->

Embora não seja obrigatório para todos os conjuntos de dados, esses arquivos permitem que você controle outros aspectos do processo de construção do conjunto de dados:

* **Log Processing Mode.cfg:** O [!DNL Log Processing Mode.cfg] arquivo permite pausar o processamento de dados em um conjunto de dados, especificar fontes offline ou especificar a frequência na qual o servidor da análise de big data salva seus arquivos de estado. Consulte Arquivos [de configuração](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)adicionais.

* **Server.cfg:** O [!DNL Server.cfg] arquivo especifica o tamanho padrão do cache de dados (em bytes) para máquinas de análise de big data que se conectam ao servidor de análise de big data. Consulte Arquivos [de configuração](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)adicionais.

* **Transform.cfg e Transform Mode.cfg:** Esses arquivos estarão disponíveis somente se você tiver licenciado a funcionalidade de transformação de dados a ser usada com seu aplicativo Adobe. O [!DNL Transform.cfg] arquivo contém os parâmetros que definem as fontes de log e as transformações de dados para a funcionalidade de transformação. As transformações que você define manipulam os dados de origem e os produzem em um formato especificado. O [!DNL Insight Transform Mode.cfg] arquivo permite pausar o processamento de dados em um conjunto de dados, especificar fontes offline ou especificar a frequência na qual o Insight Server executando a funcionalidade de transformação salva seus arquivos de estado. Consulte Funcionalidade [de transformação](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

<!--
c_next_steps.xml
-->

Para obter informações sobre tarefas específicas de configuração de conjuntos de dados, use a tabela abaixo para localizar e ler sobre as tarefas de seu interesse:

<table id="table_394CFB5135274545B5DA37952EC6943E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Se você quiser... </th> 
   <th colname="col2" class="entry"> Consulte... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Definir fontes de log </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Fontes de registro </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Determine quais entradas de log inserem o conjunto de dados durante o processamento de log </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de dados</a> </p> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condição de entrada do registro</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ativar a divisão das IDs de rastreamento com grandes quantidades de dados de eventos </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Divisão de chave</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurar um servidor Insight para ser executado como uma unidade de servidor de arquivos </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurando uma unidade do servidor de arquivos do Insight Server </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configure um servidor Insight para ser executado como um servidor de normalização centralizado </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurando uma unidade do servidor de arquivos do Insight Server </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Defina o fuso horário a ser usado para criar dimensões de tempo e fazer conversões de tempo </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Fusos horários </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Faça pequenas alterações nos arquivos de configuração do conjunto de dados incluídos nos perfis internos fornecidos pela Adobe </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077"> Edição de conjuntos de dados existentes Incluir arquivos </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Especificar novos campos de dados a serem passados do processamento de log para a transformação </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Criando Novo Conjunto de Dados Incluir Arquivos </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> O Conjunto de Dados de Processamento de Log Inclui Arquivos </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Definir transformações </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformações de dados </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Criando Novo Conjunto de Dados Incluir Arquivos </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> O conjunto de dados de transformação inclui arquivos </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Criar dimensões estendidas </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Dimensões estendidas </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Criando Novo Conjunto de Dados Incluir Arquivos </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> O conjunto de dados de transformação inclui arquivos </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Definir parâmetros a serem usados durante o processamento ou transformação do log </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definindo Parâmetros no Conjunto de Dados Incluir Arquivos </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Saiba mais sobre as interfaces do Insight que permitem monitorar ou gerenciar seu conjunto de dados </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-config-int.md#concept-0ea33a52ce234ec8951e7b4430fbc5ab"> Trabalhar Com Interfaces De Configuração De Conjunto De Dados </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ocultar determinadas dimensões estendidas para que não sejam exibidas no menu de dimensão no Insight </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Ocultar componentes do conjunto de dados </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Substituir determinados arquivos de configuração do conjunto de dados em um perfil que não pode ser modificado ou não </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Ocultar componentes do conjunto de dados </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reprocessar seu conjunto de dados </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocessamento e retransformação </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

