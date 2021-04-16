---
description: Informações sobre os campos de registro de dados do evento de linha de base, conforme registrados pelo Sensor.
title: Campos de registro de dados do eventos de linha de base
uuid: aa36d332-089c-4ae2-98e2-a93d2fa023b7
exl-id: ad3d8806-863a-4871-a35b-6680163f00ac
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 3%

---

# Campos de registro de dados do eventos de linha de base{#baseline-event-data-record-fields}

Informações sobre os campos de registro de dados do evento de linha de base, conforme registrados pelo Sensor.

<table id="table_E29606BB010E4DB48C463979B7BEC769"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> <p>O endereço IP do cliente, conforme incluído na solicitação feita ao servidor. </p> <p>Exemplo: 207.68.146.68 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> <p>Os cookies enviados pelo cliente com a solicitação. </p> <p>Exemplo: v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFBFIPLOJMKCAAEPM; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> <p>A string do referenciador HTTP enviada pelo cliente para o servidor com a solicitação. </p> <p>Exemplo: http://www.mysite.net/cgi-bin/websearch?qry </p> <p>Se você estiver usando tags de página, o cs(referrer) será o URL completo do documento que contém a imagem da tag, incluindo HTTP ou HTTPs. </p> <p>Além disso, é possível configurar o Apache (1.3, 2.0 e 2.2) e os sensores do IIS para capturar a porta usada para a solicitação, que pode identificar solicitações HTTP versus HTTPS. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> <p>A string enviada pelo cliente com sua solicitação para o servidor que indica qual tipo de agente do usuário é o cliente. </p> <p>Exemplo: Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-method </td> 
   <td colname="col2"> <p>O tipo de método da solicitação HTTP </p> <p>Exemplo: GET </p> <p>Referência: http://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> <p>A parte da sequência de consulta do URI (tronco + sequência de consulta = URI) </p> <p>Isso é precedido por um ponto de interrogação (?) e podem conter um ou mais pares nome-valor separados por "E" comercial (&amp;). </p> <p>Exemplo: page=homepage </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> <p>A parte do tronco do URI (tronco + sequência de consulta = URI) </p> <p>O tronco é o caminho real ou lógico para o recurso solicitado no servidor. </p> <p>Exemplo: /index.asp </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> <p>O tipo de conteúdo do recurso que está sendo solicitado pelo cliente, conforme relatado pelo servidor. </p> <p>Exemplos: text/html, image/png, image/gif, video/mpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-bytes </td> 
   <td colname="col2"> <p>O número de bytes de dados enviados do servidor para o cliente em resposta à solicitação. </p> <p>Exemplo: 4996 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> <p>O código de status retornado ao cliente pelo servidor. </p> <p>Exemplo: 200 </p> <p>Referência: http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> <p>O nome de domínio ou endereço IP totalmente qualificado do host do recurso solicitado. </p> <p>Exemplo: www.omniture.com </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> experimento com x </td> 
   <td colname="col2"> <p>A lista de todos os nomes e grupos de experimentos controlados dos quais o cliente é membro no momento da solicitação. </p> <p>Exemplo: Home_Exp.Group_1,Registration_Exp.Group_2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestamp </td> 
   <td colname="col2"> <p>A data e a hora (GMT) em que a solicitação foi recebida pelo servidor. </p> <p>O tempo é expresso como o número de 100 nanossegundos desde 1º de janeiro de 1600. </p> <p>Exemplo: 12771098932000000 seria o valor de carimbo de data e hora x para 11:28:52.0000000 na terça-feira, 13 de setembro de 2005. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> <p>O valor hexadecimal de 64 bits do identificador exclusivo do navegador encontrado em um cookie persistente, conforme definido por um <span class="wintitle"> Sensor </span> e fornecido pelo cliente com uma solicitação para um servidor. </p> <p>Exemplo: 42FDF66DE610CF36 </p> </td> 
  </tr> 
 </tbody> 
</table>

O [!DNL data workbench server] pode derivar diversas variáveis dos campos de registro de dados do evento da linha de base. Para obter mais informações, consulte o *Guia de Configuração do Conjunto de Dados*.
