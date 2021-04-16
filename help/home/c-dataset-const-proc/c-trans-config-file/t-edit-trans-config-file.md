---
description: Etapas para editar o arquivo Transformation.cfg para um perfil de conjunto de dados.
title: Editar o arquivo de configuração de transformação
uuid: 77b9e566-4a9a-4ea1-b5ab-63a4574c0fdb
exl-id: 3fab17a4-d356-4548-b977-f5d409870753
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1135'
ht-degree: 3%

---

# Editar o arquivo de configuração de transformação{#editing-the-transformation-configuration-file}

Etapas para editar o arquivo Transformation.cfg para um perfil de conjunto de dados.

1. Ao trabalhar no perfil do conjunto de dados, abra o [!DNL Profile Manager] e clique em **[!UICONTROL Dataset]** para mostrar seu conteúdo.

   Para obter informações sobre como abrir e trabalhar com o [!DNL Profile Manager], consulte o *Guia do Usuário do Data Workbench*.

   >[!NOTE]
   >
   >Pode existir um subdiretório Transformation no diretório do conjunto de dados. Esse subdiretório contém os arquivos [!DNL Transformation Dataset Include] que foram criados para um ou mais perfis herdados. Para obter informações sobre arquivos [!DNL Transformation Dataset Include], consulte [Arquivos de inclusão do conjunto de dados](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL Transformation.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece na coluna [!DNL User].
1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. A janela [!DNL Transformation.cfg] é exibida.

   Você também pode abrir o arquivo [!DNL Transformation.cfg] de um [!DNL Transformation Dependency Map]. Para obter informações sobre [!DNL transformation dependency maps], consulte [Ferramentas de Configuração do Conjunto de Dados](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

1. Edite os parâmetros no arquivo de configuração usando a tabela a seguir como guia.

   Ao editar o arquivo [!DNL Transformation.cfg] em uma janela do Data Workbench, você pode usar teclas de atalho para recursos básicos de edição, incluindo recortar (Ctrl+x ), copiar (Ctrl+c) , colar (Ctrl+v ), desfazer (Ctrl+z ), refazer (Ctrl+Shift+z ), selecionar seção (clicar+arrastar) e selecionar tudo (Ctrl+a ). Além disso, é possível usar os atalhos para copiar e colar o texto de um arquivo de configuração ( [!DNL .cfg]) para outro.

   >[!NOTE]
   >
   >Um arquivo [!DNL Transformation Dataset Include] para um perfil herdado contém um subconjunto dos parâmetros descritos na tabela a seguir, bem como alguns parâmetros adicionais. Para obter informações sobre arquivos [!DNL Transformation Dataset Include], consulte [Arquivos de inclusão do conjunto de dados](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)

   <table id="table_5E184F67CCEC4421B2BBD4261711A6FE"> 
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
      <ul id="ul_1EC55DA4936946C98E447E1476E8280F"> 
       <li id="li_F2D862833F4B451C965E1ED6C05DCE1B"> 1 de janeiro de 2013 HH:MM:SS EDT </li> 
       <li id="li_EB7FFEB2E2C24EAFB8E4B14F2479DA3D"> 1 de janeiro de 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Por exemplo, especificar "29 de julho de 2013 00:00:00 EDT", pois a Hora de término inclui dados até 28 de julho de 2013, às 11:59:59 EDT. </p> <p> Você deve especificar um fuso horário. O fuso horário não assume GMT como padrão se não estiver especificado. Para obter uma lista de abreviações de fuso horário compatíveis com o servidor do Data Workbench, consulte <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de fuso horário </a>. </p> <p> <p>Observação:  Se você especificar um valor para a Hora de término, um parâmetro chamado Hora de término será definido e aplicado durante toda a fase de transformação da construção do conjunto de dados. Para obter informações sobre parâmetros, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definindo Parâmetros nos Arquivos de Inclusão do Conjunto de Dados </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dimensões estendidas </td> 
      <td colname="col2"> Opcional. O Adobe recomenda definir dimensões estendidas em um ou mais arquivos <span class="wintitle"> de inclusão do conjunto de dados de transformação </span>. Para obter informações, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Arquivos de inclusão do conjunto de dados de transformação </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Limite de hash </td> 
      <td colname="col2"> <p>Opcional. Fator de amostragem para a subamostragem aleatória de linhas. Se definida como um número n, somente uma de cada IDs de rastreamento n inserirá o conjunto de dados, reduzindo o número total de linhas no conjunto de dados por um fator n. Para criar um conjunto de dados que requer 100% de precisão (ou seja, para incluir todas as linhas), você define o Limite de Hash como 1. </p> <p> Se o Limite de Hash for especificado nos arquivos <span class="filepath"> Log Processing.cfg </span> e <span class="filepath"> Transformation.cfg </span>, ele não será aplicado em sequência; aplica-se o máximo dos valores definidos em qualquer arquivo de configuração. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Condição de entrada de log </td> 
      <td colname="col2"> Opcional. Define as regras pelas quais as entradas de log saídas do processamento de log são consideradas para inclusão no perfil do conjunto de dados. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condição de entrada de log </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Condição de novo visitante </td> 
      <td colname="col2"> Opcional. Para uso com dados da Web. Define as regras pelas quais os visitantes são considerados para inclusão nos dados. A <span class="wintitle"> Condição de novo visitante </span> define a primeira entrada de log de um visitante (ordenada por tempo) que deve ser usada no conjunto de dados. Todas as entradas de log subsequentes para esse visitante são incluídas no conjunto de dados, independentemente de atenderem a essa condição. Consulte <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-new-vstr-con.md#concept-1d0d8e26718447ad9d235e00b33a36f3"> Condição de novo visitante </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Reprocessar </td> 
      <td colname="col2"> <p>Opcional. Qualquer caractere ou combinação de caracteres pode ser inserida aqui. Alterar esse parâmetro e salvar o arquivo inicia a retransformação dos dados. </p> <p> Para obter informações sobre como reprocessar seus dados, consulte <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocessando e Retransformação </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Verificação de esquema </td> 
      <td colname="col2"> Verdadeiro ou falso. Se true, o servidor do Data Workbench identificará problemas de corrupção do conjunto de dados e registrará informações sobre os problemas nos arquivos de log no diretório Trace do servidor do Data Workbench. O valor padrão é true. O Adobe recomenda deixar esse parâmetro definido como true a qualquer momento. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Estágios </td> 
      <td colname="col2"> <p>Opcional. Os nomes dos estágios de processamento que podem ser usados em arquivos <span class="wintitle"> de Inclusão </span> do Conjunto de Dados de Transformação. As etapas de processamento fornecem uma maneira de ordenar as transformações definidas nos arquivos <span class="wintitle"> de Inclusão do Conjunto de Dados de Transformação </span>. Esse parâmetro é muito útil se você tiver definido uma ou mais transformações em vários arquivos <span class="wintitle"> de inclusão do conjunto de dados de transformação </span> e desejar que transformações específicas sejam executadas em pontos específicos durante a transformação. </p> <p> A ordem em que você lista os estágios aqui determina a ordem em que as transformações nos arquivos <span class="wintitle"> de Inclusão do Conjunto de Dados de Transformação </span> são executadas durante a transformação. <span class="wintitle"> O pré-processamento  </span> e o  <span class="wintitle"> pós-processamento  </span> são etapas integradas;  <span class="wintitle"> O pré-processamento  </span> é sempre a primeira etapa e o  <span class="wintitle"> pós-processamento  </span> é sempre a última. Por padrão, há um estágio nomeado chamado <span class="wintitle"> Padrão </span>. </p> <p> <b>Para adicionar uma nova etapa de processamento</b> </p> <p> 
      <ul id="ul_6AF2EF72CEE34FA88575C46FA333BDA1"> 
       <li id="li_80627E7A89CE4E57A4228C4F5496533F"> Na janela <span class="filepath"> Transformation.cfg </span>, clique com o botão direito do mouse em <span class="uicontrol"> Estágios </span> e clique em <span class="uicontrol"> Adicionar Novo </span> &gt; <span class="uicontrol"> Estágio </span>. </li> 
       <li id="li_321BEDB1E95F4AA4B282EED32A4CA196"> Insira um nome para o novo estágio. </li> 
      </ul> </p> <p> <b>Para excluir uma etapa de processamento existente</b> </p> <p> 
      <ul id="ul_2EFA5A40982A48919E9946BF1955110A"> 
       <li id="li_3B3829DA34FD4774B3F9F94074099794"> Clique com o botão direito do mouse no número correspondente ao estágio que deseja excluir e clique em <span class="uicontrol"> Remover </span><i>&lt; <span class="uicontrol"> #stage_number </span></i>. </li> 
      </ul> </p> <p> <p>Observação:  Quando você especifica um Estágio em um arquivo <span class="wintitle"> de Inclusão do Conjunto de Dados de Transformação </span> , o nome do palco deve corresponder exatamente ao nome inserido aqui. Para obter mais informações sobre arquivos de inclusão do conjunto de dados, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Arquivos de inclusão do conjunto de dados </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hora inicial </td> 
      <td colname="col2"> <p>Opcional. Filtre os dados para incluir entradas de log com carimbos de data e hora nesse momento ou depois dele. O Adobe recomenda usar um dos seguintes formatos para o momento: 
      <ul id="ul_6BC86CCB1FC447ACAC4045E08C8EF8F8"> 
       <li id="li_2151B3F7FAD54F38B6C33E25CDCACBBE"> 1 de janeiro de 2013 HH:MM:SS EDT </li> 
       <li id="li_CA1BB675C1244104915FB9ED96A3013D"> 1 de janeiro de 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Por exemplo, especificar 29 de julho de 2013 00:00:00 EDT como <span class="wintitle"> Hora de início </span> inclui dados a partir de 29 de julho de 2013, às 12:00:00 EDT. </p> <p> Você deve especificar um fuso horário. O fuso horário não assume GMT como padrão se não estiver especificado. Para obter uma lista de abreviações de fuso horário compatíveis com o servidor do Data Workbench, consulte <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Códigos de fuso horário </a>. </p> <p> <p>Observação:  Se você especificar um valor para a Hora de início, um parâmetro chamado Hora de início será definido e aplicado durante toda a fase de transformação da construção do conjunto de dados. Para obter informações sobre parâmetros, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definindo Parâmetros nos Arquivos de Inclusão do Conjunto de Dados </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformações </td> 
      <td colname="col2"> Opcional. O Adobe recomenda definir transformações para a fase de transformação da construção do conjunto de dados em um ou mais arquivos <span class="wintitle"> Transformation Dataset Include </span> . Para obter informações, consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Arquivos de inclusão do conjunto de dados de transformação </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fuso horário </td> 
      <td colname="col2"> <p>Fuso horário do perfil do conjunto de dados. Os fusos horários são usados para conversões de tempo e para criar dimensões de tempo. Consulte <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Fusos horários </a>. </p> <p> <p>Observação:  Quando definido no arquivo <span class="filepath"> Log Processing.cfg </span>, o parâmetro Time Zone é usado somente para conversões de tempo. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
1. No [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção de [!DNL Transformation.cfg]na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > * **[!UICONTROL dataset profile name]** para que as alterações feitas localmente tenham efeito. A retransformação dos dados começa após a sincronização do perfil do conjunto de dados.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pelo Adobe, pois as alterações são substituídas ao instalar atualizações nesses perfis.

   Para obter informações sobre como reprocessar ou retransformar seus dados, consulte [Reprocessando e Retransformação](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
