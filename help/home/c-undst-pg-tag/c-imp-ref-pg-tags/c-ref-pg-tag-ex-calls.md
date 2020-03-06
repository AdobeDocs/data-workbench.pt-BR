---
description: A Chamada de execução de tag da página de referência é inserida nas páginas da Web para as quais você deseja coletar dados de medição.
solution: Analytics
title: Adicionando chamadas de execução de tag de página de referência
topic: Data workbench
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Adicionando chamadas de execução de tag de página de referência{#adding-reference-page-tag-execution-calls}

A Chamada de execução de tag da página de referência é inserida nas páginas da Web para as quais você deseja coletar dados de medição.

Ele deve ser incluído no corpo do documento HTML e pode ser colocado dentro de um rodapé de inclusão global, se aplicável. A equipe [!DNL Reference Page Tag Execution Call] pode modificar o para coletar informações adicionais que podem ser identificadas durante a reunião de requisitos com a equipe dos Serviços de consultoria da Adobe.

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

1. Modifique o caminho para o local dos arquivos [!DNL zig.js] e [!DNL zag.gif] . Por exemplo:

   ```
   //www.mysite.com/scripts/zig.js 
   //www.mysite.com/images/zag.gif 
   ```

Certifique-se de que os cabeçalhos HTTP Cache-Control apropriados foram definidos no servidor Web para garantir que os arquivos [!DNL zig.js][!DNL zag.gif] e arquivos não sejam armazenados em cache pelo navegador. É possível definir as informações do cabeçalho HTTP Cache-Control usando um dos dois métodos. O primeiro método é definir um cabeçalho HTTP por meio do servidor da Web. O segundo método é definir um cabeçalho HTTP para cada página específica ou objeto incorporado usando script. Com o método de script, a página da Web deve ter sido criada usando uma linguagem de programação como JSP ou ASP. A página então é script para que envie as informações apropriadas do cabeçalho. Este método apresenta duas desvantagens óbvias: 1) todas as páginas devem ser codificadas para enviar o cabeçalho e 2) as páginas não podem ser HTML estático, o que tem algum efeito no desempenho do servidor da Web.

Os sites em execução no Microsoft IIS podem adicionar o cabeçalho HTTP apropriado por meio do Console de Gerenciamento da Microsoft. Os sites fornecidos pelos Servidores Web Netscape iPlanet podem conseguir isso editando o [!DNL obj.conf] arquivo no diretório de configuração do site. O Apache Web Server fornece aos webmasters a capacidade de personalizar cabeçalhos HTTP usando o módulo mod_headers incluído, onde o AOLServer se torna personalizável através do uso de módulos Tcl. Antes de implementar cabeçalhos HTTP Cache-Control, consulte a documentação específica da plataforma do servidor da Web.

Em geral, o cabeçalho HTTP deve ser estruturado da seguinte maneira:

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```

