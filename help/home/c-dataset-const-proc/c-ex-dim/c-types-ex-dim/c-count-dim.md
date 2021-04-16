---
description: Os elementos de uma dimensão contável podem ser contados pelo sistema.
title: Dimensões contáveis
uuid: 3312f5eb-69b9-43af-b32a-5c40e3050b29
exl-id: c607c15d-de85-4daf-af76-79b460f51b38
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 4%

---

# Dimensões contáveis{#countable-dimensions}

Os elementos de uma dimensão contável podem ser contados pelo sistema.

Normalmente, as dimensões contáveis são usadas para criar métricas de soma, que retornam a contagem ou soma de todos os elementos da dimensão. É possível definir dimensões contáveis para contar instâncias, como reservas ou pedidos de produtos. Por exemplo, você pode definir a dimensão contável Pedidos cujos elementos (entradas de log correspondentes a pedidos da sua loja online) podem ser contados. Se quiser mostrar uma contagem de pedidos em uma visualização, defina a métrica de soma Pedidos , que pode ser avaliada por uma dimensão ou ter filtros aplicados a ela.

As dimensões contáveis podem ser pais de outras dimensões ou filhos de outras dimensões contáveis.

>[!NOTE]
>
>Se você precisar de uma dimensão que forneça apenas uma contagem de algo, deverá usar uma dimensão numérica com uma operação de CONTAGEM. Consulte [Dimension numéricos](../../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed).

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
   <td colname="col2"> Nome descritivo da dimensão, como aparece para o usuário no Data Workbench. O nome da dimensão não pode incluir um hífen (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Observações sobre a dimensão estendida. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição </td> 
   <td colname="col2"> As condições em que o campo de entrada contribui para a criação da dimensão contável. Se especificada, uma condição restringe o conjunto de entradas de log visíveis à dimensão e a todos os seus filhos no esquema do conjunto de dados. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Determina se a dimensão aparece na interface do Data Workbench. Por padrão, esse parâmetro é definido como false. Se, por exemplo, a dimensão for usada apenas como a base de uma métrica, você poderá definir esse parâmetro como true para ocultar a dimensão na exibição do Data Workbench. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chave </td> 
   <td colname="col2"> <p>Opcional. O nome do campo a ser usado como a chave. Se você definir esse parâmetro, um elemento da dimensão contável existe para cada combinação de um elemento do pai da dimensão contável e um valor distinto do campo especificado como a chave. </p> <p> Cada elemento da dimensão contável é necessário para se relacionar a um conjunto contíguo de entradas de log. Portanto, se as entradas de log não forem ordenadas pela chave, um elemento da dimensão contável será criado sempre que o campo principal for alterado. Para evitar essa situação, o Adobe recomenda o uso de uma chave exclusiva que é contígua em ordem de tempo. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pai </td> 
   <td colname="col2"> <p>O nome da dimensão pai. Qualquer dimensão contável pode ser uma dimensão principal. Para tornar uma dimensão a dimensão de nível superior no esquema do conjunto de dados, defina o parâmetro como "raiz". A dimensão definida se torna a dimensão contável raiz do conjunto de dados. Por exemplo, se você estiver trabalhando com Site, a dimensão Visitante será a dimensão contável raiz do seu conjunto de dados. </p> <p> <p>Observação:  Embora sua dimensão contável de raiz não precise ser associada às IDs de rastreamento nos dados, o Adobe recomenda configurar a dimensão contável do conjunto de dados para usar o campo de ID de rastreamento (x-trackingid) como sua Chave. Como resultado, cada elemento da tabela raiz é associado a um valor exclusivo de x-trackingid e todos os dados sobre cada elemento são agrupados. Se quiser configurar seu conjunto de dados de forma diferente, entre em contato com o Adobe. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Este exemplo ilustra a definição de uma dimensão contável usando dados de evento coletados do tráfego do site. A dimensão contável conta os eventos de campanha da Web em uma determinada sessão. A suposição é que todos os recursos da campanha de email sejam solicitados do servidor da Web com &quot;email=&quot; como parte de cs-uri-query. No exemplo, o número de vezes que o visitante responde a uma campanha de email durante uma sessão específica é de interesse, não o valor real do campo cs-uri-query(email) .

![](assets/cfg_Transformation_Dim_Countable.png)

Este exemplo também ilustra a definição de uma dimensão contável usando dados de evento coletados do tráfego do site, mas tem um parâmetro Chave definido. A dimensão contável Sessão usa o campo x-session-key como sua chave. (O campo x-session-key é a saída da transformação [!DNL Sessionize] e tem um valor exclusivo para cada sessão.) Cada combinação exclusiva de um elemento da dimensão Visitante (o pai) e o campo x-session-key é um elemento da dimensão Sessão .

![](assets/cfg_Transformation_Dim_Countable2.png)
