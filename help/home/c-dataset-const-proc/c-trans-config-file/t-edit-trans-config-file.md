---
description: Etapas para editar o arquivo Transformation.cfg para um perfil de conjunto de dados.
solution: Analytics
title: Editando o arquivo de configuração de transformação
topic: Data workbench
uuid: 77b9e566-4a9a-4ea1-b5ab-63a4574c0fdb
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Editando o arquivo de configuração de transformação{#editing-the-transformation-configuration-file}

Etapas para editar o arquivo Transformation.cfg para um perfil de conjunto de dados.

1. Ao trabalhar em seu perfil de conjunto de dados, abra o [!DNL Profile Manager] e clique **[!UICONTROL Dataset]** para mostrar seu conteúdo.

   Para obter informações sobre como abrir e trabalhar com o [!DNL Profile Manager], consulte o Guia *do usuário da Análise de* big data.

   >[!NOTE]
   >
   >Um subdiretório Transformation pode existir no diretório Dataset. Esse subdiretório contém os [!DNL Transformation Dataset Include] arquivos que foram criados para um ou mais perfis herdados. Para obter informações sobre [!DNL Transformation Dataset Include] arquivos, consulte [Arquivo de inclusão de conjuntos de dados](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL Transformation.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção para este arquivo é exibida na [!DNL User] coluna.
1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. A [!DNL Transformation.cfg] janela é exibida.

   Você também pode abrir o [!DNL Transformation.cfg] arquivo a partir de um [!DNL Transformation Dependency Map]. Para obter informações sobre [!DNL transformation dependency maps], consulte Ferramentas [de configuração de](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)conjuntos de dados.

1. Edite os parâmetros no arquivo de configuração usando a tabela a seguir como guia.

   Ao editar o [!DNL Transformation.cfg] arquivo em uma janela de análise de big data, você pode usar teclas de atalho para recursos básicos de edição, incluindo recortar (Ctrl+x ), copiar (Ctrl+c), colar (Ctrl+v ), desfazer (Ctrl+z ), refazer (Ctrl+Shift+z ), selecionar a seção (clique+arrastar) e selecionar tudo (Ctrl+a ). Além disso, você pode usar os atalhos para copiar e colar o texto de um arquivo de configuração ( [!DNL .cfg]) para outro.

   >[!NOTE]
   >
   >Os [!DNL Transformation Dataset Include] arquivos de um perfil herdado contêm um subconjunto dos parâmetros descritos na tabela a seguir, bem como alguns parâmetros adicionais. Para obter informações sobre [!DNL Transformation Dataset Include] arquivos, consulte Incluir arquivos [do conjunto de dados](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)

   <table id="table_5E184F67CCEC4421B2BBD4261711A6FE"> 
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
      <ul id="ul_1EC55DA4936946C98E447E1476E8280F"> 
       <li id="li_F2D862833F4B451C965E1ED6C05DCE1B"> 1 de janeiro de 2013 HH:MM:SS EDT </li> 
       <li id="li_EB7FFEB2E2C24EAFB8E4B14F2479DA3D"> Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Por exemplo, especificar "29 de julho de 2013 00:00:00 EDT" como a Hora de término inclui dados até 28 de julho de 2013, às 11:59:59 EDT. </p> <p> Você deve especificar um fuso horário. O fuso horário não assumirá GMT como padrão se não for especificado. Para obter uma lista de abreviações de fuso horário suportadas pelo servidor da análise de big data, consulte <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de fuso horário </a>. </p> <p> <p>Observação:  Se você especificar um valor para Hora de término, um parâmetro chamado Hora de término será definido e aplicado durante toda a fase de transformação da construção do conjunto de dados. Para obter informações sobre parâmetros, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definindo Parâmetros em Arquivos de Inclusão de Conjunto de Dados </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dimensões estendidas </td> 
      <td colname="col2"> Opcional. A Adobe recomenda definir dimensões estendidas em um ou mais <span class="wintitle"> </span> arquivos de inclusão de conjuntos de dados de transformação. Para obter informações, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Transformation Dataset Include Files (Incluir arquivos do conjunto de dados de transformação) </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Limite de hash </td> 
      <td colname="col2"> <p>Opcional. Um fator de amostragem para a subamostragem aleatória de linhas. Se definido como um número n, somente uma de cada n IDs de rastreamento informa o conjunto de dados, reduzindo o número total de linhas no conjunto de dados por um fator n. Para criar um conjunto de dados que exija 100% de precisão (ou seja, para incluir todas as linhas), você definiria o Limite de hash como 1. </p> <p> Se o Limite de Hash for especificado nos arquivos <span class="filepath"> Log Processing.cfg </span> e <span class="filepath"> Transformation.cfg </span> , ele não será aplicado em sequência; aplica-se o máximo dos valores definidos em qualquer arquivo de configuração. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Condição de entrada do registro </td> 
      <td colname="col2"> Opcional. Define as regras pelas quais a saída de entradas de log do processamento de log é considerada para inclusão no perfil do conjunto de dados. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condição de entrada do registro </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nova condição do visitante </td> 
      <td colname="col2"> Opcional. Para uso com dados da Web. Define as regras pelas quais os visitantes são considerados para inclusão nos dados. A <span class="wintitle"> Nova condição de visitante </span> define a primeira entrada de registro para um visitante (ordenada por hora) que deve ser usada no conjunto de dados. Todas as entradas de log subsequentes para esse visitante são incluídas no conjunto de dados, independentemente de atenderem a essa condição. Consulte <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-new-vstr-con.md#concept-1d0d8e26718447ad9d235e00b33a36f3"> Nova condição de visitante </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Reprocessar </td> 
      <td colname="col2"> <p>Opcional. Qualquer caractere ou combinação de caracteres pode ser inserida aqui. Alterar esse parâmetro e salvar o arquivo inicia a retransformação de dados. </p> <p> Para obter informações sobre como reprocessar seus dados, consulte <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocessamento e Retransformação </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Verificação de esquema </td> 
      <td colname="col2"> Verdadeiro ou falso. Se verdadeiro, o servidor de análise de big data identifica problemas de corrupção do conjunto de dados e registra informações sobre os problemas nos arquivos de log no diretório Trace do servidor de análise de big data. O valor padrão é true. A Adobe recomenda deixar esse parâmetro definido como true a qualquer momento. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Estágios </td> 
      <td colname="col2"> <p>Opcional. Os nomes dos estágios de processamento que podem ser usados em <span class="wintitle"> Transformation Dataset Incluem </span> arquivos. Os estágios de processamento fornecem uma maneira de ordenar as transformações definidas nos arquivos <span class="wintitle"> </span> Transformation Dataset Include. Esse parâmetro é muito útil se você tiver definido uma ou mais transformações em vários arquivos de Inclusão de Conjunto de Dados de <span class="wintitle"> </span> Transformação e desejar que transformações específicas sejam executadas em pontos específicos durante a transformação. </p> <p> A ordem em que você lista os estágios aqui determina a ordem em que as transformações nos arquivos <span class="wintitle"> Transformation Dataset Include </span> são executadas durante a transformação. <span class="wintitle"> O pré-processamento </span> e o <span class="wintitle"> pós-processamento </span> são fases integradas; <span class="wintitle"> O pré-processamento </span> é sempre o primeiro estágio, e o <span class="wintitle"> pós-processamento </span> é sempre o último estágio. Por padrão, há uma etapa nomeada chamada <span class="wintitle"> Padrão </span>. </p> <p> <b>Para adicionar uma nova etapa de processamento</b> </p> <p> 
      <ul id="ul_6AF2EF72CEE34FA88575C46FA333BDA1"> 
       <li id="li_80627E7A89CE4E57A4228C4F5496533F"> Na janela <span class="filepath"> Transformation.cfg </span> , clique com o botão direito do mouse em <span class="uicontrol"> Estágios </span> e clique em <span class="uicontrol"> Adicionar novo </span> &gt; <span class="uicontrol"> Estágio </span>. </li> 
       <li id="li_321BEDB1E95F4AA4B282EED32A4CA196"> Insira um nome para o novo estágio. </li> 
      </ul> </p> <p> <b>Para excluir um estágio de processamento existente</b> </p> <p> 
      <ul id="ul_2EFA5A40982A48919E9946BF1955110A"> 
       <li id="li_3B3829DA34FD4774B3F9F94074099794"> Clique com o botão direito do mouse no número correspondente ao estágio que deseja excluir e clique em <span class="uicontrol"> Remover </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> </p> <p> <p>Observação:  Quando você especifica um Palco em um Conjunto de Dados de <span class="wintitle"> Transformação Incluir </span> arquivos, o nome do palco deve corresponder exatamente ao nome inserido aqui. Para obter mais informações sobre o conjunto de dados incluir arquivos, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Conjunto de dados Incluir arquivos </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hora inicial </td> 
      <td colname="col2"> <p>Opcional. Filtre os dados para incluir entradas de log com carimbos de data e hora nesse momento ou depois dele. A Adobe recomenda usar um dos seguintes formatos para o tempo: 
      <ul id="ul_6BC86CCB1FC447ACAC4045E08C8EF8F8"> 
       <li id="li_2151B3F7FAD54F38B6C33E25CDCACBBE"> 1 de janeiro de 2013 HH:MM:SS EDT </li> 
       <li id="li_CA1BB675C1244104915FB9ED96A3013D"> Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Por exemplo, especificar 29 de julho de 2013 00:00:00 EDT como a Hora de <span class="wintitle"> início </span> inclui dados que começam a partir de 29 de julho de 2013, às 12:00:00 AM EDT. </p> <p> Você deve especificar um fuso horário. O fuso horário não assumirá GMT como padrão se não for especificado. Para obter uma lista de abreviações de fuso horário suportadas pelo servidor da análise de big data, consulte <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de fuso horário </a>. </p> <p> <p>Observação:  Se você especificar um valor para a Hora de início, um parâmetro chamado Hora de início será definido e aplicado em toda a fase de transformação da construção do conjunto de dados. Para obter informações sobre parâmetros, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definindo Parâmetros em Arquivos de Inclusão de Conjunto de Dados </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformações </td> 
      <td colname="col2"> Opcional. A Adobe recomenda definir transformações para a fase de transformação da construção do conjunto de dados em um ou mais arquivos de Inclusão do conjunto de dados de <span class="wintitle"> transformação </span> . Para obter informações, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Transformation Dataset Include Files (Incluir arquivos do conjunto de dados de transformação) </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fuso Horário </td> 
      <td colname="col2"> <p>Fuso horário do perfil do conjunto de dados. Os fusos horários são usados para conversões de tempo e para criar dimensões de tempo. Consulte <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Fusos horários </a>. </p> <p> <p>Observação:  Quando definido no arquivo <span class="filepath"> Log Processing.cfg </span> , o parâmetro Fuso horário é usado apenas para conversões de tempo. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
1. Na [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção para [!DNL Transformation.cfg]na [!DNL User] coluna, em seguida, clique em **[!UICONTROL Save to]** > * **[!UICONTROL dataset profile name]** para que as alterações feitas localmente entrem em vigor. A retransformação dos dados começa após a sincronização do perfil do conjunto de dados.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pela Adobe, pois suas alterações são substituídas quando você instala atualizações nesses perfis.

   Para obter informações sobre como reprocessar ou retransformar seus dados, consulte [Reprocessamento e Retransformação](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
