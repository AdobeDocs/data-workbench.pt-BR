---
description: Informações sobre os campos de dados que o servidor do Data Workbench pode processar para construir um conjunto de dados.
title: Campos de registro de dados do evento
uuid: b0232bfa-0a3b-4e3d-876e-6a15a3764eae
exl-id: 35433b87-991a-4fb9-ba6a-3217e89eb769
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 2%

---

# Campos de registro de dados do evento{#event-data-record-fields}

Informações sobre os campos de dados que o servidor do Data Workbench pode processar para construir um conjunto de dados.

* [Sobre dados de evento](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-3a0705f8c1824017aa4effed9903efbe)
* [Campos de registro de dados do eventos de linha de base](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-a882ed7aa6af41eeb45a55bf8c1ca3d7)
* [Campos derivados](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-b6c57ee2aa31469fbd5dab90e52bc677)

## Sobre dados de evento {#section-3a0705f8c1824017aa4effed9903efbe}

Os dados do evento usados para criar um conjunto de dados residem em arquivos chamados de fontes de log. Os dados disponíveis nas fontes de log são chamados de dados de evento porque cada registro de dados representa um registro de transação ou uma única instância de um evento com um carimbo de data e hora associado.

Os dados de evento de uma fonte de log são coletados em tempo real por [!DNL Sensors]. Os dados de evento coletados por [!DNL Sensors] de HTTP e servidores de aplicativos são transmitidos para servidores do Data Workbench, que convertem os dados em arquivos de log compactados ( [!DNL .vsl]). Os dados de evento que residem em um arquivo simples, em um arquivo XML ou em uma fonte de dados ODBC são lidos pelo servidor do Data Workbench, que fornece decodificadores definidos para extrair um conjunto comum de campos de dados desses diferentes formatos.

As seções a seguir fornecem informações sobre os campos de dados (conhecidos como campos de registro de dados de eventos ou campos de entrada de log ) coletados por [!DNL Sensors] ou lidos e disponibilizados para o servidor do Data Workbench.

>[!NOTE]
>
>Os nomes dos campos geralmente seguem a convenção de nomenclatura do formato de arquivo de log estendido W3C. Muitos dos campos têm prefixos que indicam a fonte das informações contidas no campo :

* cs indica a comunicação do cliente com o servidor.
* sc indica a comunicação do servidor com o cliente.
* s indica informações do servidor.
* c indica informações do cliente.
* x indica informações criadas por um produto de software Adobe.

## Campos de registro de dados do eventos de linha de base {#section-a882ed7aa6af41eeb45a55bf8c1ca3d7}

Os arquivos de log ( [!DNL .vsl]) contêm os campos de dados de evento coletados dos servidores por [!DNL Sensors] e usados pelo servidor do Data Workbench no processo de construção do conjunto de dados. A tabela a seguir lista os campos em um registro de dados de evento típico, conforme registrado por [!DNL Sensor]:

<table id="table_98E135FE4EAF44D6ADEB3C6C1C0BF6A4">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Campo </th>
   <th colname="col2" class="entry"> Descrição </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> c-ip </td>
   <td colname="col2"> <p>O endereço IP do cliente, conforme incluído na solicitação feita ao servidor. </p> <p> Exemplo: 207.68.146.68 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> <p>Os cookies enviados pelo cliente com a solicitação. </p> <p> Exemplo: v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFBFIPLOJMKCAAEPM; </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> <p>A string do referenciador HTTP enviada pelo cliente para o servidor com a solicitação. </p> <p> Exemplo: <span class="filepath"> https://www.mysite.net/cgi-bin/websearch?qry </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> <p>A string enviada pelo cliente com sua solicitação para o servidor que indica qual tipo de agente do usuário é o cliente. </p> <p> Exemplo: Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-method </td>
   <td colname="col2"> <p>O tipo de método da solicitação HTTP. </p> <p> Exemplo: GET </p> <p> Referência: <span class="filepath"> https://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> <p>A parte da sequência de consulta do URI (tronco + sequência de consulta = URI). Isso é precedido por um ponto de interrogação (?) e podem conter um ou mais pares nome-valor separados por "E" comercial (&amp;). </p> <p> Exemplo: page=homepage </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-stem </td>
   <td colname="col2"> <p>A parte do tronco do URI (tronco + sequência de consulta = URI). O tronco é o caminho real ou lógico para o recurso solicitado no servidor. </p> <p> Exemplo: <span class="filepath"> /index.asp </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc(content-type) </td>
   <td colname="col2"> <p>O tipo de conteúdo do recurso que está sendo solicitado pelo cliente, conforme relatado pelo servidor. </p> <p> Exemplos: text/html, image/png, image/gif, video/mpeg </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc-bytes </td>
   <td colname="col2"> <p>O número de bytes de dados enviados do servidor para o cliente em resposta à solicitação </p> <p> Exemplo: 4996 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc-status </td>
   <td colname="col2"> <p>O código de status retornado ao cliente pelo servidor. </p> <p> Exemplo: 200 </p> <p> Referência: <span class="filepath"> https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> s-dns </td>
   <td colname="col2"> <p>O nome de domínio ou endereço IP totalmente qualificado do host do recurso solicitado. </p> <p> Exemplo: <span class="filepath"> www.adobe.com </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> experimento com x </td>
   <td colname="col2"> <p>A lista de todos os nomes e grupos de experimentos controlados dos quais o cliente é membro no momento da solicitação. </p> <p> Exemplo: VSHome_Exp.Group_1,VSRegistration_Exp.Group_2 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-timestamp </td>
   <td colname="col2"> <p>A data e a hora (GMT) em que a solicitação foi recebida pelo servidor. O tempo é expresso como o número de 100 nanossegundos desde 1º de janeiro de 1600. </p> <p> Exemplo: 127710989320000000 seria o valor x-timestamp para 11:28:52.0000000 na terça-feira, 13 de setembro de 2005. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> <p>O valor hexadecimal de 64 bits do identificador exclusivo do navegador encontrado em um cookie persistente, conforme definido por um <span class="wintitle"> Sensor </span> e fornecido pelo cliente com uma solicitação para um servidor. </p> <p> Exemplo: 42FDF66DE610CF36 </p> </td>
  </tr>
 </tbody>
