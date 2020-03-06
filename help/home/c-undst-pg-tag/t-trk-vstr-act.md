---
description: Os sites arquitetados usando o Flash exigem atenção especial em relação à captura de ações de visitantes executadas dentro do conteúdo de mídia avançada.
solution: Analytics
title: Rastreamento da atividade do visitante dentro do conteúdo Flash Rich Media
topic: Data workbench
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Rastreamento da atividade do visitante dentro do conteúdo Flash Rich Media{#tracking-visitor-activity-within-flash-rich-media-content}

Os sites arquitetados usando o Flash exigem atenção especial em relação à captura de ações de visitantes executadas dentro do conteúdo de mídia avançada.

Usando o [!DNL Flash] ActionScript, você pode fazer alterações simples em seus [!DNL Flash] filmes existentes para permitir o rastreamento de todas as interações do visitante com o filme, como cliques em botões ou movimentos do mouse.

Para facilitar o rastreamento da atividade do Visitante em seu [!DNL Flash] filme, siga as etapas listadas abaixo:

1. Adicione o seguinte código ActionScript ao seu filme. Este código representa uma função que pode ser chamada por eventos dentro do [!DNL Flash] filme que você deseja rastrear.

   ```
   // FLASH TAG CODE BEGIN 
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt"; 
   function tag(PAGENAME,VARIABLES) { 
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0); 
   } 
   // FLASH TAG CODE END
   ```

1. Crie um arquivo em branco com o nome [!DNL flashtag.txt] e coloque-o em seus servidores da Web.
1. Na função na Etapa 1, substitua o espaço reservado [!DNL [PATH_TO_WEB_SERVER]] pelo caminho relativo ou totalmente qualificado para o local do [!DNL flashtag.txt] arquivo. Por exemplo:

   ```
   var FLASHTAGURI = http://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. Adicione o seguinte código ActionScript a todos os eventos a serem rastreados. Este código representa uma chamada de função usada para capturar dados sobre o evento:

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Este exemplo ilustra o uso do evento on(release); no entanto, a função tag() pode ser referenciada por meio de qualquer evento que você queira rastrear, como um evento on(press), on(rollover), on(rollout) ou on(keypress).

   O espaço reservado [!DNL [PUT_PAGE_NAME_HERE]] deve ser substituído por uma string que representa o nome da página ou do evento que você está rastreando. A variável [!DNL [PUT_PAGE_NAME_HERE]] pode ser modificada manualmente ou por meio de referência de variável para indicar um nome exclusivo para a página ou evento no [!DNL Flash] aplicativo. O valor que substitui o espaço reservado [!DNL [PUT_PAGE_NAME_HERE]] pode consistir de um nome simples ou pode ser estruturado para representar uma estrutura hierárquica semelhante a um URI completo. Por exemplo:

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   A Adobe recomenda que, antes da implantação do código, você compile uma especificação por escrito para nomes de páginas e nomes de eventos para facilitar o alinhamento das necessidades comerciais e das tarefas de desenvolvimento e reduzir o potencial para ciclos adicionais de desenvolvimento.

1. Se desejar, variáveis adicionais podem ser coletadas e associadas a páginas ou eventos no [!DNL Flash] filme. Para fazer isso, substitua o espaço reservado [!DNL [PUT_ADDITIONAL_VAR_HERE]] por um conjunto de pares de nome=valor separados por um e comercial (&amp;). Por exemplo:

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   As variáveis podem ser modificadas manualmente ou por meio de referência de variável para indicar atributos adicionais a serem coletados e associados à página ou ao evento. Se não houver variáveis adicionais aplicáveis para coletar, remova [!DNL [PUT_ADDITIONAL_VAR_HERE]].

   A configuração do rastreamento de visitantes em conteúdo de mídia [!DNL Flash] avançada está concluída. Quando o evento for chamado, a função de [!DNL (PAGENAME,VARIABLES)] tag será chamada, resultando em uma solicitação HTTP para o arquivo a seguir. Esta função será chamada além de outras funções que podem ser acionadas conforme definido no seu [!DNL Flash] filme:

   ```
   http://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

A solicitação HTTP resultante da função [!DNL Flash] Tag ActionScript resulta na coleta das seguintes informações em relação a cada evento dentro do [!DNL Flash] filme. A última linha da tabela (consulta do W3C Name cs-uri) representa as informações coletadas para as variáveis adicionais especificadas na chamada de função.

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
   <td colname="col3"> Hora em que a solicitação foi processada pelo servidor (com precisão de 100 ns; a precisão depende do ambiente do servidor e do NTP) </td> 
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
   <td colname="col2"> Código de status da resposta HTTP </td> 
   <td colname="col3"> Código numérico gerado pelo servidor que anota o status da resposta do servidor HTTP </td> 
   <td colname="col4"> 200 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> URI Stem </td> 
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
   <td colname="col2"> Nome do domínio do servidor </td> 
   <td colname="col3"> Nome de domínio do servidor Web que processa a solicitação </td> 
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
   <td colname="col2"> Cookies do Cliente do Domínio </td> 
   <td colname="col3"> Conteúdo de todos os cookies do usuário para o site </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> String de consulta </td> 
   <td colname="col3"> A parte da string de consulta, se houver, do URI solicitado pelo cliente </td> 
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td> 
  </tr> 
 </tbody> 
</table>
