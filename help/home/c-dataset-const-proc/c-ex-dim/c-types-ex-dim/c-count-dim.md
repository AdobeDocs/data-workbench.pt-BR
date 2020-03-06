---
description: Os elementos de uma dimensão contável podem ser contados pelo sistema.
solution: Analytics
title: Dimensões contáveis
topic: Data workbench
uuid: 3312f5eb-69b9-43af-b32a-5c40e3050b29
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensões contáveis{#countable-dimensions}

Os elementos de uma dimensão contável podem ser contados pelo sistema.

Normalmente, as dimensões contáveis são usadas para criar métricas de soma, que retornam a contagem, ou soma, de todos os elementos da dimensão. É possível definir dimensões contáveis para contar instâncias como reservas ou pedidos de produtos. Por exemplo, você pode definir a dimensão contável Pedidos cujos elementos (entradas de log correspondentes a pedidos da sua loja online) podem ser contados. Se você quiser mostrar uma contagem de ordens em uma visualização, defina a métrica Soma de pedidos, que pode ser avaliada em uma dimensão ou ter filtros aplicados a ela.

As dimensões contáveis podem ser pais de outras dimensões ou filhos de outras dimensões contáveis.

>[!NOTE]
>
>Se você precisar de uma dimensão que forneça apenas uma contagem de algo, deverá usar uma dimensão numérica com uma operação de COUNT. Consulte Dimensões [numéricas](../../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed).

As dimensões contáveis são definidas pelos seguintes parâmetros:

<table id="table_9F3F093F5B074EA68CA4DCE731161F6C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Nome descritivo da dimensão como aparece para o usuário na análise de big data. O nome da dimensão não pode incluir um hífen (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Notas sobre a dimensão estendida. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição </td> 
   <td colname="col2"> As condições em que o campo de entrada contribui para a criação da dimensão contável. Se especificada, uma condição restringe o conjunto de entradas de log visíveis à dimensão e a todos os seus filhos no esquema do conjunto de dados. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Determina se a dimensão aparece na interface da análise de big data. Por padrão, esse parâmetro é definido como false. Se, por exemplo, a dimensão for usada apenas como base de uma métrica, você poderá definir esse parâmetro como verdadeiro para ocultar a dimensão da exibição da análise de big data. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chave </td> 
   <td colname="col2"> <p>Opcional. O nome do campo a ser usado como a chave. Se você definir esse parâmetro, um elemento da dimensão contável existe para cada combinação de um elemento do pai da dimensão contável e um valor distinto do campo especificado como a chave. </p> <p> Cada elemento da dimensão contável é necessário para relacionar-se a um conjunto contíguo de entradas de log. Portanto, se as entradas de log não forem ordenadas pela chave, um elemento da dimensão contável será criado sempre que o campo chave for alterado. Para evitar essa situação, a Adobe recomenda que você use uma chave exclusiva que seja contígua em ordem de tempo. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pai </td> 
   <td colname="col2"> <p>O nome da dimensão pai. Qualquer dimensão contável pode ser uma dimensão pai. Para tornar uma dimensão a dimensão de nível superior no esquema do conjunto de dados, defina o parâmetro como "raiz". A dimensão definida se torna a dimensão contável raiz do conjunto de dados. Por exemplo, se você estiver trabalhando com o Site, a dimensão Visitante será a dimensão contável raiz do conjunto de dados. </p> <p> <p>Observação:  Embora sua dimensão contável raiz não precise ser associada às IDs de rastreamento nos dados, a Adobe recomenda que você configure a dimensão contável raiz do conjunto de dados para usar o campo de ID de rastreamento (x-trackingid) como sua Chave. Como resultado, cada elemento da contagem raiz é associado a um valor exclusivo de x-trackingid, e todos os dados sobre cada elemento são agrupados. Se você quiser configurar seu conjunto de dados de forma diferente, entre em contato com a Adobe. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Este exemplo ilustra a definição de uma dimensão contável usando dados de evento coletados do tráfego do site. A dimensão contável conta os eventos de campanha da Web em uma determinada sessão. Supõe-se que todos os recursos de campanha por email sejam solicitados ao servidor da Web com &quot;email=&quot; como parte da consulta cs-uri. No exemplo, o número de vezes que o visitante responde a uma campanha de email durante uma sessão específica é de interesse, não o valor real do campo cs-uri-query(email).

![](assets/cfg_Transformation_Dim_Countable.png)

Este exemplo também ilustra a definição de uma dimensão contável usando dados de evento coletados do tráfego do site, mas tem um parâmetro Chave definido. A dimensão contável Sessão usa o campo x-session-key como sua chave. (O campo x-session-key é a saída da [!DNL Sessionize] transformação e tem um valor exclusivo para cada sessão.) Cada combinação exclusiva de um elemento da dimensão Visitante (o pai) e do campo chave x-session é um elemento da dimensão Sessão.

![](assets/cfg_Transformation_Dim_Countable2.png)

