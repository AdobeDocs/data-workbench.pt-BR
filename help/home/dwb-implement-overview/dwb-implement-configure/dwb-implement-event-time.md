---
description: Esta seção explica como criar carimbos de data e hora para um conjunto de dados do Análise de big data.
title: Configuração da hora do evento
uuid: 0230154d-05a2-44cf-9456-0a27e55f58ef
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuração da hora do evento{#setting-up-event-time}

Esta seção explica como criar carimbos de data e hora para um conjunto de dados do Análise de big data.

## Noções Gerais da Hora do Evento {#section-e10ef2b5b6244dc5b215836e3c77d663}

Hora do evento é a data e a hora em que a solicitação (ou evento) ocorre.

Geralmente, para dados online, *x_hit_time_gmt* é usado como campo de carimbo de data e hora. A hora da chamada pode ser usada como carimbo de data e hora para dados offline (como dados da central de atendimento). Este é um campo obrigatório e todas as fontes de dados devem ter um campo nele que possa ser usado como carimbo de data e hora. Essas informações devem ser fornecidas pela sua organização.

No DWB, as seguintes variáveis predefinidas capturam o carimbo de data e hora:

<table id="table_C24BD56CEB4E42F68D645EBB65585D16"> 
 <tbody> 
  <tr> 
   <td colname="col1"><i>x-timestamp</i> </td> 
   <td colname="col2"> <p> A data e a hora (GMT) em que a solicitação foi recebida pelo servidor. O tempo é expresso como o número de 100 nanossegundos desde 1º de janeiro de 1600. </p> <p>Exemplo: 127710989320000000 seria o valor <i>x-timestamp</i> para 11:28:52.0000000 na terça-feira, 13 de setembro de 2005. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-timestring</i> </td> 
   <td colname="col2"> <i>x-timestamp</i> no formato AAAA-MM-DD HH:MM:SS.mmm. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-unixtime</i> </td> 
   <td colname="col2"> <i>x-unixtime</i> é o tempo epoc que representa o número de segundos desde 1º de janeiro de 1970, às 00:00:01. </td> 
  </tr> 
 </tbody> 
</table>

Com base no formato do campo de data, é usado x-timestamp ou x-unixtime ou x-timestring. Por exemplo, se os dados recebidos estiverem no formato AAAA-MM-DD, então x-timestring será usado.

O carimbo de data e hora é definido em um dos formatos e o DWB gera internamente os outros dois formatos. Além disso, esses são campos DWB predefinidos e o mesmo nome não deve ser usado para nenhum outro campo.

## Fusos horários definidos em DWB {#section-3cdd12254342442b917376661e1d9c9f}

Se o campo de data contiver qualquer um dos fusos horários mencionados abaixo, o DWB considerará a linha inteira nesse fuso horário específico. Por exemplo, um arquivo tem a data definida como 2015-01-01 00:00:00 gmte outro arquivo tem o valor como 2015-01-01 00:00:00 cst, então a data do primeiro arquivo será considerada no fuso horário GMT enquanto a data do segundo arquivo estará em Fuso horário CST.

| Código | Fuso Horário |
|---|---|
| gmt | Greenwich Mean |
| est | Padrão oriental |
| edt | Horário de Verão Oriental |
| custo | Padrão Central |
| cdt | Luz de Verão Central |
| mst | Padrão de Montanha |
| mdt | Hora de Verão das Montanhas |
| pst | Padrão do Pacífico |
| pdt | Horário de Verão do Pacífico |

>[!NOTE]
>
>O DWB processa somente os Fusos horários mencionados acima.

## Configuração de fusos horários personalizados {#section-7c351921f22b439b81c73f40d5b47536}

O DWB não processa o deslocamento no Fuso horário. Para considerar o deslocamento em Fuso horário, os dados devem ser formatados nesse fuso horário de deslocamento.

Exemplo: para considerar o formato de data no fuso horário CST, os dados devem vir no formato AAAA-MM-DD HH:MM:SS UTC +/-HHMM do cliente.

2015-10-18 05:00:00 UTC -0200

## Como definir a Hora/Carimbo de data e hora do evento {#section-81507080f0b44ae6b83d3650ba019812}

Com base no formato do campo de data, a variável *x-timestamp, x-unixtime* ou *x-timestring* é usada. No exemplo abaixo, como *x-hit_time_gmt* vem no formato epoc único, *x-unixtime* é usado.

No [!DNL foundation.cfg] arquivo DWB (ou em qualquer outro arquivo de configuração na pasta de processamento de log do Conjunto de dados), use a transformação Copiar para definir a Hora do evento como mostrado:

Com base no formato do campo de data, a variável x-timestamp, x-unixtime ou x-timestring é usada. No exemplo abaixo, como x-hit_time_gmt vem no formato epoc unix, x-unixtime é usado.

No insight foundation.cfg (ou qualquer outra configuração na pasta de processamento de log Datasetà), use a transformação Copiar para definir a Hora do evento, como mostrado abaixo: ![](assets/dwb_impl_timestamp1.png)

Se a data em estiver no formato AAAA-MM-DD HH:MM:SS.mmm, x-timestring será usado. ![](assets/dwb_impl_timestamp2.png)Exemplo: Se o campo de data estiver no formato diferente do definido no DWB, diga AAAA/MM/DD, formate-o primeiro em um dos formatos de carimbo de data e hora aceitos pelo DWB e atribua-o à variável correspondente. Na captura de tela abaixo, a data é convertida primeiro no formato AAAA-MM-DD e, em seguida, atribuída à variável *x-timestring *. ![](assets/dwb_impl_timestamp3.png)

