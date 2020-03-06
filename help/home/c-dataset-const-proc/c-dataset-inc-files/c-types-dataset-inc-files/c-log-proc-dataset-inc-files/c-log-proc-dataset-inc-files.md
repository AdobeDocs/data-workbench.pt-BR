---
description: O arquivo de Inclusão do Conjunto de Dados de Processamento de Log para um perfil herdado contém parâmetros associados à fase de processamento de log da construção do conjunto de dados.
solution: Analytics
title: O Conjunto de Dados de Processamento de Log Inclui Arquivos
topic: Data workbench
uuid: 8bf99c9a-f674-4a07-bb3e-de0d9efc9716
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# O Conjunto de Dados de Processamento de Log Inclui Arquivos{#log-processing-dataset-include-files}

O arquivo de Inclusão do Conjunto de Dados de Processamento de Log para um perfil herdado contém parâmetros associados à fase de processamento de log da construção do conjunto de dados.

A primeira linha de um [!DNL Log Processing Dataset Include] arquivo define um tipo [!DNL LogProcessingInclude] que suporta os parâmetros Decoder Groups, Fields, Log Entry Condition, Parameters, Reprocess, Stage e Transformations. Todos os outros parâmetros para o processamento de log devem ser definidos no [!DNL Log Processing.cfg] arquivo no diretório Dataset do perfil do conjunto de dados. É possível nomear um [!DNL Log Processing Dataset Include] arquivo como desejar, mas sua extensão deve ser [!DNL .cfg]. O arquivo deve ser armazenado dentro do nome *\Dataset\Log Processing directory do perfil* herdado. Como os arquivos são carregados recursivamente durante a fase de processamento de log da construção do conjunto de dados, é possível armazenar os [!DNL Log Processing Dataset Include] arquivos em qualquer nível dentro do diretório (por exemplo, nome do perfil *herdado*\Dataset\Log Processing\*nome da pasta*\*incluir nome do arquivo*.cfg).

>[!NOTE]
>
>Muitos parâmetros de configuração específicos da Web para o Site são definidos em [!DNL Log Processing Dataset Include] arquivos. Para obter informações sobre esses parâmetros, consulte Configurações [de configuração para dados](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)da Web.

<table id="table_E2112652CCD443E889A529EEDC4ADF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Grupos do decodificador </td> 
   <td colname="col2"> <p>Obrigatório se você tiver definido arquivos de log ou fontes de log de arquivos XML no arquivo <span class="filepath"> Log Processing.cfg</span> . O arquivo de texto ou os decodificadores XML que você define para extrair campos de dados do arquivo de log e das fontes de log XML. </p> <p> <b>Para adicionar um novo grupo decodificador</b> 
     <ul id="ul_54087499003C48C8B0AD9660A2F46EA9"> 
      <li id="li_E361861E61D246DDB3964C97CC5187E9"> Clique com o botão direito do mouse em <span class="uicontrol"> Decoder Group</span> e clique em <span class="uicontrol"> Adicionar novo</span> &gt; <span class="uicontrol"> TextFileDecoderGroup</span> ou <span class="uicontrol"> XMLDecoderGroup</span>. </li> 
      <li id="li_B2D61A0763AD4FEDB619BF9550EF4602"> No parâmetro Name do novo grupo, digite o nome desejado do grupo decodificador. </li> 
     </ul> </p> <p> <p>Observação:  Quando você especifica um Grupo decodificador no arquivo <span class="filepath"> Log Processing.cfg</span> para o perfil do conjunto de dados, o nome deve corresponder exatamente ao nome inserido aqui. Para obter mais informações, consulte <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Arquivos</a>de log. </p> </p> <p> Para obter informações sobre os decodificadores que podem ser definidos para cada grupo, consulte Grupos <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> do decodificador de arquivos de</a> texto ou Grupos <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> do decodificador de arquivos</a>XML. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campos </td> 
   <td colname="col2"> <p>Lista os campos definidos nas Fontes <span class="wintitle"> de Log ou nas Transformações</span> <span class="wintitle"> em um arquivo de Configuração</span> de Conjunto de Dados de Processamento de <span class="wintitle"> Log, mas usados em transformações, condições ou dimensões estendidas em um arquivo de Configuração</span> de Conjunto de Dados de <span class="wintitle"></span> Transformação devem ser listados aqui. </p> <p> Cada campo abaixo deve estar listado em algum arquivo Incluir <span class="wintitle"> Conjunto de Dados de Processamento de</span> Log: 
     <ul id="ul_D1BB18A80D874C0B9B54DA361698EB30"> 
      <li id="li_7E8B5B697BDA408DBE10D9A63AF295AC"> x-trackingid </li> 
      <li id="li_F5DEE90A596A4A1C86AF874653C4048C"> x-timestamp </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição de entrada do registro </td> 
   <td colname="col2"> <p>Opcional. Define as regras pelas quais as entradas de log são consideradas para inclusão no conjunto de dados. Consulte <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condição</a>de entrada do registro. </p> <p> <p>Observação:  Para ser incluída no conjunto de dados, uma entrada de log deve atender à Condição <span class="wintitle"> de entrada do</span> log no arquivo <span class="filepath"> Log Processing.cfg</span> e em cada arquivo de Inclusão <span class="wintitle"> de Conjunto de Dados de Processamento de</span> Log. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parâmetros </td> 
   <td colname="col2"> Opcional. Uma variável que pode ser referenciada em outros parâmetros de configuração. Para obter mais informações, consulte <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definição de parâmetros no conjunto de dados Incluir arquivos</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reprocessar </td> 
   <td colname="col2"> <p>Opcional. Qualquer caractere ou combinação de caracteres pode ser inserida aqui. Alterar esse parâmetro e salvar o arquivo no servidor da análise de big data inicia o reprocessamento de dados. </p> <p> Para obter informações sobre como reprocessar seus dados, consulte <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocessamento e Retransformação</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Estágio </td> 
   <td colname="col2"> <p>Opcional. O nome do estágio de processamento que se aplica a este arquivo de Inclusão <span class="wintitle"></span> do Conjunto de Dados de Processamento de Log. Os estágios de processamento são definidos no parâmetro Estágios no arquivo <span class="filepath"> Log Processing.cfg</span> . </p> <p> <p>Observação:  Quando você especifica um Palco, o nome do Palco deve corresponder exatamente ao nome listado no parâmetro Estágios no arquivo <span class="filepath"> Log Processing.cfg</span> para o perfil do conjunto de dados. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformações </td> 
   <td colname="col2"> Opcional. Define as transformações de dados que precisam ser aplicadas durante o processamento de log. Para obter informações sobre os tipos de transformação disponíveis, consulte <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformações</a>de dados. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Para obter descrições dos parâmetros no [!DNL Log Processing.cfg] arquivo, consulte Arquivo [de configuração de processamento de](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)log.

Você deve ter os seguintes pontos em mente sempre que estiver trabalhando com [!DNL Log Processing Dataset Include] arquivos:

* A alteração de qualquer um dos parâmetros neste arquivo requer o reprocessamento de todos os dados.
* Você pode adicionar qualquer um dos parâmetros descritos acima ao [!DNL Log Processing Dataset Include] arquivo abrindo e editando o arquivo no Bloco de notas. Quaisquer alterações feitas e salvas serão exibidas quando o arquivo for reaberto na análise de big data. Ao adicionar um novo parâmetro, use a tecla Space (não a tecla Tab) para recuar dois (2) espaços à direita do nível de cabeçalho anterior.

