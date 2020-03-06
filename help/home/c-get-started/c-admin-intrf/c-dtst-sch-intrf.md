---
description: A interface do Esquema do Conjunto de Dados exibe as dimensões estendidas (contáveis, simples, muitas para muitas, numéricas, denormal e de tempo) definidas em qualquer arquivo de configuração do conjunto de dados de transformação e fornece uma exibição das relações entre essas dimensões.
solution: Analytics
title: Interface do Esquema de Conjunto de Dados
topic: Data workbench
uuid: 3726e568-d3ea-47f8-8ac4-582c97fbbe0a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Interface do Esquema de Conjunto de Dados{#dataset-schema-interface}

A interface do Esquema do Conjunto de Dados exibe as dimensões estendidas (contáveis, simples, muitas para muitas, numéricas, denormal e de tempo) definidas em qualquer arquivo de configuração do conjunto de dados de transformação e fornece uma exibição das relações entre essas dimensões.

Além disso, a [!DNL Dataset Schema] interface mostra qualquer dimensão derivada que você tenha definido, bem como qualquer dimensão estendida configurada para ser oculta.

![](assets/vis_DatasetSchema_Example2.png)

>[!NOTE]
>
>Você pode pesquisar dimensões no diagrama de esquema. O nome das dimensões encontradas pela string de pesquisa são realçados e as linhas da classe pai mudam de cor para quaisquer ocorrências encontradas nas dimensões secundárias subordinadas. As dimensões contáveis permanecem visíveis à medida que você percorre para fornecer hierarquia e contexto visualizáveis.

**Interpretação de um tipo de dimensão usando a[!DNL Dataset Schema]interface**

A tabela a seguir lista os tipos de dimensão e as cores em que seus nomes aparecem na [!DNL Dataset Schema] interface. Os pais das dimensões de amostra (do exemplo acima) também são anotados.

<table id="table_CF888522626E49A4A10D87085CAB5CC1"> 
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
   <td colname="col3"> <p>Visitante - neste esquema, o Visitante é uma dimensão contável raiz. </p> <p>Sessão - pai é visitante </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2"> Amarelo </td> 
   <td colname="col3"> DenormalPage - parent is Page View </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Derivado </td> 
   <td colname="col2"> Azul  </td> 
   <td colname="col3"> Próxima página - pai é Exibição de página </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Muitos para muitos </td> 
   <td colname="col2"> Rosa e Verde (o origem do pai é rosa, enquanto o nome da dimensão é verde.) </td> 
   <td colname="col3"> Termo de pesquisa - pai é Sessão </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numérico </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Duração exata da página - o pai é a Exibição de página. Neste exemplo, Duração exata da página é uma dimensão numérica oculta. Consulte o tipo de dimensão Oculto nesta tabela. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Simples </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Página - pai é a Exibição de página </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Hora - pai é Sessão </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Dimensões ocultas são uma versão mais escura da cor do tipo de dimensão apropriada. Por exemplo, uma dimensão numérica oculta é um verde mais escuro e menos brilhante. </td> 
   <td colname="col3"> Duração exata da página - o pai é a Exibição de página </td> 
  </tr> 
 </tbody> 
</table>

Para obter mais informações sobre esses tipos de dimensão, consulte o Guia *de Configuração de* Conjunto de Dados.

**Para exibir a visualização padrão de uma dimensão**

* Na [!DNL Dataset Schema] interface, clique na dimensão desejada. A visualização padrão é exibida. Por exemplo, se a visualização padrão for uma tabela que exibe Sessões e a dimensão selecionada e você clicar na dimensão URI, o Análise de big data exibirá uma tabela com URI por Sessões.

   >[!NOTE]
   >
   >Se desejar alterar a visualização padrão que é exibida, consulte [A interface](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175)do esquema de conjunto de dados.

**Para exibir uma visualização específica de uma dimensão**

* Na [!DNL Dataset Schema] interface, clique com o botão direito do mouse na dimensão desejada e clique em **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*.

