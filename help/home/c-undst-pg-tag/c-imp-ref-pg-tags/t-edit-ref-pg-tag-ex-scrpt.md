---
description: A tag de página de referência consiste em um script de execução de tag de página que reside em um servidor da Web e, quando chamado, resulta na coleta de todos os dados do lado do cliente para a página solicitada pelo visitante do site.
title: Editar o script de execução de tag da página de referência
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
exl-id: bc922b59-716e-4e92-84b5-59a52620df03
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 7%

---

# Editar o script de execução de tag da página de referência{#editing-the-reference-page-tag-execution-script}

{{eol}}

A tag de página de referência consiste em um script de execução de tag de página que reside em um servidor da Web e, quando chamado, resulta na coleta de todos os dados do lado do cliente para a página solicitada pelo visitante do site.

Você pode modificar o [!DNL Reference Page Tag Execution Script] para coletar informações adicionais que podem ser identificadas durante a reunião de requisitos com a equipe do Adobe Consulting Services. O [!DNL Reference Page Tag Execution Script] tem um tamanho relativamente pequeno para evitar grandes adições de download às suas páginas da Web.

O seguinte [!DNL Reference Page Tag Execution Script] é fornecido a você em um arquivo chamado [!DNL zig.js]:

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

Para facilitar a recolha de dados através da utilização da variável [!DNL Reference Page Tag], execute as seguintes etapas:

1. Crie ou coloque o arquivo de imagem de 1 pixel por 1 pixel com o nome [!DNL zag.gif] em um diretório presente no servidor da Web.
1. Modifique a variável cd para fazer referência ao domínio apropriado de seu site ou domínio de serviços gerenciados pelo Adobe do qual a variável [!DNL zag.gif] o arquivo é referenciado. A referência ao arquivo é criada por meio da execução do [!DNL zig.js] funções de arquivo. Por exemplo:

   ```
   //www.mysite.com
   ```

1. Modifique a variável cu para fazer referência ao caminho apropriado para o local da variável [!DNL zag.gif] arquivo. Por exemplo

   ```
   /scripts
   ```

1. Certifique-se de que os cabeçalhos de controle de cache apropriados sejam estabelecidos para o [!DNL zag.gif] e [!DNL zig.js] arquivos.
