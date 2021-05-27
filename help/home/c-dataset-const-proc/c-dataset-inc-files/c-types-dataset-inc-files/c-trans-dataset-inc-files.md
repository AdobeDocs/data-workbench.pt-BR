---
description: O arquivo de inclusão do conjunto de dados de transformação para um perfil herdado contém parâmetros associados à fase de transformação da construção do conjunto de dados.
title: Arquivos de inclusão do conjunto de dados de transformação
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
exl-id: 58793f82-162a-4d43-aea9-163716c82db6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 3%

---

# Arquivos de inclusão do conjunto de dados de transformação{#transformation-dataset-include-files}

O arquivo de inclusão do conjunto de dados de transformação para um perfil herdado contém parâmetros associados à fase de transformação da construção do conjunto de dados.

A primeira linha do arquivo define um tipo [!DNL TransformationInclude] que suporta os parâmetros Dimension, Parâmetros, Reprocessamento, Estágio e Transformações Estendidos. Todos os outros parâmetros devem ser definidos no arquivo [!DNL Transformation.cfg] no diretório do conjunto de dados do perfil do conjunto de dados.

A inclusão de parâmetros diferentes de Dimension estendido, Parâmetros, Reprocessar, Estágio e Transformações em um arquivo [!DNL Transformation Dataset Include] gera erros.

Você pode nomear um arquivo [!DNL Transformation Dataset Include] o que desejar, mas sua extensão de arquivo deve ser [!DNL .cfg]. O arquivo deve ser armazenado dentro do *nome de perfil herdado*\Dataset\Transformation directory. Como os arquivos são carregados recursivamente durante a fase de transformação da construção do conjunto de dados, você pode armazenar os arquivos [!DNL Transformation Dataset Include] em qualquer nível dentro do diretório (por exemplo, *nome de perfil herdado*\Dataset\Transformation\*nome da pasta*\*incluir nome de arquivo*.cfg).

>[!NOTE]
>
>Muitos parâmetros de configuração específicos da Web para o Site são definidos em [!DNL Transformation Dataset Include] arquivos. Para obter informações sobre esses parâmetros, consulte [Configurações para Dados da Web](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

A tabela a seguir descreve os parâmetros que estão disponíveis em um arquivo [!DNL Transformation Dataset Include] :

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
   <td colname="col2"> Opcional. Define as dimensões estendidas. Consulte <a href="../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Dimension estendido</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parâmetros </td> 
   <td colname="col2"> Opcional. Uma variável que pode ser referenciada em outros parâmetros de configuração. Para obter mais informações, consulte <a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definindo Parâmetros nos Arquivos de Inclusão do Conjunto de Dados</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reprocessar </td> 
   <td colname="col2"> <p>Opcional. Qualquer caractere ou combinação de caracteres pode ser inserida aqui. Alterar esse parâmetro e salvar o arquivo inicia a retransformação dos dados. </p> <p> Para obter informações sobre como reprocessar seus dados, consulte <a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocessando e Retransformação</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fase </td> 
   <td colname="col2"> <p>Opcional. O nome da etapa de processamento que se aplica a esse arquivo <span class="wintitle"> de Inclusão do Conjunto de Dados de Transformação</span>. Os estágios de processamento são definidos no parâmetro Estágios no arquivo <span class="filepath"> Transformation.cfg</span>. </p> <p> <p>Observação: Quando você especifica um Estágio, o nome do Estágio deve corresponder exatamente ao nome listado no parâmetro Estágios no arquivo <span class="filepath"> Transformation.cfg</span> para o perfil do conjunto de dados. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformações </td> 
   <td colname="col2"> Opcional. Define as transformações de dados que precisam ser aplicadas durante a transformação. Para obter informações sobre os tipos de transformação disponíveis, consulte <a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformações de dados</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Para obter descrições dos parâmetros no arquivo [!DNL Transformation.cfg], consulte [Arquivo de configuração de transformação](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

Lembre-se dos pontos a seguir sempre que estiver trabalhando com arquivos [!DNL Transformation Dataset Include]:

* Alterar qualquer um dos parâmetros neste arquivo requer a retransformação dos dados.
* [!DNL CrossRows]As  [!DNL ODBCLookup]transformações,  [!DNL Sessionize],  [!DNL AppendURI]  e funcionam somente quando definidas em um  [!DNL Transformation Dataset Configuration] arquivo. Para obter informações sobre essas transformações, consulte [Transformações de dados](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

* Você pode adicionar qualquer um dos parâmetros descritos acima ao arquivo [!DNL Transformation Dataset Include] abrindo e editando o arquivo no Bloco de notas. Quaisquer alterações feitas e salvas serão exibidas quando você reabrir o arquivo no Data Workbench. Ao adicionar um novo parâmetro, use a tecla Space (não a tecla Tab) para recuar dois (2) espaços à direita do nível de cabeçalho anterior.

Se você assinar o serviço de dados [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] do Adobe, o Adobe fornece um perfil interno que consiste em um conjunto de transformações de dados e dimensões estendidas que são criadas especificamente para o serviço de dados. As transformações e dimensões são definidas em [!DNL Transformation Dataset Include] arquivos que estão incluídos no diretório Conjunto de dados do perfil interno. Para obter instruções para instalar o perfil interno do serviço de dados [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence], consulte o *Guia do Usuário do Data Workbench*.
