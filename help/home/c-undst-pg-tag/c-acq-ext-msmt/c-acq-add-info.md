---
description: As variáveis de sequência de consulta podem ser adicionadas a uma solicitação JavaScript para coletar medidas adicionais quando uma solicitação é feita.
solution: Analytics
title: Adquirir informações adicionais
topic: Data workbench
uuid: 0a8075e9-4986-42c4-b505-3985b433cf8e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Adquirir informações adicionais{#acquiring-additional-information}

As variáveis de sequência de consulta podem ser adicionadas a uma solicitação JavaScript para coletar medidas adicionais quando uma solicitação é feita.

Essas variáveis podem ser adicionadas manualmente ou por script na própria página.

Informações adicionais que podem ser adquiridas de uma página podem ser adicionadas ao objeto incorporado por meio de um script usando o seguinte código como exemplo:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_pn"] = "Application Form"; 
v["_1"] = “99.99”; 
v["_2"] = "visa"; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
<noscript> 
 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
<!-- END REFERENCE PAGE TAG-->
```

Neste exemplo, as variáveis de script para v_1 e v_2 podem ser derivadas de outra função dentro da sua página da Web. As variáveis foram inseridas como exemplos. Além das medidas de linha de base adquiridas com cada solicitação, as seguintes medidas estendidas seriam adquiridas com a solicitação do URL acima:

| Dados Coletados | Explicação | Exemplo |
|---|---|---|
| v_pn= | Valor associado à variável da string de consulta v_pn | v_pn=Formulário de aplicativo |
| v_1= | Valor associado à variável da string de consulta v_1 | v_1=99.99 |
| v_2= | Valor associado à variável da string de consulta v_2 | v_2=visa |
