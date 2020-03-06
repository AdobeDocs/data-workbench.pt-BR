---
description: Depois que o HTML de uma página é solicitado por um navegador, o navegador solicita que os objetos incorporados referenciados no HTML dessa página sejam preenchidos em um servidor da Web para preencher a página mostrada pelo navegador.
solution: Analytics
title: Aquisição de solicitações de objetos incorporados (marcas de página)
topic: Data workbench
uuid: 7fe561d1-aa5a-4ac9-82ba-aa27c7d208dd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aquisição de solicitações de objetos incorporados (marcas de página){#acquiring-embedded-object-requests-page-tags}

Depois que o HTML de uma página é solicitado por um navegador, o navegador solicita que os objetos incorporados referenciados no HTML dessa página sejam preenchidos em um servidor da Web para preencher a página mostrada pelo navegador.

Essas solicitações de objetos incorporados são mais comumente solicitações de arquivos de imagem ou arquivos JavaScript, embora existam centenas ou milhares de tipos de objetos incorporados usados na Internet hoje. Muitas dessas solicitações de objetos incorporados geralmente não são úteis para analisar ou relatar a atividade comercial de um site da Internet; muitas dessas solicitações não são, portanto, desejáveis para aquisição, a menos que tenham um objetivo comercial específico, como a apresentação de um anúncio ou outra medição da atividade do site.

Por exemplo, uma imagem pode ser um anúncio e você pode querer saber que o anúncio foi impressionado por um visitante. Um trecho do JavaScript pode estar em uso para avaliar se o navegador específico tem uma determinada característica e retorná-lo a um [!DNL Sensor] para aquisição. Cada página em um site pode ter 10 ou 100 solicitações de objeto incorporadas nele. Se um site armazena as informações de log para cada uma dessas solicitações, a quantidade de armazenamento de dados necessária para manter os dados de log disponíveis para análise futura é multiplicada pelo número de solicitações de objetos incorporados para cada página solicitada. Por isso, [!DNL Site] permite que você mantenha as solicitações importantes para análise e descarte outras antes de incorrer em custos desnecessários de armazenamento.

Ao usar o recurso de substituição fornecido nos recursos de filtragem de tipo de conteúdo de [!DNL Sensor] (anexando &quot;Log=1&quot; à string de consulta de um URL de solicitação de objeto incorporado), essa solicitação de objeto incorporado específica e os dados de medição relacionados podem ser adquiridos sem exigir que o gerente do site armazene todas as solicitações desse tipo (por exemplo, todas as <image> solicitações).

[!DNL Sensor] coleta os dados de medição na tabela a seguir para cada solicitação de objeto incorporado feita do servidor da Web, assumindo que isso não [!DNL Sensor] está configurado para filtrá-lo ou que o filtro foi substituído. As informações coletadas estão relacionadas ao visitante e à sessão e às sessões subsequentes por meio das entradas do campo de log x-trackingid ou cs(cookie).

<table id="table_11BE08A798E743EC8E76F738F0CE5884"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome W3C </th> 
   <th colname="col2" class="entry"> Dados Coletados </th> 
   <th colname="col3" class="entry"> Explicação </th> 
   <th colname="col4" class="entry"> Exemplo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> Identificador de rastreamento (visitante único) </td> 
   <td colname="col3"> Identificador lido de um cookie colocado no navegador do usuário pelo <span class="wintitle"> Sensor </span> na solicitação inicial </td> 
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
   <td colname="col4"> 200 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> URI Stem </td> 
   <td colname="col3"> A parte do "sistema" do URI solicitada pelo cliente </td> 
   <td colname="col4"> pagedir/page.asp </td> 
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
   <td colname="col4"> <p>Mozilla/4.0+(compatível;+MSIE+6.0; </p> <p>+Windows+NT+5.1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> Cookies do Cliente do Domínio </td> 
   <td colname="col3"> Conteúdo de todos os cookies do usuário para o site </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972 x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> String de consulta </td> 
   <td colname="col3"> A parte da string de consulta, se houver, do URI solicitado pelo cliente </td> 
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td> 
  </tr> 
 </tbody> 
</table>

