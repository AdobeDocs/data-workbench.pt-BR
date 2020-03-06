---
description: O arquivo Transformation Dataset Include para um perfil herdado contém parâmetros associados à fase de transformação da construção do conjunto de dados.
solution: Analytics
title: O conjunto de dados de transformação inclui arquivos
topic: Data workbench
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# O conjunto de dados de transformação inclui arquivos{#transformation-dataset-include-files}

O arquivo Transformation Dataset Include para um perfil herdado contém parâmetros associados à fase de transformação da construção do conjunto de dados.

A primeira linha do arquivo define um tipo [!DNL TransformationInclude] que suporta os parâmetros Dimensões estendidas, Parâmetros, Reprocessamento, Palco e Transformações. Todos os outros parâmetros devem ser definidos no [!DNL Transformation.cfg] arquivo no diretório Dataset do perfil do conjunto de dados.

A inclusão de parâmetros diferentes de Dimensões estendidas, Parâmetros, Reprocesso, Estágio e Transformações em um [!DNL Transformation Dataset Include] arquivo gera erros.

É possível nomear um [!DNL Transformation Dataset Include] arquivo como desejar, mas sua extensão deve ser [!DNL .cfg]. O arquivo deve ser armazenado dentro do nome *\Dataset\Transformation directory do perfil* herdado. Como os arquivos são carregados recursivamente durante a fase de transformação da construção do conjunto de dados, é possível armazenar os [!DNL Transformation Dataset Include] arquivos em qualquer nível dentro do diretório (por exemplo, nome do perfil *herdado*\Dataset\Transformation\*nome da pasta*\*incluir nome do arquivo*.cfg).

>[!NOTE]
>
>Muitos parâmetros de configuração específicos da Web para o Site são definidos em [!DNL Transformation Dataset Include] arquivos. Para obter informações sobre esses parâmetros, consulte Configurações [de configuração para dados](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)da Web.

A tabela a seguir descreve os parâmetros que estão disponíveis em um [!DNL Transformation Dataset Include] arquivo:

<table id="table_7BD343888D9145BCBA889B531A4D18F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimensões estendidas </td> 
   <td colname="col2"> Opcional. Define as dimensões estendidas. Consulte <a href="../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Dimensões</a>estendidas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parâmetros </td> 
   <td colname="col2"> Opcional. Uma variável que pode ser referenciada em outros parâmetros de configuração. Para obter mais informações, consulte <a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definição de parâmetros no conjunto de dados Incluir arquivos</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reprocessar </td> 
   <td colname="col2"> <p>Opcional. Qualquer caractere ou combinação de caracteres pode ser inserida aqui. Alterar esse parâmetro e salvar o arquivo inicia a retransformação de dados. </p> <p> Para obter informações sobre como reprocessar seus dados, consulte <a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocessamento e Retransformação</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Estágio </td> 
   <td colname="col2"> <p>Opcional. O nome do estágio de processamento que se aplica a esse <span class="wintitle"> arquivo Incluir</span> conjunto de dados de transformação. Os estágios de processamento são definidos no parâmetro Stages no arquivo <span class="filepath"> Transformation.cfg</span> . </p> <p> <p>Observação: Quando você especifica um Palco, o nome do Palco deve corresponder exatamente ao nome listado no parâmetro Estágios no arquivo <span class="filepath"> Transformation.cfg</span> para o perfil do conjunto de dados. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformações </td> 
   <td colname="col2"> Opcional. Define as transformações de dados que precisam ser aplicadas durante a transformação. Para obter informações sobre os tipos de transformação disponíveis, consulte <a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformações</a>de dados. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Para obter descrições dos parâmetros no [!DNL Transformation.cfg] arquivo, consulte Arquivo [de configuração de](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md)transformação.

Você deve ter os seguintes pontos em mente sempre que estiver trabalhando com [!DNL Transformation Dataset Include] arquivos:

* A alteração de qualquer um dos parâmetros neste arquivo requer a retransformação dos dados.
* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]e [!DNL AppendURI] transformações funcionam somente quando definidas em um [!DNL Transformation Dataset Configuration] arquivo. Para obter informações sobre essas transformações, consulte Transformações [de dados](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

* Você pode adicionar qualquer um dos parâmetros descritos acima ao [!DNL Transformation Dataset Include] arquivo abrindo e editando o arquivo no Bloco de notas. Quaisquer alterações feitas e salvas serão exibidas quando o arquivo for reaberto na análise de big data. Ao adicionar um novo parâmetro, use a tecla Space (não a tecla Tab) para recuar dois (2) espaços à direita do nível de cabeçalho anterior.

Se você assinar o serviço de dados [!DNL IP Geo-location] [!DNL IP Geo-intelligence] ou da Adobe, a Adobe fornece um perfil interno que consiste em um conjunto de transformações de dados e dimensões estendidas criadas especificamente para o serviço de dados. As transformações e dimensões são definidas em [!DNL Transformation Dataset Include] arquivos incluídos no diretório Conjunto de dados do perfil interno. Para obter instruções sobre como instalar o perfil interno do serviço de dados [!DNL IP Geo-location] ou do serviço de [!DNL IP Geo-intelligence] dados, consulte o Guia *do Usuário da Análise de* big data.
