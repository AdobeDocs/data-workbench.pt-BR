---
description: O sensor adquire todos os dados de medição que são executados nas solicitações de página (solicitações GET) feitas nos servidores da Web nos quais ele foi instalado.
solution: Analytics
title: Aquisição de dados de solicitação de página
topic: Data workbench
uuid: 06cf2b14-8d2c-483e-8a75-ce772798978f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aquisição de dados de solicitação de página{#acquiring-page-request-data}

O sensor adquire todos os dados de medição que são executados nas solicitações de página (solicitações GET) feitas nos servidores da Web nos quais ele foi instalado.

[!DNL Sensor] adquire esses dados de medição por meio da interface de programação de aplicativos do servidor da Web, diretamente da instância ou instâncias do software do servidor da Web em execução no servidor da Web. [!DNL Sensor] não acessa os arquivos de log gerados pelo servidor da Web. Na verdade, depois [!DNL Sensor] que o servidor de análise de big data for instalado e testado, o recurso de registro nativo do servidor da Web poderá ser desativado sem afetar a coleta de dados. Em muitos casos, a desativação do registro de arquivos nos discos locais das máquinas do servidor Web melhora a capacidade de serviço de página desses servidores Web devido à quantidade relativamente grande de E/S de disco fixo necessária para registrar essas informações no disco local da máquina do servidor Web.

[!DNL Sensor] coleta dados de medição e solicitação da Web diretamente de cada processo do servidor da Web e do servidor virtual (se aplicável) e grava temporariamente os dados em um Arquivo de Fila, uma fila de memória tolerante a falhas com backup em disco fixo, na máquina do servidor da Web. O serviço de Transmissor de Sensores (ou daemon dependendo da plataforma) recupera dados do Arquivo de Fila e compacta e criptografa-os antes de transmiti-los para o servidor de análise de big data para armazenamento de longo prazo. Com [!DNL Sensor], os dados são acumulados nos computadores do servidor Web no Arquivo de Fila somente se você tiver uma rede ou outro problema que impeça sua transmissão. O Arquivo de Fila permite o armazenamento local eficiente de horas a dias de dados de solicitação da Web para proteger os dados se uma falha da rede ou do sistema não permitir que os dados sejam transmitidos ao servidor de análise de big data em tempo real.

[!DNL Sensor] coleta dados de medição de cada processo do servidor da Web físico e lógico, filtra-os por tipo de conteúdo, compacta-os, criptografa-os e os transmite para o servidor da análise de big data.

A tabela a seguir contém os campos de informações de log adquiridos por [!DNL Sensor] cada solicitação GET que não é filtrada com base no arquivo de [!DNL Sensor’s] configuração:

<table id="table_5F65474150EC41648B35D0B031FB9B15"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome W3C </th> 
   <th colname="col2" class="entry"> Dados Coletados </th> 
   <th colname="col3" class="entry"> Explicação </th> 
   <th colname="col4" class="entry"> Explicação </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> Identificador de rastreamento (visitante único) </td> 
   <td colname="col3"> Identificador lido de um cookie colocado no navegador do usuário pelo <span class="wintitle"> Sensor </span> na solicitação inicial do Visitante </td> 
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data </p> <p>Hora </p> </td> 
   <td colname="col2"> Carimbo de data e hora </td> 
   <td colname="col3"> Hora em que a solicitação foi processada pelo servidor (com precisão de 100 ns; a precisão depende do ambiente do servidor e do NTP) </td> 
   <td colname="col4"> 2002-11-21 17:21:45.123 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-Type) </td> 
   <td colname="col2"> Tipo de conteúdo </td> 
   <td colname="col3"> Tipo de objeto retornado do servidor </td> 
   <td colname="col4"> text/html </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> Código de status da resposta HTTP </td> 
   <td colname="col3"> Código numérico gerado pelo servidor que anota o status da resposta do servidor HTTP </td> 
   <td colname="col4"> 404 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> URI Stem </td> 
   <td colname="col3"> A parte do sistema do URI solicitada pelo cliente </td> 
   <td colname="col4"> <span class="filepath"> pagedir/page.asp </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> IP do cliente </td> 
   <td colname="col3"> Endereço IP do cliente requerente </td> 
   <td colname="col4"> 127.0.0.1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> Nome do domínio do servidor </td> 
   <td colname="col3"> Nome de domínio do servidor Web que processa a solicitação </td> 
   <td colname="col4"> <span class="filepath"> www.domain.com </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> URL de referência </td> 
   <td colname="col3"> Conteúdo do campo do referenciador HTTP enviado pelo cliente </td> 
   <td colname="col4"> <span class="filepath"> http://www.referringsite.com </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> Agente do usuário </td> 
   <td colname="col3"> Dispositivo usado para fazer uma solicitação ao servidor HTTP </td> 
   <td colname="col4"> Mozilla/4.0+(compatível;+MSIE+6.0; +Windows+NT+5.1) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> Cookies do Cliente do Domínio </td> 
   <td colname="col3"> Conteúdo de todos os cookies do usuário para o site </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> String de consulta </td> 
   <td colname="col3"> A parte da string de consulta, se houver, do URI solicitado pelo cliente </td> 
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td> 
  </tr> 
 </tbody> 
</table>

