---
description: O arquivo de Inclusão do conjunto de dados de processamento de log para um perfil herdado contém parâmetros associados à fase de processamento de log da construção do conjunto de dados.
title: Arquivos de dados do conjunto de dados de processamento de log
uuid: 8bf99c9a-f674-4a07-bb3e-de0d9efc9716
exl-id: 06d8046d-6bac-4ccd-bcef-06f7c9ec7619
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 3%

---

# Arquivos de dados do conjunto de dados de processamento de log{#log-processing-dataset-include-files}

{{eol}}

O arquivo de Inclusão do conjunto de dados de processamento de log para um perfil herdado contém parâmetros associados à fase de processamento de log da construção do conjunto de dados.

A primeira linha de um [!DNL Log Processing Dataset Include] arquivo define um tipo [!DNL LogProcessingInclude] que suporta os parâmetros de Grupos, Campos, Condição de entrada de log, Parâmetros, Reprocessamento, Estágio e Transformações do decodificador. Todos os outros parâmetros para processamento de log devem ser definidos na variável [!DNL Log Processing.cfg] no diretório do conjunto de dados do perfil do conjunto de dados. Você pode nomear um [!DNL Log Processing Dataset Include] arquivar tudo o que quiser, mas a extensão de arquivo deve ser [!DNL .cfg]. O arquivo deve ser armazenado no *nome de perfil herdado*\Dataset\Log Processing diretory. Como os arquivos são carregados recursivamente durante a fase de processamento de log da construção do conjunto de dados, você pode armazenar a variável [!DNL Log Processing Dataset Include] arquivos em qualquer nível dentro do diretório (por exemplo, *nome de perfil herdado*\Dataset\Log Processing\*nome da pasta*\*incluir nome do arquivo*.cfg).

>[!NOTE]
>
>Muitos parâmetros de configuração específicos da Web para o Site são definidos em [!DNL Log Processing Dataset Include] arquivos. Para obter informações sobre esses parâmetros, consulte [Configurações para dados da Web](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

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
   <td colname="col2"> <p>Obrigatório se você tiver definido arquivo de log ou fontes de log do arquivo XML no <span class="filepath"> Log Processing.cfg</span> arquivo. O arquivo de texto ou decodificadores XML definidos para extrair campos de dados do arquivo de log e fontes de log XML. </p> <p> <b>Para adicionar um novo grupo decodificador</b> 
     <ul id="ul_54087499003C48C8B0AD9660A2F46EA9"> 
      <li id="li_E361861E61D246DDB3964C97CC5187E9"> Clique com o botão direito do mouse <span class="uicontrol"> Grupo decodificador</span> e clique em <span class="uicontrol"> Adicionar novo</span> &gt; <span class="uicontrol"> TextFileDecoderGroup</span> ou <span class="uicontrol"> XMLDecoderGroup</span>. </li> 
      <li id="li_B2D61A0763AD4FEDB619BF9550EF4602"> No parâmetro Name do novo grupo, insira o nome desejado do grupo decodificador. </li> 
     </ul> </p> <p> <p>Observação: Ao especificar um Grupo decodificador na variável <span class="filepath"> Log Processing.cfg</span> para o perfil do conjunto de dados, o nome deve corresponder exatamente ao nome inserido aqui. Para obter mais informações, consulte <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Arquivos de registro</a>. </p> </p> <p> Para obter informações sobre os decodificadores que podem ser definidos para cada grupo, consulte <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Grupos do decodificador de arquivos de texto</a> ou <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> Grupos do decodificador de XML</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campos </td> 
   <td colname="col2"> <p>Lista os campos definidos em <span class="wintitle"> Fontes de log</span> ou <span class="wintitle"> Transformações</span> em <span class="wintitle"> Configuração do conjunto de dados de processamento de log</span> , mas usado em transformações, condições ou dimensões estendidas em uma <span class="wintitle"> Configuração do conjunto de dados de transformação</span> deve ser listado aqui. </p> <p> Cada campo abaixo deve ser listado em alguns <span class="wintitle"> Inclusão do conjunto de dados de processamento de log</span> arquivo: 
     <ul id="ul_D1BB18A80D874C0B9B54DA361698EB30"> 
      <li id="li_7E8B5B697BDA408DBE10D9A63AF295AC"> x-trackingid </li> 
      <li id="li_F5DEE90A596A4A1C86AF874653C4048C"> x-timestamp </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição de entrada de log </td> 
   <td colname="col2"> <p>Opcional. Define as regras pelas quais as entradas de log são consideradas para inclusão no conjunto de dados. Consulte <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condição de entrada de log</a>. </p> <p> <p>Observação: Para ser incluído no conjunto de dados, uma entrada de log deve atender ao <span class="wintitle"> Condição de entrada de log</span> no <span class="filepath"> Log Processing.cfg</span> e em cada <span class="wintitle"> Inclusão do conjunto de dados de processamento de log</span> arquivo. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parâmetros </td> 
   <td colname="col2"> Opcional. Uma variável que pode ser referenciada em outros parâmetros de configuração. Para obter mais informações, consulte <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definir parâmetros nos arquivos de inclusão do conjunto de dados</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reprocessar </td> 
   <td colname="col2"> <p>Opcional. Qualquer caractere ou combinação de caracteres pode ser inserida aqui. Alterar esse parâmetro e salvar o arquivo no servidor do Data Workbench inicia o reprocessamento de dados. </p> <p> Para obter informações sobre como reprocessar seus dados, consulte <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocessamento e retransformação</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fase </td> 
   <td colname="col2"> <p>Opcional. O nome da etapa de processamento que se aplica a essa <span class="wintitle"> Inclusão do conjunto de dados de processamento de log</span> arquivo. Os estágios de processamento são definidos no parâmetro Estágios da variável <span class="filepath"> Log Processing.cfg</span> arquivo. </p> <p> <p>Observação: Quando você especifica um Estágio, o nome do Estágio deve corresponder exatamente ao nome listado no parâmetro Estágios na <span class="filepath"> Log Processing.cfg</span> para o perfil do conjunto de dados. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformações </td> 
   <td colname="col2"> Opcional. Define as transformações de dados que precisam ser aplicadas durante o processamento do log. Para obter informações sobre os tipos de transformação disponíveis, consulte <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformações de dados</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Para obter descrições dos parâmetros no [!DNL Log Processing.cfg] arquivo, consulte [Arquivo de configuração de processamento de log](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

Lembre-se dos pontos a seguir sempre que estiver trabalhando com [!DNL Log Processing Dataset Include] arquivos:

* Alterar qualquer um dos parâmetros neste arquivo requer o reprocessamento de todos os dados.
* Você pode adicionar qualquer um dos parâmetros descritos acima à [!DNL Log Processing Dataset Include] abrindo e editando o arquivo no Bloco de notas. Quaisquer alterações feitas e salvas serão exibidas quando você reabrir o arquivo no Data Workbench. Ao adicionar um novo parâmetro, use a tecla Space (não a tecla Tab) para recuar dois (2) espaços à direita do nível de cabeçalho anterior.
