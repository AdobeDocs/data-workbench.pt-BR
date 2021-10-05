---
description: Os sites arquitetados com o Flash exigem atenção especial em relação à captura de ações de visitantes realizadas dentro do conteúdo de mídia avançada.
title: Rastrear atividade do visitante no conteúdo de mídia avançada em flash
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
exl-id: f51c7034-a7fd-4575-80e1-18fc6513ca2b
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 5%

---

# Rastrear atividade do visitante no conteúdo de mídia avançada em flash{#tracking-visitor-activity-within-flash-rich-media-content}

Os sites arquitetados com o Flash exigem atenção especial em relação à captura de ações de visitantes realizadas dentro do conteúdo de mídia avançada.

Usando o ActionScript [!DNL Flash], você pode fazer alterações simples em seus filmes existentes [!DNL Flash] para permitir o rastreamento de todas as interações do visitante com o filme, como cliques de botão ou movimentos do mouse.

Para facilitar o rastreamento da atividade do Visitante em seu filme [!DNL Flash], siga as etapas listadas abaixo:

1. Adicione o seguinte código de ActionScript ao seu filme. Este código representa uma função que pode ser chamada por eventos no filme [!DNL Flash] que você deseja rastrear.

   ```
   // FLASH TAG CODE BEGIN
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt";
   function tag(PAGENAME,VARIABLES) {
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0);
   }
   // FLASH TAG CODE END
   ```

1. Crie um arquivo em branco chamado [!DNL flashtag.txt] e coloque o arquivo em seus servidores da Web.
1. Na função na Etapa 1, substitua o espaço reservado \[[!DNL PATH_TO_WEB_SERVER]\] pelo caminho relativo totalmente qualificado para o local do arquivo [!DNL flashtag.txt]. Por exemplo:

   ```
   var FLASHTAGURI = https://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. Adicione o seguinte código de ActionScript a todos os eventos a serem rastreados. Este código representa uma chamada de função usada para capturar dados sobre o evento:

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Este exemplo ilustra o uso do evento on(release); no entanto, a função tag() pode ser referenciada por meio de qualquer evento que você queira rastrear, como um evento on(press), on(rolover), on(rollout) ou on (keypress) .

   O espaço reservado \[[!DNL PUT_PAGE_NAME_HERE]\] deve ser substituído por uma string que representa o nome da página ou evento que você está rastreando. A variável \[[!DNL PUT_PAGE_NAME_HERE]\]pode ser modificada manualmente ou por meio de referência de variável para indicar um nome exclusivo para a página ou evento dentro do aplicativo [!DNL Flash]. O valor que substitui o espaço reservado \[[!DNL PUT_PAGE_NAME_HERE]\] pode consistir em um nome simples ou pode ser estruturado para representar uma estrutura hierárquica semelhante a um URI completo. Por exemplo:

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   A Adobe recomenda que, antes da implantação do código, você compile uma especificação escrita para nomes de página e nomes de evento para facilitar o alinhamento das necessidades comerciais e das tarefas de desenvolvimento e reduzir o potencial para ciclos de desenvolvimento adicionais.

1. Se desejar, variáveis adicionais podem ser coletadas e associadas a páginas ou eventos no filme [!DNL Flash]. Para fazer isso, substitua o espaço reservado \[[!DNL PUT_ADDITIONAL_VAR_HERE]\] por um conjunto de pares name=value separados por um E comercial (&amp;). Por exemplo:

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   As variáveis podem ser modificadas manualmente ou por meio de referência de variável para indicar atributos adicionais a serem coletados e associados à página ou evento. Se não houver variáveis adicionais aplicáveis para coletar, remova \[[!DNL PUT_ADDITIONAL_VAR_HERE]\].

   Sua configuração de rastreamento de visitantes no conteúdo de mídia avançada [!DNL Flash] agora está concluída. Quando o evento for chamado, a função tag [!DNL (PAGENAME,VARIABLES)] será chamada, resultando em uma solicitação HTTP sendo feita para o arquivo a seguir. Esta função será chamada além de outras funções que podem ser acionadas conforme definido no filme [!DNL Flash]:

   ```
   https://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

A solicitação HTTP resultante da função [!DNL Flash] Tag ActionScript resulta na coleta das seguintes informações em relação a cada evento no filme [!DNL Flash]. A última linha na tabela (W3C Name cs-uri-query) representa as informações coletadas para as variáveis adicionais especificadas na chamada de função.

<table id="table_A7ED9D38F36B4405947B2F48EA94D3C4">
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
   <td colname="col3"> Identificador lido de um cookie colocado no navegador do usuário pelo <span class="wintitle"> Sensor </span> na solicitação inicial do Visitante </td>
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td>
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
   <td colname="col4"> Texto/html </td>
  </tr>
  <tr>
   <td colname="col1"> sc-status </td>
   <td colname="col2"> Código de status de resposta HTTP </td>
   <td colname="col3"> Código numérico gerado pelo servidor que anota o status da resposta do servidor HTTP </td>
   <td colname="col4"> 200 </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-stem </td>
   <td colname="col2"> Etapa URI </td>
   <td colname="col3"> A parte do sistema do URI solicitada pelo cliente </td>
   <td colname="col4"> /flashtag/flashtag.txt </td>
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
   <td colname="col4"> www.mysite.com </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> URL de referência </td>
   <td colname="col3"> Conteúdo do campo do referenciador HTTP enviado pelo cliente </td>
   <td colname="col4"></td>
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
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td>
  </tr>
 </tbody>
</table>
