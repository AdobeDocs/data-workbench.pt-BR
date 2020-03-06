---
description: A interface do Esquema do Conjunto de Dados exibe as dimensões estendidas (contáveis, simples, muitas para muitas, numéricas, denormal e de tempo) definidas em qualquer arquivo de Configuração do Conjunto de Dados de Transformação e as relações entre essas dimensões.
solution: Analytics
title: Esquema de conjunto de dados
topic: Data workbench
uuid: 4ef5f14b-dc19-4118-a2f2-d680ded8092c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Esquema de conjunto de dados{#dataset-schema}

A interface do Esquema do Conjunto de Dados exibe as dimensões estendidas (contáveis, simples, muitas para muitas, numéricas, denormal e de tempo) definidas em qualquer arquivo de Configuração do Conjunto de Dados de Transformação e as relações entre essas dimensões.

Além disso, a [!DNL Dataset Schema] interface mostra qualquer dimensão derivada que você tenha definido, bem como qualquer dimensão estendida configurada para ser oculta.

![](assets/vis_DatasetSchema_Example.png)

Esta seção discute os seguintes tópicos:

* [Para interpretar o tipo de dimensão usando a interface do Esquema de Conjunto de Dados](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-16a0a12b11334c07bec558c0b7d260b1)
* [Para exibir a visualização padrão de uma dimensão](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-1bbb73a5cbb34ffb844eb1932db85318)
* [Para exibir uma visualização específica de uma dimensão](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-d46626df90bc4c44ae60c4b71eaeac7f)

## Interpretação do tipo de dimensão usando a interface do esquema de conjunto de dados {#section-16a0a12b11334c07bec558c0b7d260b1}

A tabela a seguir lista os tipos de dimensão e as cores em que seus nomes aparecem na [!DNL Dataset Schema] interface. Os pais das dimensões de amostra (do exemplo acima) também são anotados.

<table id="table_20D1A9EAAED247338476C475C63255F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de dimensão </th> 
   <th colname="col2" class="entry"> Cor do canal </th> 
   <th colname="col3" class="entry"> Dimensão de amostra e pai </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Contável </td> 
   <td colname="col2"> Rosa </td> 
   <td colname="col3"> <p>Visitante - neste esquema, o Visitante é uma dimensão contável raiz. </p> <p> Sessão - o pai é Visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2"> Amarelo </td> 
   <td colname="col3"> DenormalPage - parent é Page View. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Derivado </td> 
   <td colname="col2"> Azul  </td> 
   <td colname="col3"> Próxima página - o pai é a Exibição de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Muitos para muitos </td> 
   <td colname="col2"> Rosa e Verde (o origem do pai é rosa, enquanto o nome da dimensão é verde.) </td> 
   <td colname="col3"> Termo de pesquisa - o pai é Sessão. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numérico </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Duração exata da página - o pai é Exibição de página Neste exemplo, Duração exata da página é uma dimensão numérica oculta. Consulte o tipo de dimensão Oculto nesta tabela. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Simples </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Página - pai é Exibição de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Hora - o pai é a Sessão. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Dimensões ocultas são uma versão mais escura da cor do tipo de dimensão apropriada. Por exemplo, uma dimensão numérica oculta é um verde mais escuro e menos brilhante. </td> 
   <td colname="col3"> Duração exata da página - o pai é a Exibição de página. </td> 
  </tr> 
 </tbody> 
</table>

## Para exibir a visualização padrão de uma dimensão {#section-1bbb73a5cbb34ffb844eb1932db85318}

* Na [!DNL Dataset Schema] interface, clique na dimensão desejada. A visualização padrão é exibida. Por exemplo, se a visualização padrão for uma tabela que exibe Sessões e a dimensão selecionada, e você clicar na dimensão URI, a análise de big data exibirá uma tabela com URI por Sessões.

>[!NOTE]
>
>Se você quiser alterar a visualização padrão que é exibida, consulte o capítulo Configuração de recursos de interface e análise no Guia *do usuário do* Análise de big data.

## Para Exibir uma Visualização Específica de uma Dimensão {#section-d46626df90bc4c44ae60c4b71eaeac7f}

* Na [!DNL Dataset Schema] interface, clique com o botão direito do mouse na dimensão desejada e clique em **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*.

