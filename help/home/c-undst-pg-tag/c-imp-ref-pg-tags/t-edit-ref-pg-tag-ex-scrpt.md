---
description: A tag de página de referência consiste em um script de execução de tag de página que reside em um servidor da Web e, quando chamado, resulta na coleta de todos os dados do lado do cliente para a página solicitada pelo visitante do site.
solution: Analytics
title: Editar o script de execução de tag da página de referência
topic: Data workbench
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Editar o script de execução de tag da página de referência{#editing-the-reference-page-tag-execution-script}

A tag de página de referência consiste em um script de execução de tag de página que reside em um servidor da Web e, quando chamado, resulta na coleta de todos os dados do lado do cliente para a página solicitada pelo visitante do site.

Você pode modificar o para coletar informações adicionais que podem ser identificadas durante a reunião de requisitos com a equipe dos Serviços de consultoria da Adobe. [!DNL Reference Page Tag Execution Script] O tamanho [!DNL Reference Page Tag Execution Script] é relativamente pequeno para evitar grandes adições de download às suas páginas da Web.

O seguinte [!DNL Reference Page Tag Execution Script] código é fornecido a você em um arquivo chamado [!DNL zig.js]:

```
//REFERENCE PAGE TAG 
// CONSTANTS 
var ct = "<img src="; 
var cd = "[PATH_TO_WEB_SERVER]"; //this should contain the domain of 
                               //the web site that will host the 
                                //page tag 
 
var cu = "[PATH_TO_WEB_PAGE_TAG_CODE]/zag.gif?Log=1";  
                                 //this should contain the full path to 
                                 //the zag.gif file (excluding domain) 
                                 //and include the query string of log=1 
var ce = ">"; 
var c = {}; 
c["sw"] = screen.width; 
c["sh"] = screen.height; 
c["cd"] = screen.colorDepth; 
var co = ""; 
 
for ( cKey in c ) { 
co = co+"&"+cKey+"="+escape(c[cKey]); 
} 
document.write(ct,cd,cu,co,ce); 
 
var d = {}; 
d["dt"] = document.title; 
d["dr"] = document.referrer; 
d["cb"] = new Date().getTime(); 
var vo = ""; 
 
if (typeof v != "undefined") { 
for ( vKey in v ) { 
vo = vo+"&"+vKey+"="+escape(v[vKey]); 
} 
} 
for ( dKey in d ) { 
vo = vo+"&"+dKey+"="+escape(d[dKey]); 
} 
document.write(ct,cd,cu,vo,ce); 
//END REFERENCE PAGE TAG 
```

Para facilitar a coleta de dados por meio do uso do [!DNL Reference Page Tag], conclua as seguintes etapas:

1. Crie ou coloque o arquivo de imagem de 1 pixel por 1 pixel nomeado [!DNL zag.gif] em um diretório presente no servidor da Web.
1. Modifique a variável cd para fazer referência ao domínio apropriado do seu site ou do domínio de serviços gerenciados da Adobe a partir do qual o [!DNL zag.gif] arquivo é referenciado. A referência ao arquivo é criada por meio da execução das funções do [!DNL zig.js] arquivo. Por exemplo:

   ```
   //www.mysite.com
   ```

1. Modifique a variável cu para fazer referência ao caminho apropriado para o local do [!DNL zag.gif] arquivo. Por exemplo

   ```
   /scripts
   ```

1. Verifique se os cabeçalhos de controle de cache apropriados foram estabelecidos para os arquivos [!DNL zag.gif] e [!DNL zig.js] .