</table>

## Campos derivados {#section-b6c57ee2aa31469fbd5dab90e52bc677}

A tabela abaixo lista exemplos de campos que são derivados pelo servidor do Data Workbench a partir dos campos de registro de dados do evento da linha de base:

<table id="table_3B008F1314804A69AE69E8F94908F497">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Campo </th>
   <th colname="col2" class="entry"> Descrição </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> cs(cookie)(name) </td>
   <td colname="col2"> O valor de um determinado par nome-valor dentro de um cookie. </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer-domain) </td>
   <td colname="col2"> <p>O nome de domínio ou endereço IP do URI de referência HTTP. </p> <p> <p>Observação:  Este campo é somente leitura. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer-host) </td>
   <td colname="col2"> <p>O nome do host inteiro do referenciador. </p> <p> Exemplo: Se cs(referrer) for <span class="filepath"> https://my.domain.com/my/page </span>, cs(referrer-host) será <span class="filepath"> my.domain.com </span>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer-query)(name) </td>
   <td colname="col2"> <p>O valor de uma string de consulta de referenciador. </p> <p> <p>Observação:  Não é possível acessar um valor de string de consulta de referenciador usando o campo cs(referrer)(name) . </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri </td>
   <td colname="col2"> <p>O URI completo (tronco + sequência de consulta = URI inteiro). </p> <p> Exemplo: <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query(name) </td>
   <td colname="col2"> <p>O valor associado ao nome fornecido. Se houver vários valores para o nome fornecido, esse campo retornará o último desses valores. </p> Exemplos:
    <ul id="ul_47BBB2E3076A46629BFCDB2A460F700B">
     <li id="li_AC9BB29505A54AE4AFF49438530C9EA4"> Para o URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span>, cs-uri-query(product3) retornaria cd. </li>
     <li id="li_B036C1D0B25748E0A155DDC9B1B999CB"> Para o URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product1=casette </span>, <span class="wintitle"> cs-uri-query(product1) </span> retornaria a caixa. </li>
    </ul> <p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> ctime </td>
   <td colname="col2"> x-timestamp expresso como segundos desde 1° de janeiro de 1970. Este campo também é chamado de x-unixtime. </td>
  </tr>
  <tr>
   <td colname="col1"> data </td>
   <td colname="col2"> x-timestamp no formato AAAA-MM-DD. </td>
  </tr>
  <tr>
   <td colname="col1"> time </td>
   <td colname="col2"> x-timestamp no formato HH:MM:SS. </td>
  </tr>
  <tr>
   <td colname="col1"> x-local-timestring </td>
   <td colname="col2"> <p>x-timestamp convertido para o fuso horário local especificado no arquivo <span class="filepath"> Transformation.cfg </span> do conjunto de dados. O formato é AAAA-MM-DD HH:MM:SS.mmm. </p> <p> <p>Observação:  Também é possível definir conversões de tempo, como x-local-timestring no arquivo <span class="filepath"> Log Processing.cfg </span>. Para obter informações, consulte <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Arquivo de configuração de processamento de log </a>. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-log-source-id </td>
   <td colname="col2"> <p>O identificador correspondente à origem do log de uma entrada de log específica. Para que o identificador seja registrado, você deve especificá-lo no campo <span class="wintitle"> ID da Fonte de Log </span> do arquivo <span class="filepath"> Log Processing.cfg </span> ao definir <span class="wintitle"> Sensor </span>, arquivo de log ou fontes de dados ODBC. Para obter mais informações, consulte <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Arquivo de configuração de processamento de log </a>. </p> <p> Exemplo: VSensor01. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> máscara x </td>
   <td colname="col2"> O padrão de máscara das fontes de dados do <span class="wintitle"> Sensor </span> (derivado dos nomes de arquivo <span class="filepath"> .vsl </span>). Para um arquivo cujo nome é do formato <span class="filepath"> AAAAMMDD-SENSORID.VSL </span>, a máscara x é SENSORID. </td>
  </tr>
  <tr>
   <td colname="col1"> x-timestring </td>
   <td colname="col2"> x-timestamp no formato AAAA-MM-DD HH:MM:SS.mmm. </td>
  </tr>
  <tr>
   <td colname="col1"> x-unixtime </td>
   <td colname="col2"> A hora decimal UNIX derivada do carimbo de data e hora x. </td>
  </tr>
 </tbody>
</table>

[!DNL Sensor], quando usado em um servidor, o pode coletar campos de dados do evento de qualquer solicitação HTTP ou cabeçalho de resposta válido ou variável disponível para ele por meio da API do servidor. Para coletar esses campos de dados, você deve especificar os campos de cabeçalho ou variáveis desejados no arquivo de configuração [!DNL txlogd.conf]para [!DNL Sensor]. Para obter mais informações, consulte o *Guia [!DNL Sensor] de Data Workbench*.
