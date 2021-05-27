---
description: A Chamada de execução de tag da página de referência é inserida em páginas da Web para as quais você deseja coletar dados de medição.
title: Adicionar chamadas de execução de tag de página de referência
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
exl-id: a4f9ab2b-50e8-4e0b-9c87-80dffb697316
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 3%

---

# Adicionar chamadas de execução de tag de página de referência{#adding-reference-page-tag-execution-calls}

A Chamada de execução de tag da página de referência é inserida em páginas da Web para as quais você deseja coletar dados de medição.

Ela deve ser incluída no corpo do documento HTML e pode ser colocada em um rodapé de inclusão global, se aplicável. O [!DNL Reference Page Tag Execution Call] pode ser modificado pela sua equipe para coletar informações adicionais que podem ser identificadas durante a coleta de requisitos em reuniões com a equipe de Serviços de consultoria do Adobe.

Para facilitar a coleta de dados por meio do uso do [!DNL Reference Page Tag], conclua as seguintes etapas:

1. Copie o seguinte código no corpo do documento HTML:

   ```
   <!--//BEGIN REFERENCE PAGE TAG--> 
   <script language="javascript"> 
   var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
   var v = {}; 
   </script> 
   
   <!--//MODIFIY PATH TO ZIG.JS--> 
   <script language="javascript" src="/path/to/zig.js" type="text/javascript"></script> 
   <!--//END REFERENCE PAGE TAG--> 
   
   <noscript> 
   <img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
   </noscript> 
   <!-- END REFERENCE PAGE TAG-->
   ```

1. Modifique o caminho para o local dos arquivos [!DNL zig.js] e [!DNL zag.gif]. Por exemplo:

   ```
   //www.mysite.com/scripts/zig.js 
   //www.mysite.com/images/zag.gif 
   ```

Certifique-se de que os cabeçalhos de Controle de Cache HTTP apropriados tenham sido definidos no servidor da Web para garantir que os arquivos [!DNL zig.js]e [!DNL zag.gif] não sejam armazenados em cache pelo navegador. Você pode definir as informações do cabeçalho Controle de Cache HTTP usando um dos dois métodos. O primeiro método é definir um cabeçalho HTTP por meio do servidor da Web. O segundo método é definir um cabeçalho HTTP para cada página específica ou objeto incorporado usando script. Com o método de script, a página da Web deve ter sido criada usando uma linguagem de programação, como JSP ou ASP. A página é, então, script para enviar as informações de cabeçalho apropriadas. Este método apresenta duas desvantagens óbvias: 1) todas as páginas devem ser codificadas para enviar o cabeçalho e 2) as páginas não podem ser HTML estático, o que tem algum efeito no desempenho do servidor da Web.

Os sites da Web em execução no Microsoft IIS podem adicionar o cabeçalho HTTP apropriado por meio do Console de Gerenciamento da Microsoft. Os sites oferecidos pelos Servidores Web Netscape iPlanet podem fazer isso editando o arquivo [!DNL obj.conf] no diretório de configuração do site. O Apache Web Server fornece webmasters a capacidade de personalizar cabeçalhos HTTP usando o módulo mod_headers incluído, onde o AOLServer se torna personalizável por meio do uso de módulos Tcl. Antes de implementar cabeçalhos HTTP Cache-Control, você deve consultar a documentação específica da plataforma do servidor da Web.

Em geral, o cabeçalho HTTP deve ser estruturado da seguinte maneira:

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```
