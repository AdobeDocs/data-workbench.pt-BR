---
description: O arquivo de inclusão do conjunto de dados de transformação para um perfil herdado contém parâmetros associados à fase de transformação da construção do conjunto de dados.
title: Arquivos de inclusão do conjunto de dados de transformação
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
exl-id: 58793f82-162a-4d43-aea9-163716c82db6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 3%

---

# Arquivos de inclusão do conjunto de dados de transformação{#transformation-dataset-include-files}

{{eol}}

O arquivo de inclusão do conjunto de dados de transformação para um perfil herdado contém parâmetros associados à fase de transformação da construção do conjunto de dados.

A primeira linha do arquivo define um tipo [!DNL TransformationInclude] que suporta os parâmetros Dimension, Parâmetros, Reprocessar, Estágio e Transformações Estendidos. Todos os outros parâmetros devem ser definidos na variável [!DNL Transformation.cfg] no diretório do conjunto de dados do perfil do conjunto de dados.

Inclusão de parâmetros diferentes de Dimension estendido, Parâmetros, Reprocessar, Estágio e Transformações em um [!DNL Transformation Dataset Include] O arquivo gera erros.

Você pode nomear um [!DNL Transformation Dataset Include] arquivar tudo o que quiser, mas a extensão de arquivo deve ser [!DNL .cfg]. O arquivo deve ser armazenado no *nome de perfil herdado*\Dataset\Transformation diretory. Como os arquivos são carregados recursivamente durante a fase de transformação da construção do conjunto de dados, você pode armazenar a variável [!DNL Transformation Dataset Include] arquivos em qualquer nível dentro do diretório (por exemplo, *nome de perfil herdado*\Dataset\Transformation\*nome da pasta*\*incluir nome do arquivo*.cfg).

>[!NOTE]
>
>Muitos parâmetros de configuração específicos da Web para o Site são definidos em [!DNL Transformation Dataset Include] arquivos. Para obter informações sobre esses parâmetros, consulte [Configurações para dados da Web](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

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
   <td colname="col2"> Opcional. Define as dimensões estendidas. Consulte <a href="../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Dimension estendidas</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parâmetros </td> 
   <td colname="col2"> Opcional. Uma variável que pode ser referenciada em outros parâmetros de configuração. Para obter mais informações, consulte <a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definir parâmetros nos arquivos de inclusão do conjunto de dados</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reprocessar </td> 
   <td colname="col2"> <p>Opcional. Qualquer caractere ou combinação de caracteres pode ser inserida aqui. Alterar esse parâmetro e salvar o arquivo inicia a retransformação dos dados. </p> <p> Para obter informações sobre como reprocessar seus dados, consulte <a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocessamento e retransformação</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fase </td> 
   <td colname="col2"> <p>Opcional. O nome da etapa de processamento que se aplica a essa <span class="wintitle"> Inclusão do conjunto de dados de transformação</span> arquivo. Os estágios de processamento são definidos no parâmetro Estágios da variável <span class="filepath"> Transformation.cfg</span> arquivo. </p> <p> <p>Observação: Quando você especifica um Estágio, o nome do Estágio deve corresponder exatamente ao nome listado no parâmetro Estágios na <span class="filepath"> Transformation.cfg</span> para o perfil do conjunto de dados. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformações </td> 
   <td colname="col2"> Opcional. Define as transformações de dados que precisam ser aplicadas durante a transformação. Para obter informações sobre os tipos de transformação disponíveis, consulte <a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformações de dados</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Para obter descrições dos parâmetros no [!DNL Transformation.cfg] arquivo, consulte [Arquivo de configuração de transformação](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

Lembre-se dos pontos a seguir sempre que estiver trabalhando com [!DNL Transformation Dataset Include] arquivos:

* Alterar qualquer um dos parâmetros neste arquivo requer a retransformação dos dados.
* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]e [!DNL AppendURI] as transformações funcionam somente quando definidas em um [!DNL Transformation Dataset Configuration] arquivo. Para obter informações sobre essas transformações, consulte [Transformações de dados](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

* Você pode adicionar qualquer um dos parâmetros descritos acima à [!DNL Transformation Dataset Include] abrindo e editando o arquivo no Bloco de notas. Quaisquer alterações feitas e salvas serão exibidas quando você reabrir o arquivo no Data Workbench. Ao adicionar um novo parâmetro, use a tecla Space (não a tecla Tab) para recuar dois (2) espaços à direita do nível de cabeçalho anterior.

Se você se inscrever no Adobe [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] serviço de dados, o Adobe fornece um perfil interno que consiste em um conjunto de transformações de dados e dimensões estendidas que são criadas especificamente para o serviço de dados. As transformações e dimensões são definidas em [!DNL Transformation Dataset Include] arquivos incluídos no diretório Dataset do perfil interno. Para obter instruções sobre como instalar o perfil interno do [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] serviço de dados, consulte o *Guia do usuário do Data Workbench*.
