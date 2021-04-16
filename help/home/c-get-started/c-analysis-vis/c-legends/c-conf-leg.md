---
description: As legendas de confiança ajudam a determinar a probabilidade de os números que você está vendo se deverem ao acaso e a entender os possíveis desvios nos dados.
title: Legendas de confiança
uuid: 2559ff7c-6060-4fee-b509-9ae0c3912016
exl-id: 9aab169a-98b8-4e71-b74d-28e385c5c424
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 2%

---

# Legendas de confiança{#confidence-legends}

As legendas de confiança ajudam a determinar a probabilidade de os números que você está vendo se deverem ao acaso e a entender os possíveis desvios nos dados.

Mesmo que você não esteja coletando dados de amostragem, não poderá extrapolar os números de um período ou subconjunto específico para outros períodos ou subconjuntos com confiança total. A legenda de confiança permite explorar a probabilidade de os números se encaixarem em um intervalo específico.

Se você pensar em dados do mundo real como um grande experimento, o mundo real ainda envolve acaso, mesmo quando trabalha com números exatos. Por exemplo, conhecer o número de pessoas que concluíram uma transação entre as 8h e as 12h de uma terça-feira não significa que o mesmo número o fará exatamente na terça-feira seguinte.

A legenda de confiança a seguir exibe detalhes de confiança sobre a métrica de Conversão, enquanto a tabela a seguir fornece mais informações sobre o significado de cada ponto de dados.

![](assets/lgd_ConfidenceLegend.png)

<table id="table_387F22C7EF4E4DE9AD810D3D9204676F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Métrica ou Fórmula </p> </td> 
   <td colname="col2"> <p>O nome da métrica ou expressão da métrica para a qual deseja exibir informações de confiança. Quaisquer seleções feitas em seu espaço de trabalho são refletidas na legenda. Este exemplo exibe detalhes sobre a métrica Conversão . </p> <p>Para obter informações sobre regras de sintaxe para inserir uma expressão, consulte <a href="../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f"> Sintaxe de idioma de consulta</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valor medido </p> </td> 
   <td colname="col2"> <p>O valor dos dados reais coletados. Neste exemplo, a taxa de conversão para a seleção atual é de 2,3%. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Desvio padrão </p> </td> 
   <td colname="col2"> <p>O desvio padrão do valor medido. Neste exemplo, o desvio padrão da taxa de conversão para a seleção atual é de 0,1%. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>O valor "true" </p> </td> 
   <td colname="col2"> <p>A probabilidade de o Valor medido ficar dentro do intervalo listado para cada probabilidade. Neste exemplo, se esse "experimento do mundo real" fosse repetido várias vezes, você poderia ter 90% de certeza de que o Valor medido ficaria entre 2,1% e 2,4%. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Ao analisar os resultados de qualquer cálculo, você deve considerar os seguintes avisos:
>* Os números são estimativas. Se você repetiu os mesmos cálculos com um conjunto de dados diferente, obteria um resultado diferente. Isso é conhecido como variação aleatória.
>* Extrapolações para probabilidades mais altas dependem de uma suposição de normalidade que não é correta para todas as métricas. Portanto, os valores para probabilidade de 99% são menos confiáveis do que os valores para probabilidade de 90%.

>
>
Se precisar de números mais exatos, entre em contato com um especialista em estatísticas.

## Alterar métricas ou fórmulas {#section-7f09ff84c3514f26b78d29294e1f03d9}

* Na legenda de confiança, clique no campo **[!UICONTROL Metric or Formula]** e digite a métrica ou expressão desejada. Para obter as regras da sintaxe da expressão, consulte [Sintaxe da linguagem de consulta](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f).

## Exportar para o Microsoft Excel {#section-f36e2db7273740b7af278f8a2b79d564}

Para obter informações sobre como exportar janelas, consulte [Exportar Dados da Janela](../../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
