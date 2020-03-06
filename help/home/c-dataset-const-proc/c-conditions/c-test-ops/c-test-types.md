---
description: A condição Comparar e a condição Intervalo exigem que você especifique o tipo de comparação a ser feita para a condição.
solution: Analytics
title: Tipos de teste para operações de teste
topic: Data workbench
uuid: dc0433dd-a35e-472e-8975-f58347512c11
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Tipos de teste para operações de teste{#test-types-for-test-operations}

A condição Comparar e a condição Intervalo exigem que você especifique o tipo de comparação a ser feita para a condição.

A tabela a seguir descreve os tipos disponíveis ( [!DNL LEXICAL], [!DNL NUMERIC]e [!DNL DATETIME]).

<table id="table_1B3AD8BDF0414D0AB8EE0E6D1B53E2CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de teste </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Notas </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> INTEIRO</span> </p> </td> 
   <td colname="col2"> <p>Primeiro, transforma o campo de entrada em um número inteiro. Se isso não for possível, um valor zero será usado. O teste retornará true somente se o valor de entrada inteiro resultante for maior ou igual ao valor mínimo especificado e menor ou igual ao valor máximo especificado. </p> </td> 
   <td colname="col3"> <p>Se um dos campos mín. ou máx. for deixado em branco, o sistema usará o valor mín. ou máx. apropriado disponível para números inteiros assinados de 64 bits. </p> <p> Se o valor mínimo ou máximo especificado na condição não for analisado com êxito em um valor inteiro, o sistema substituirá zero e não interromperá o processamento do conjunto de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> DATA E HORA</span> </p> </td> 
   <td colname="col2"> <p>Primeiro, transforma o campo de entrada em uma data. Se o campo de entrada não puder ser transformado em uma data válida, o teste de condição retornará false. Se o campo puder ser transformado em uma data, o teste retornará true somente se a data de entrada cair na data mínima especificada e na data máxima especificada ou antes dela. </p> </td> 
   <td colname="col3"> <p>Se as datas mín. e máx. não forem válidas, o conjunto de dados não será construído. </p> <p> Se as datas mín. ou máx. não forem fornecidas, o sistema substituirá apropriadamente a data mín. (1 de janeiro de 1600) ou a data máx. (em algum momento do século 24). </p> <p> A Adobe recomenda usar um dos seguintes formatos para <span class="wintitle"> DATETIME</span>: </p> 
    <ul id="ul_44F469CC5D974382AF70D7B1975CF077"> 
     <li id="li_DB5FD4AFD6B34436ACD7C13282F64956"> 1 de janeiro de 2013 HH:MM:SS EDT </li> 
     <li id="li_307580C3F97D495BB16F1212DB38CE37"> Jan 1 2013 HH:MM:SS GMT </li> 
    </ul> <p> O padrão do fuso horário é GMT se não for especificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LEXICAL</span> </p> </td> 
   <td colname="col2"> <p>Retorna true somente se o campo de entrada for lexicamente maior ou igual à string especificada como o mínimo e menor ou igual à string especificada no valor máximo. </p> </td> 
   <td colname="col3"> <p>A comparação léxica usa o valor ASCII dos caracteres nas strings que se movem da esquerda para a direita, comparando os caracteres. Para o primeiro caractere que não corresponde, aquele com o valor ASCII maior é considerado o maior dos dois. Se uma string for menor que a outra, mas até esse ponto todos os caracteres tiverem sido iguais, a string maior será considerada a maior dos dois. Se as strings forem equivalentes a caracteres e com o mesmo comprimento, serão consideradas lexicamente equivalentes. </p> </td> 
  </tr> 
 </tbody> 
</table>

