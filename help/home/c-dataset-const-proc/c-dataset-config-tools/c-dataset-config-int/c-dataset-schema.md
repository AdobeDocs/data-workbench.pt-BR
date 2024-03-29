---
description: A interface do Esquema do conjunto de dados exibe as dimensões estendidas (contáveis, simples, muitas para muitas, numéricas, denormal e de tempo) definidas em qualquer arquivo de Configuração do conjunto de dados de transformação e as relações entre essas dimensões.
title: Esquema do conjunto de dados
uuid: 4ef5f14b-dc19-4118-a2f2-d680ded8092c
exl-id: b80e6e8e-9147-46ec-8602-2d7e5d33f077
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 3%

---

# Esquema do conjunto de dados{#dataset-schema}

{{eol}}

A interface do Esquema do conjunto de dados exibe as dimensões estendidas (contáveis, simples, muitas para muitas, numéricas, denormal e de tempo) definidas em qualquer arquivo de Configuração do conjunto de dados de transformação e as relações entre essas dimensões.

Além disso, a variável [!DNL Dataset Schema] A interface do mostra qualquer dimensão derivada que você tenha definido, bem como qualquer dimensão estendida que esteja configurada para ser oculta.

![](assets/vis_DatasetSchema_Example.png)

Esta seção discute os seguintes tópicos:

* [Para interpretar o tipo de dimensão usando a interface Esquema do conjunto de dados](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-16a0a12b11334c07bec558c0b7d260b1)
* [Para exibir a visualização padrão de uma dimensão](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-1bbb73a5cbb34ffb844eb1932db85318)
* [Para exibir uma visualização específica de uma dimensão](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-d46626df90bc4c44ae60c4b71eaeac7f)

## Interpretação do tipo de Dimension usando a interface do esquema do conjunto de dados {#section-16a0a12b11334c07bec558c0b7d260b1}

A tabela a seguir lista os tipos de dimensão e as cores em que seus nomes aparecem no [!DNL Dataset Schema] interface. Os pais das dimensões de amostra (do exemplo acima) também são anotados.

<table id="table_20D1A9EAAED247338476C475C63255F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de Dimension </th> 
   <th colname="col2" class="entry"> Cor do canal </th> 
   <th colname="col3" class="entry"> Dimension e Pai de exemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Contável </td> 
   <td colname="col2"> Rosa </td> 
   <td colname="col3"> <p>Visitante - Nesse esquema, Visitante é uma dimensão contável raiz. </p> <p> Sessão - principal é Visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2"> Amarelo </td> 
   <td colname="col3"> DenormalPage - principal é Exibição de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Derivado </td> 
   <td colname="col2"> Azul </td> 
   <td colname="col3"> Próxima página - o pai é a Visualização de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Muitas para muitas </td> 
   <td colname="col2"> Rosa e Verde (o tronco do pai é rosa, enquanto o nome da dimensão é verde.) </td> 
   <td colname="col3"> Termo de pesquisa - principal é Sessão. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numérico </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Duração exata da página - principal é Exibição de página Neste exemplo, Duração exata da página é uma dimensão numérica oculta. Consulte o tipo de dimensão Oculto nesta tabela. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Simples </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Página - principal é Exibição de página . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Hora - o pai é Sessão. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> As dimensões ocultas são uma versão mais escura da cor de tipo de dimensão apropriada. Por exemplo, uma dimensão numérica oculta é um verde mais escuro e menos brilhante. </td> 
   <td colname="col3"> Duração exata da página - o pai é a Exibição de página. </td> 
  </tr> 
 </tbody> 
</table>

## Para exibir a visualização padrão de um Dimension {#section-1bbb73a5cbb34ffb844eb1932db85318}

* No [!DNL Dataset Schema] , clique na dimensão desejada. A visualização padrão é exibida. Por exemplo, se a visualização padrão for uma tabela que exibe Sessões e a dimensão selecionada, e você clicar na dimensão URI, o Data Workbench exibirá uma tabela com URI por Sessões.

>[!NOTE]
>
>Se desejar alterar a visualização padrão exibida, consulte o capítulo Configuração da interface e recursos de análise na *Guia do usuário do Data Workbench*.

## Para exibir uma visualização específica de um Dimension {#section-d46626df90bc4c44ae60c4b71eaeac7f}

* No [!DNL Dataset Schema] clique com o botão direito do mouse na dimensão desejada e clique em **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*.
