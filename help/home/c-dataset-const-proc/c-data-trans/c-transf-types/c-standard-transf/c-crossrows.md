---
description: Como outras transformações, a transformação CrossRows é aplicada às linhas de dados (entradas de log) nas fontes de log.
title: CrossRows
uuid: 5910c150-6bec-4d98-b116-9b382fd54d3c
exl-id: 321f986e-44a9-454c-9311-0ae37a11a088
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 1%

---

# CrossRows{#crossrows}

Como outras transformações, a transformação CrossRows é aplicada às linhas de dados (entradas de log) nas fontes de log.

Para cada linha de dados, a transformação pega o valor do campo de entrada especificado, executa um conjunto de etapas de processamento e registra o resultado no campo de saída especificado. No entanto, quando a transformação [!DNL CrossRows] funciona em uma linha de dados (essa linha é chamada de linha de saída), leva em conta que a linha mais uma ou mais linhas de dados (essas linhas são chamadas linhas de entrada) que estão associadas à mesma ID de rastreamento. Portanto, para uma determinada ID de rastreamento, o valor do campo de saída para cada linha de saída é baseado nos valores do campo de entrada para uma ou mais linhas de entrada.

A transformação fornece várias condições e restrições que permitem limitar as linhas de entrada da transformação. Você pode expressar esses limites em termos das condições do servidor do Data Workbench (consulte [Conditions](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)), um intervalo de linhas de entrada em relação à linha de saída ou um intervalo de vezes em relação ao tempo da linha de saída. Para essas linhas de entrada que atendem às condições e restrições da transformação, é possível aplicar uma operação (como SUM) que determine o valor do campo de saída.

>[!NOTE]
>
>Para funcionar, a transformação [!DNL CrossRows] exige que os dados sejam solicitados no tempo e agrupados pela ID de rastreamento nos dados de origem. Portanto, [!DNL CrossRows] funciona somente quando definido no arquivo [!DNL Transformation.cfg] ou em um arquivo [!DNL Transformation Dataset Include].

À medida que revisa as descrições dos parâmetros na tabela a seguir, lembre-se do seguinte:

* A linha de saída é a linha de dados na qual a transformação está funcionando em um determinado ponto no tempo.
* As linhas de entrada são todas as outras linhas de dados (antes, depois ou incluindo a linha de saída) cujos valores do campo de entrada servem como entradas para a transformação. As linhas de entrada estão sujeitas aos parâmetros Condição de entrada, Chave, Início da linha, Fim da linha, Início da hora e Fim da hora.

