---
description: Usando o Modelo de objeto de documento JavaScript, métodos de script adicionais podem ser empregados para aumentar a solicitação para o arquivo ziguezague.
solution: Analytics
title: Aquisição de objetos de documento
topic: Data workbench
uuid: 7681c337-b147-4937-9d9c-0ff48d9bdd00
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aquisição de objetos de documento{#acquiring-document-objects}

Usando o Modelo de objeto de documento JavaScript, métodos de script adicionais podem ser empregados para aumentar a solicitação para o arquivo ziguezague.

Informações como o valor das tags META, os valores de ID das tags DIV e assim por diante podem ser referenciadas pelo nome e coletadas como variáveis para uso na análise. Por exemplo, para capturar dinamicamente as informações contidas no elemento META do documento HTML, você pode usar a seguinte sintaxe JavaScript:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var m0 = document.getElementsByTagName('META')[0]; //define the first instance of META 
var metacontent = m0.getAttribute('content'); //get the ‘content’ value of META 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_1"] = metacontent; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

| Dados Coletados | Explicação | Exemplo |
|---|---|---|
| v_1= | Valor associado à variável da string de consulta METAVALUE. Esse valor representa os dados dentro do elemento META do documento HTML. | v_1=Esta página fornece conteúdo relacionado à página de agradecimento da ordem. |

Após a coleta dos dados, é possível configurar o servidor da análise de big data para processar esses dados de medição para fins de análise e relatório.
