---
description: A configuração do conjunto de dados refere-se ao processo de edição dos arquivos de configuração cujos parâmetros fornecem as regras para a construção do conjunto de dados.
title: Entender a configuração do conjunto de dados
uuid: 813933d1-f52d-4584-8edd-ce9cd4aed74a
exl-id: 1358d08e-d81c-453d-a3a3-c1f279f38192
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 7%

---

# Entender a configuração do conjunto de dados{#understanding-dataset-configuration}

A configuração do conjunto de dados refere-se ao processo de edição dos arquivos de configuração cujos parâmetros fornecem as regras para a construção do conjunto de dados.

O conjunto de dados construído reside fisicamente no arquivo [!DNL temp.db] armazenado no computador do servidor do Data Workbench, mas os arquivos de configuração do conjunto de dados residem em um diretório para um perfil. Um perfil contém um conjunto de arquivos de configuração que criam um conjunto de dados (incluindo suas dimensões estendidas) para uma finalidade de análise específica. Além disso, um perfil contém as definições de entidades, como métricas, dimensões derivadas, espaços de trabalho, relatórios e visualizações, que permitem que os analistas interajam com o conjunto de dados e obtenham informações dele.

O perfil cujos arquivos de configuração do conjunto de dados você está editando é chamado de perfil do conjunto de dados. Um perfil de conjunto de dados faz referência a vários perfis herdados, que podem ser quaisquer perfis criados e mantidos por você, para que possa configurar o aplicativo Adobe para melhor se adequar às suas necessidades de análise. Um perfil de conjunto de dados também pode fazer referência a perfis internos fornecidos com seu aplicativo do Adobe para formar a base de toda a funcionalidade disponível em seu aplicativo.

Para obter mais informações sobre os diferentes tipos de perfis que estão disponíveis com aplicativos Adobe, consulte o *Guia do Usuário do Data Workbench*.

<!--
c_req_config_files.xml
-->

Um perfil de conjunto de dados para qualquer aplicativo do Adobe deve conter os seguintes arquivos de configuração na máquina do servidor Insight:

* **Profile.cfg:** lista os perfis herdados e os servidores de processamento do perfil. Os servidores de processamento são as DPUs do servidor Insight que processam os dados do perfil. Se tiver instalado um cluster do Insight Server, você pode especificar vários computadores do Insight Server para executar um único perfil.

   Para obter instruções para adicionar perfis herdados ao arquivo [!DNL Profile.cfg] de um perfil de conjunto de dados, consulte o *Guia de Instalação e Administração de Produtos de Servidor*. Para obter informações sobre como instalar um cluster do Insight Server ou configurar um perfil de conjunto de dados para ser executado em um cluster do Insight Server, consulte o *Guia de Instalação e Administração de Produtos do Servidor*.