<table id="table_152851484AFF4C50AF736DC62FAA43E3"> 
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
   <td colname="col2"> Limita a saída da transformação a determinadas entradas de log. Se a condição não for atendida para uma entrada de log específica, o campo no parâmetro Saída permanecerá inalterado. A entrada ainda pode ser usada para afetar outras entradas de log. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> O nome do campo da linha de entrada a ser usada como entrada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição de entrada </td> 
   <td colname="col2"> Aceita entrada para a transformação a partir de apenas determinadas linhas de entrada. Se a Condição de entrada não for atendida para uma linha de entrada específica, o campo de entrada dessa linha será ignorado e não afetará outras linhas de saída. No entanto, o campo de saída dessa linha ainda será modificado de acordo com a Condição especificada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chave </td> 
   <td colname="col2"> <p>Opcional. O nome do campo a ser usado como a chave. </p> <p> Se uma chave for especificada, as linhas de entrada de uma determinada linha de saída serão limitadas ao bloco contíguo de linhas com o mesmo valor Chave da linha de saída. Essa restrição é adicional a todas as outras limitações colocadas nas linhas de entrada por outros parâmetros da transformação <span class="wintitle"> CrossRows</span>. </p> <p> Por exemplo, se estiver trabalhando com dados da Web e fizer com que o campo x-session-key (que tem um valor exclusivo para cada sessão) tenha a chave, as linhas de entrada da transformação serão limitadas às linhas que têm o mesmo valor x-session-key que a linha de saída. Portanto, você está considerando apenas as linhas de entrada que representam exibições de página que ocorrem durante a mesma sessão que a linha de saída. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operação </td> 
   <td colname="col2"> <p>Uma operação que, para cada linha de saída, é aplicada a todas as linhas de entrada que satisfaçam todas as condições definidas pelos parâmetros Condição de entrada, Chave, Início da linha, Fim da linha, Início do tempo e Fim do tempo para produzir uma saída: 
     <ul id="ul_C01CCF73A9544BCFB7B1105042FEF2DD"> 
      <li id="li_2D1A192970904499AB9F4431D51106D7"> TODOS pega todos os valores do campo de entrada das linhas de entrada e os gera como um vetor. </li> 
      <li id="li_B8863724AD924DE5BDBC987143548257"> SUM interpreta os valores do campo de entrada das linhas de entrada como números e os soma. </li> 
      <li id="li_BF930069DCEA4E0B80893C3C06CAE100"> A PRIMEIRA LINHA gera o valor do campo de entrada a partir da primeira linha de entrada. </li> 
      <li id="li_04B9E2D88C0847E28101FC830C18D8E2"> A ÚLTIMA LINHA gera o valor do campo de entrada a partir da última linha de entrada. </li> 
     </ul> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Saída </td> 
   <td colname="col2"> O nome do campo de saída. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Início da linha/Término da linha </td> 
   <td colname="col2"> <p>Opcional. Especifica um intervalo de linhas de entrada em relação à linha de saída. Por exemplo, um valor de Início de linha "0" exclui todas as linhas antes da linha de saída. Um valor inicial de linha de "1" também exclui a linha de saída. Intervalos comuns incluem: 
     <ul id="ul_B030F32A5146430BA50DD4FAB4A527B0"> 
      <li id="li_30DFB8C0265349C295943A1CB8077B86"> Início 0: Esta linha e todas as subsequentes. </li> 
      <li id="li_9090C2E94E394351867BC5B78F27B41C"> Início 1: Todas as linhas subsequentes. </li> 
      <li id="li_F870DC913E3F45BA94EE2EC04D344DE0"> Fim 0: Esta linha e todas as anteriores. </li> 
      <li id="li_B8A576E419744D84AB1298E5155B583E"> Fim -1: Todas as linhas anteriores. </li> 
      <li id="li_CD2307A262D34542A2860FF07005CAD7"> Início -1, Fim -1: A linha anterior. </li> 
      <li id="li_6BF30B7BB7CC40A68B2332A3C11DD3B5"> Início 1, Fim 1: A próxima linha. </li> 
     </ul> </p> </td> 
   <td colname="col3"> Todas as linhas </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora de início/hora de término </td> 
   <td colname="col2"> <p>Opcional. Especifica um intervalo de vezes relativo ao tempo da linha de saída. Por exemplo, um Fim de tempo de 30 minutos inclui todas as linhas que ocorrem dentro de 30 minutos após a linha de saída. Um Início de tempo de -30 minutos inclui todas as linhas que ocorrem dentro de 30 minutos antes da linha de saída. </p> <p> As unidades de tempo disponíveis são dias, semanas, horas, minutos, ms (milissegundos), tiques (100 nanossegundos) e ns (nanossegundos). </p> </td> 
   <td colname="col3"> Todas as vezes </td> 
  </tr> 
 </tbody> 
</table>

A transformação [!DNL CrossRows] neste exemplo é aplicada a linhas de dados da Web a serem encontradas para cada exibição de página no momento da próxima exibição de página. Como sabemos que [!DNL CrossRows] é aplicado somente durante a fase de transformação do processo de construção do conjunto de dados, as linhas de dados são solicitadas pelo visitante (cada visitante tem uma ID de rastreamento exclusiva) e pelo tempo.

O campo de entrada, x-timestamp, é considerado apenas para as linhas de entrada nas quais x-is-page-view é preenchido (indicando que a linha de dados representa uma exibição de página). O campo x-session-key (que tem um valor exclusivo para cada sessão) é especificado para o parâmetro Key . Portanto, as linhas de entrada (entradas de log) para a transformação são limitadas ao bloco contíguo de linhas que têm o mesmo valor de x-session-key que a linha de saída. Em outras palavras, para ser considerada para a transformação, uma linha de entrada deve representar uma exibição de página que ocorre durante a mesma sessão que a exibição de página na linha de saída. A primeira operação de linha obtém o valor do campo de saída da primeira linha de entrada que satisfaz a condição [!DNL Input] e tem o mesmo valor de x-session-key que a linha de saída.

![](assets/cfg_TransformationType_CrossRows.png)

[!DNL CrossRows] O é executado em uma quantidade de tempo proporcional ao tamanho de suas entradas mais o tamanho de suas saídas. Isso significa que para as operações SUM, FIRST ROW e LAST ROW, não é menos eficiente do que outras transformações. Para TODOS, a situação é mais complexa porque é possível configurar [!DNL CrossRows] para produzir uma quantidade de dados para cada linha de dados (entrada de log) que é proporcional ao número total de linhas (entradas de log) para uma determinada ID de rastreamento.
