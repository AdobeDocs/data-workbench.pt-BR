---
description: O sensor adquire todos os dados de medição que são transportados nas solicitações de página (solicitações do GET) feitas nos servidores da Web em que foi instalado.
title: Adquirir dados de solicitação de página
uuid: 06cf2b14-8d2c-483e-8a75-ce772798978f
exl-id: e42566a3-d5b4-4f1a-b8cd-1ea646041101
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 4%

---

# Adquirir dados de solicitação de página{#acquiring-page-request-data}

O sensor adquire todos os dados de medição que são transportados nas solicitações de página (solicitações do GET) feitas nos servidores da Web em que foi instalado.

[!DNL Sensor] O adquire esses dados de medição por meio da interface de programação de aplicativos do servidor da Web, diretamente da instância ou instâncias do software do servidor da Web em execução no seu servidor da Web. [!DNL Sensor] não acessa os arquivos de log gerados pelo servidor da Web. Na verdade, depois que [!DNL Sensor] e o servidor do Data Workbench tiverem sido instalados e testados, o recurso de registro nativo do servidor da Web poderá ser desativado sem afetar a coleta de dados. Em muitos casos, desabilitar o registro de arquivos nos discos locais das máquinas do servidor da Web melhora a capacidade de fornecimento de página desses servidores da Web devido à quantidade relativamente grande de E/S de disco fixo necessária para registrar essas informações no disco local da máquina do servidor da Web.

[!DNL Sensor] coleta dados de medição e solicitação da Web diretamente de cada processo de servidor da Web e do servidor virtual (se aplicável) e grava temporariamente os dados em um arquivo de fila, uma fila de memória tolerante a falhas com backup de disco fixo, na máquina do servidor da Web. O serviço Transmissor do sensor (ou daemon dependendo da plataforma) recupera dados do Arquivo de fila e compacta e criptografa-os antes de transmiti-los para o servidor do Data Workbench para armazenamento de longo prazo. Com [!DNL Sensor], os dados são acumulados nas máquinas do servidor da Web no Arquivo de Fila somente se você estiver tendo um problema de rede ou outro que impeça a transmissão. O Arquivo de Fila permite o armazenamento local eficiente de horas a dias de dados de solicitação da Web para proteger os dados se uma falha de rede ou de sistema não permitir que os dados sejam transmitidos para o servidor do Data Workbench em tempo real.

[!DNL Sensor] coleta dados de medição de cada processo físico e lógico do servidor da Web, os filtra por tipo de conteúdo, compacta, criptografa e os envia para o servidor do Data Workbench.

A tabela a seguir contém os campos de informações de log adquiridos por [!DNL Sensor] para cada solicitação de GET que não é filtrada com base no arquivo de configuração [!DNL Sensor’s]:

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
   <td colname="col3"> Hora em que a solicitação foi processada pelo servidor (com precisão de 100ns; a precisão depende do ambiente do servidor e do NTP) </td> 
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
   <td colname="col2"> Código de status de resposta HTTP </td> 
   <td colname="col3"> Código numérico gerado pelo servidor que anota o status da resposta do servidor HTTP </td> 
   <td colname="col4"> 404 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> Etapa URI </td> 
   <td colname="col3"> A parte do sistema do URI solicitada pelo cliente </td> 
   <td colname="col4"> <span class="filepath"> pagedir/page.asp  </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> IP do cliente </td> 
   <td colname="col3"> Endereço IP do cliente requerente </td> 
   <td colname="col4"> 127.0.0.1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> Nome de domínio do servidor </td> 
   <td colname="col3"> Nome do domínio do servidor da Web que processa a solicitação </td> 
   <td colname="col4"> <span class="filepath"> www.domain.com  </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> URL de referência </td> 
   <td colname="col3"> Conteúdo do campo do referenciador HTTP enviado pelo cliente </td> 
   <td colname="col4"> <span class="filepath"> http://www.referringsite.com  </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> Agente do usuário </td> 
   <td colname="col3"> Dispositivo usado para fazer uma solicitação ao servidor HTTP </td> 
   <td colname="col4"> Mozilla/4.0+(compatível;+MSIE+6.0; +Windows+NT+5.1) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> Cookies do cliente do domínio </td> 
   <td colname="col3"> Conteúdo de todos os cookies do usuário para o site </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> String de consulta </td> 
   <td colname="col3"> A parte da sequência de consulta, se houver, do URI solicitado pelo cliente </td> 
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td> 
  </tr> 
 </tbody> 
</table>