* **Conjunto de dados\Log Processing.cfg:** controla a fase de processamento de log do processo de construção do conjunto de dados. Consulte [Processamento de Log](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-8a63892878004dc389c7dad784fcb061). Para obter mais informações sobre o arquivo [!DNL Log Processing.cfg], consulte [Arquivo de configuração de processamento de log](../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

* **Conjunto de dados\Transformation.cfg:**  controla a fase de transformação do processo de construção do conjunto de dados. Consulte [Transformation](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-88f72e0897a744b5bc03df5039264dda). O arquivo [!DNL Transformation.cfg] normalmente configura o conjunto de dados para análise específica do perfil. Para obter mais informações sobre o arquivo [!DNL Transformation.cfg], consulte [Arquivo de configuração de transformação](../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

* **Arquivos de inclusão do conjunto de dados:** um  [!DNL dataset include] arquivo contém um subconjunto dos parâmetros contidos no  [!DNL Log Processing.cfg] ou no  [!DNL Transformation.cfg] arquivo para o perfil do conjunto de dados, mas é armazenado e gerenciado em um perfil herdado. [!DNL Dataset include] Os arquivos complementam os arquivos de configuração do conjunto de dados principal. Para obter mais informações, consulte [Arquivos de inclusão do conjunto de dados](../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

O perfil do conjunto de dados fornecido a você durante a implementação do aplicativo do Adobe contém um conjunto de arquivos de configuração do conjunto de dados que você pode abrir, editar e salvar usando o [!DNL Profile Manager].

Para obter informações sobre o [!DNL Profile Manager], consulte o *Guia do Usuário do Insight*.

<!--
c_addl_config_files.xml
-->

Embora não seja necessário para todos os conjuntos de dados, esses arquivos permitem controlar outros aspectos do processo de construção do conjunto de dados:

* **Log Processing Mode.cfg:** o  [!DNL Log Processing Mode.cfg] arquivo permite pausar o processamento de dados em um conjunto de dados, especificar fontes offline ou especificar a frequência na qual o servidor do Data Workbench salva seus arquivos de estado. Consulte [Arquivos de Configuração Adicionais](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* **Server.cfg:** o  [!DNL Server.cfg] arquivo especifica o tamanho padrão do cache de dados (em bytes) para máquinas do Data Workbench que se conectam ao servidor do Data Workbench. Consulte [Arquivos de Configuração Adicionais](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* **Transform.cfg e Transform Mode.cfg:** Esses arquivos estarão disponíveis somente se você tiver licenciado a funcionalidade de transformação de dados a ser usada com seu aplicativo Adobe. O arquivo [!DNL Transform.cfg] contém os parâmetros que definem as fontes de log e as transformações de dados para a funcionalidade de transformação. As transformações definidas manipulam os dados de origem e os produzem em um formato especificado. O arquivo [!DNL Insight Transform Mode.cfg] permite pausar o processamento de dados em um conjunto de dados, especificar fontes offline ou especificar a frequência na qual o Servidor Insight que está executando a funcionalidade de transformação salva seus arquivos de estado. Consulte [Funcionalidade de transformação](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

<!--
c_next_steps.xml
-->

Para obter informações sobre tarefas específicas de configuração do conjunto de dados, use a tabela abaixo para localizar e ler sobre as tarefas de seu interesse:

<table id="table_394CFB5135274545B5DA37952EC6943E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Se quiser... </th> 
   <th colname="col2" class="entry"> Consulte... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Definir fontes de log </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Fontes de log </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Determine quais entradas de log inserem o conjunto de dados durante o processamento do log </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de dados</a> </p> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condição de entrada de log</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ativar a divisão das IDs de rastreamento com grandes quantidades de dados de evento </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Divisão de chave</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurar um servidor Insight para ser executado como uma unidade de servidor de arquivos </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurar uma unidade de servidor de arquivos do servidor Insight  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurar um servidor Insight para ser executado como um servidor de normalização centralizado </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurar uma unidade de servidor de arquivos do servidor Insight  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Definir o fuso horário a ser usado para criar dimensões de tempo e fazer conversões de tempo </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Fusos horários </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Faça pequenas alterações nos arquivos de configuração do conjunto de dados incluídos com os perfis internos fornecidos pelo Adobe </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077"> Editar arquivos de inclusão existentes do conjunto de dados </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Especificar novos campos de dados a serem passados do processamento de log para a transformação </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Criar novos arquivos de inclusão do conjunto de dados </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Arquivos de dados do conjunto de dados de processamento de log </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Definir transformações </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformações de dados </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Criar novos arquivos de inclusão do conjunto de dados </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Arquivos de inclusão do conjunto de dados de transformação </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Criar dimensões estendidas </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Dimensões estendidas </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Criar novos arquivos de inclusão do conjunto de dados </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Arquivos de inclusão do conjunto de dados de transformação </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Definir parâmetros a serem usados durante o processamento ou transformação do log </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definir parâmetros nos arquivos de inclusão do conjunto de dados </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Saiba mais sobre as interfaces do Insight que permitem monitorar ou gerenciar seu conjunto de dados </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-config-int.md#concept-0ea33a52ce234ec8951e7b4430fbc5ab"> Trabalhar com interfaces de configuração de conjunto de dados </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ocultar determinadas dimensões estendidas para que não sejam exibidas no menu de dimensão no Insight </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Ocultar componentes do conjunto de dados </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Substituir determinados arquivos de configuração do conjunto de dados em um perfil que você não pode ou não deseja modificar </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Ocultar componentes do conjunto de dados </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reprocessar seu conjunto de dados </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocessar e retransformar </a> </p> </td> 
  </tr> 
 </tbody> 
</table>
