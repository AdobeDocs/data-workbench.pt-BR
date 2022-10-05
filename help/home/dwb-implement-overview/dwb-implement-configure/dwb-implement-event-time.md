---
description: Esta seção explica como criar carimbos de data e hora para um conjunto de dados do Data Workbench.
title: Configurar tempo do evento
uuid: 0230154d-05a2-44cf-9456-0a27e55f58ef
exl-id: 9632e713-5cf9-4acf-aafa-bfdf79a51ad9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 2%

---

# Configurar tempo do evento{#setting-up-event-time}

{{eol}}

Esta seção explica como criar carimbos de data e hora para um conjunto de dados do Data Workbench.

## Noções básicas sobre o tempo do evento {#section-e10ef2b5b6244dc5b215836e3c77d663}

Hora do evento é a data e a hora em que a solicitação (ou evento) ocorre.

Geralmente, para dados online, *x_hit_time_gmt* é usada como campo de carimbo de data e hora. A hora da chamada pode ser usada como carimbo de data e hora para dados offline (como dados da central de atendimento). Este é um campo obrigatório e todas as fontes de dados devem ter um campo nele que possa ser usado como carimbo de data e hora. Essas informações devem ser fornecidas pela organização.

No DWB, as seguintes variáveis predefinidas capturam o carimbo de data e hora:

<table id="table_C24BD56CEB4E42F68D645EBB65585D16"> 
 <tbody> 
  <tr> 
   <td colname="col1"><i>x-timestamp</i> </td> 
   <td colname="col2"> <p> A data e a hora (GMT) em que a solicitação foi recebida pelo servidor. O tempo é expresso como o número de 100 nanossegundos desde 1º de janeiro de 1600. </p> <p>Exemplo: 127710989320000000 seria o <i>x-timestamp</i> valor para 11:28:52.000000 na terça-feira, 13 de setembro de 2005. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-timestring</i> </td> 
   <td colname="col2"> <i>x-timestamp</i> no formato AAAA-MM-DD HH:MM:SS.mmm </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-unixtime</i> </td> 
   <td colname="col2"> <i>x-unixtime</i> é o tempo epoc que representa o número de segundos desde 1º de janeiro de 1970, em 00:00:01. </td> 
  </tr> 
 </tbody> 
</table>

Com base no formato do campo de data, x-timestamp ou x-unixtime ou x-timestring é usado. Por exemplo, se os dados recebidos estiverem no formato AAA-MM-DD, então x-timestring será usado.

O carimbo de data e hora é definido em um dos formatos e o DWB gera internamente os outros dois formatos. Além disso, esses são campos DWB predefinidos e o mesmo nome não deve ser usado para nenhum outro campo.

## Fusos horários definidos no DWB {#section-3cdd12254342442b917376661e1d9c9f}

Se o campo de data contiver qualquer um dos fusos horários mencionados abaixo, o DWB considerará a linha inteira nesse fuso horário específico. Por exemplo, um arquivo tem a data definida como 2015-01-01 00:00:00 gmtand outro arquivo tem o valor como 2015-01-01 00:00:00 custo, a data do primeiro arquivo será considerada no fuso horário GMT, enquanto a data do segundo arquivo estará no fuso horário CST.

| Código | Fuso horário |
|---|---|
| gmt | Greenwich Mean |
| est | Padrão oriental |
| edt | Horário de Verão do Leste |
| cst | Padrão central |
| cdt | Horário de Verão Central |
| mst | Padrão das Montanhas |
| mdt | Hora de Verão das Montanhas |
| pst | Padrão do Pacífico |
| pdt | Horário de Verão do Pacífico |

>[!NOTE]
>
>O DWB processa apenas os Fusos horários mencionados acima.

## Configuração de fusos horários personalizados {#section-7c351921f22b439b81c73f40d5b47536}

O DWB não processa o deslocamento no Fuso horário. Para considerar o deslocamento em Fuso Horário, os dados devem ser formatados nesse fuso horário deslocado.

Exemplo: para considerar o formato de data no fuso horário CST, os dados devem vir em AAAA-MM-DD HH:MM:Formato SS UTC +/-HMM do cliente.

2015-10-18 05:00:00 UTC -0200

## Como definir a Hora do evento/Carimbo de data e hora {#section-81507080f0b44ae6b83d3650ba019812}

Com base no formato do campo de data, *x-timestamp, x-unixtime* ou *x-timestring* é usada. No exemplo abaixo, já que a variável *x-hit_time_gmt* vem no formato unix epoc, *x-unixtime* é usada.

No DWB [!DNL foundation.cfg] (ou qualquer outro arquivo de configuração na pasta de processamento de log do conjunto de dados), use a transformação Copiar para definir a Hora do evento como mostrado:

Com base no formato do campo de data, é usada a variável x-timestamp, x-unixtime ou x-timestring. No exemplo abaixo, como x-hit_time_gmt vem no formato de epoc unix, x-unixtime é usado.

No insight foundation.cfg (ou qualquer outra configuração na pasta de processamento de log do Datasetà), use a transformação Copiar para definir o Tempo do evento como mostrado abaixo: ![](assets/dwb_impl_timestamp1.png)

Se a data em for AAAA-MM-DD HH:MM:Formato SS.mmm, x-timestring é usado. ![](assets/dwb_impl_timestamp2.png)Exemplo: Se o campo de data estiver no formato diferente do definido em DWB, digamos AAAA/MM/DD, primeiro formate-o em um dos formatos de carimbo de data e hora aceitos pelo DWB e depois o atribua à variável correspondente. Na captura de tela abaixo, a data é convertida primeiro em formato AAAA-MM-DD e, em seguida, atribuída à variável *x-timestring *. ![](assets/dwb_impl_timestamp3.png)
