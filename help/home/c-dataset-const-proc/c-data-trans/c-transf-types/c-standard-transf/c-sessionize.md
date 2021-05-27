---
description: Se estiver trabalhando com dados coletados do tráfego do site, você pode usar a transformação Sessões para determinar como as sessões são definidas.
title: Sessionize
uuid: c6e2487a-80e5-4e00-b4d4-2ce013fac3ea
exl-id: bb25cb4b-7185-4524-8ff5-740b672e1cd9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---

# Sessionize{#sessionize}

Se estiver trabalhando com dados coletados do tráfego do site, você pode usar a transformação Sessões para determinar como as sessões são definidas.

A transformação assume como entrada um carimbo de data e hora e uma ID de rastreamento e gera um número de sessão para cada entrada de log. O número da sessão é &quot;1&quot; para a primeira sessão com uma determinada ID de rastreamento, &quot;2&quot; para a segunda sessão com a mesma ID de rastreamento e assim por diante. A saída pode ser usada diretamente como uma chave de sessão, pois tem um valor exclusivo para cada sessão.

>[!NOTE]
>
>Para funcionar, a transformação [!DNL Sessionize] exige que os dados sejam solicitados no tempo e agrupados pela ID de rastreamento nos dados de origem. Portanto, [!DNL Sessionize] funciona somente quando definido no arquivo [!DNL Transformation.cfg] ou em um arquivo [!DNL Transformation Dataset Include].

<table id="table_34984DF9340149C0A5016F08EABAD158"> 
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
   <td colname="col2"> Nome descritivo da transformação. Você pode inserir qualquer nome aqui. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Observações sobre a transformação. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição </td> 
   <td colname="col2"> Condições de aplicação desta transformação. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Carimbo de data e hora de entrada </td> 
   <td colname="col2"> O campo que contém os valores do carimbo de data e hora que será usado. </td> 
   <td colname="col3"> x-timestamp </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de rastreamento de entrada </td> 
   <td colname="col2"> <p>O campo que contém os valores da ID de rastreamento a ser usada. O valor deve ser de 64 bits (16 dígitos) ou um número hexadecimal menor ou um número inteiro decimal de 16 dígitos ou menos. </p> <p> <p>Observação: Se quiser usar um campo diferente de x-trackingid para a ID de rastreamento, será necessário executar hash primeiro no campo . Consulte <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-hash.md#concept-9c353923264941c3aea4428fed66d369"> Hash</a>. </p> </p> </td> 
   <td colname="col3"> x-trackingid </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Duração máxima da sessão </p> </td> 
   <td colname="col2">A duração mais longa da sessão antes de iniciar uma nova sessão. (Isso mantém as páginas da Web que têm atualização automática de conteúdo da criação de sessões que são arbitrariamente longas.) Se a <span class="wintitle"> Condição de tempo limite</span> for satisfeita e o referenciador de um clique for definido como uma das entradas no parâmetro Domínios internos, a Duração máxima da sessão será usada para definir o fim de uma sessão. Nenhuma sessão pode ser maior do que a Duração máxima da sessão especificada, independentemente de quantos cliques ela contém. O valor recomendado é de 48 horas. Para obter mais informações sobre os parâmetros Duração máxima da sessão e Domínios internos, consulte <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> Configurações para dados da Web</a>. </td> 
   <td colname="col3"> 48 horas </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Número da sessão de saída </td> 
   <td colname="col2"> O campo no qual o número de sessão é armazenado. Este campo tem um valor exclusivo para cada sessão de cada visitante. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tempo limite da sessão </td> 
   <td colname="col2"> <p>O tempo que precisa passar entre as entradas de log de um determinado visitante para determinar o fim de uma sessão e o início de uma nova sessão (ou seja, o tempo limite típico usado para definir uma sessão de usuário). O valor recomendado desse parâmetro é de 30 minutos. Se a Condição de tempo limite não for satisfeita e o referenciador de um clique não estiver definido como um dos referenciadores no parâmetro Domínios internos, o Tempo limite da sessão será usado para definir a sessão. </p> <p> Se a Condição de tempo limite for satisfeita e cs (referrer-domain) para uma entrada de log estiver na lista de domínios internos, a Duração máxima da sessão determinará se a entrada de log atual faz parte de uma sessão existente ou se o início de uma nova sessão. </p> <p> Para obter mais informações sobre o parâmetro Tempo limite da sessão, consulte <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> Configurações para Dados da Web</a>. </p> </td> 
   <td colname="col3"> 30 minutos </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição de tempo limite </td> 
   <td colname="col2"> A condição que deve ser atendida para que uma entrada de log seja considerada o início de uma nova sessão. Observe que o tempo decorrido entre a entrada de log e a entrada de log anterior deve ser pelo menos o valor do parâmetro Tempo limite da sessão . </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Uma nova sessão começa quando qualquer uma das seguintes situações ocorre:

* A ID de rastreamento muda.
* O tempo desde a última entrada de log é pelo menos igual ao valor do parâmetro Tempo Limite da Sessão e a Condição de Tempo Limite é atendida.
* O tempo desde a primeira entrada de log da última sessão excede o valor do parâmetro Duração máxima da sessão.

>[!NOTE]
>
>Se você já tiver definido a Duração máxima da sessão e o Tempo limite da sessão como parâmetros no arquivo [!DNL Session Parameters.cfg], não insira valores para eles na configuração. Você pode fazer referência aos parâmetros digitando *$(nome do parâmetro)* como mostrado no exemplo a seguir. Para obter mais informações sobre esses parâmetros, consulte [Configurações para Dados da Web](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

A transformação [!DNL Sessionize] neste exemplo assume como entrada os campos x-timestamp e x-trackingid e registra o número da sessão para cada entrada de log no campo x-session-key . O [!DNL Timeout Condition] da transformação é baseado em uma condição [!DNL Neither]: Se o campo cs(referrer-domain) de uma entrada de log corresponder a um membro do parâmetro Domínios internos , a condição será avaliada como false. Observe as referências aos parâmetros de Domínios internos e Tempo limite da sessão.

Para obter informações sobre [!DNL NeitherCondition], consulte [Condições](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md). Para obter informações sobre os parâmetros de Domínios internos e Tempo limite da sessão, consulte [Configurações para dados da Web](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

![](assets/cfg_TransformationType_Sessionize.png)
