---
description: Etapas usadas para facilitar a coleta de cliques em links por meio do uso da tag de página de referência.
solution: Analytics
title: Rastreamento de cliques em links
topic: Data workbench
uuid: e4c492d2-9c90-4ed7-b997-6c50bdf98f93
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Rastreamento de cliques em links{#tracking-link-clicks}

Etapas usadas para facilitar a coleta de cliques em links por meio do uso da tag de página de referência.

Por meio da implantação do [!DNL Reference Page Tag], é possível coletar dados de medição que denotam os links (ou valores href) em que os visitantes clicam ao visitar páginas específicas. Normalmente, essa coleção não envolve a implementação de identificadores de links adicionais em suas páginas HTML.

Para facilitar a coleta de cliques em links por meio do uso do [!DNL Reference Page Tag], conclua as seguintes etapas:

1. Copie o seguinte código no arquivo existente chamado [!DNL zig.js]:

   ```
   //REFERENCE LINK AND FORM CLICK PAGE TAG 
   //INITIATE FUNCTIONS ONLOAD 
   function addEvent(obj, evType, fn){  
    if (obj.addEventListener){  
      obj.addEventListener(evType, fn, false);  
      return true;  
    } else if (obj.attachEvent){  
      var r = obj.attachEvent("on"+evType, fn);  
      return r;  
    } else {  
      return false;  
    }  
   } 
   addEvent(window, 'load', startCapture); 
   addEvent(window, 'load', startCapture); 
   function startCapture(){ 
   //TO CAPTURE LINK CLICKS 
     if (vlc == "1"){captureLink();} 
     //TO CAPTURE FORM FIELD CLICKS 
     if (vfc == "1"){captureForm();} 
   } 
   //BEGIN LINK CAPTURE PAGE TAG 
   function captureLink(){ 
     if (document.links[0]){ 
       if (document.links){ 
         var links = document.links, link, k=0; 
         while(link=links[k++]) { 
           link.onclick = captureLinkName; 
    } 
       } 
     } 
   } 
   function captureLinkName() { 
     var lc=new Image(); 
     this.parent = this.parentNode; 
     lc.src='zag2.gif?linkname=' + escape(this.name) + "&cd=" + new Date().getTime(); 
   } 
   //END LINK CAPTURE PAGE TAG 
   //BEGIN FORM CLICK CAPTURE PAGE TAG 
   function captureForm(){ 
     if (document.forms[0]) { 
       if(document.forms){ 
    for(i=0; i<document.forms[0].elements.length; i++){ 
           var forms = document.forms[0].elements[i]; 
           forms.onfocus = captureFormName; 
         } 
       } 
     } 
   } 
   function captureFormName() { 
     var fc=new Image(); 
     fc.src='zag3.gif?fieldname=' + escape(this.name) + "&cd=" + new Date().getTime(); 
   } 
   //END FORM CLICK CAPTURE PAGE TAG
   ```

1. Crie ou coloque o arquivo de imagem de 1 pixel por 1 pixel nomeado [!DNL zag2.gif] em um diretório presente no servidor da Web.
1. Modifique a [!DNL lc.src] variável para fazer referência ao domínio apropriado do site a partir do qual o [!DNL zag2.gif]arquivo é referenciado.

1. Verifique se os cabeçalhos de controle de cache apropriados foram estabelecidos para os arquivos [!DNL zag.gif] e [!DNL zig.js] .

1. Nos arquivos HTML dos quais você deseja coletar valores de cliques em links, o link [!DNL Reference Page Tag Execution Call] deve ser modificado para informar o usuário [!DNL Page Tag Execution Script] para capturar cliques em links para essa página. Para fazer isso, altere o valor da variável vlc para &quot;1&quot;, como realçado no exemplo de código a seguir:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "1" //Capture Link Click  1=TRUE, 0=FALSE 
var vfc = "0"; //Capture Form Field Click  1=TRUE, 0=FALSE 
var v = {}; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

| Dados Coletados | Explicação | Exemplo |
|---|---|---|
| v_ln= | Valor que denota a campanha de impressão | v_ln=&quot;About%20Us&quot; |

