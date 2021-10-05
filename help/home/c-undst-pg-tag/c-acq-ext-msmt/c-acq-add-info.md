---
description: As variáveis da sequência de consulta podem ser adicionadas a uma solicitação do JavaScript para coletar medidas adicionais quando uma solicitação é feita.
title: Adquirir informações adicionais
uuid: 0a8075e9-4986-42c4-b505-3985b433cf8e
exl-id: ad4f5e08-b7b7-4de3-b0c2-71440facb2d1
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 4%

---

# Adquirir informações adicionais{#acquiring-additional-information}

As variáveis da sequência de consulta podem ser adicionadas a uma solicitação do JavaScript para coletar medidas adicionais quando uma solicitação é feita.

Essas variáveis podem ser adicionadas manualmente ou por script na própria página.

Informações adicionais que podem ser adquiridas de uma página podem ser adicionadas ao objeto incorporado por meio do script usando o seguinte código como exemplo:

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE
var v = {};
v["_pn"] = "Application Form";
v["_1"] = “99.99”;
v["_2"] = "visa";
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>
<noscript>

<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>
<!-- END REFERENCE PAGE TAG-->
```

Neste exemplo, as variáveis de script para v_1 e v_2 podem ser derivadas de outra função na página da Web. As variáveis foram inseridas como exemplos. Além das medidas de linha de base adquiridas com cada solicitação, as seguintes medidas estendidas seriam adquiridas com a solicitação do URL acima:

| Dados Coletados | Explicação | Exemplo |
|---|---|---|
| v_pn= | Valor associado à variável da string de consulta v_pn | v_pn=Formulário de aplicativo |
| v_1= | Valor associado à variável da string de consulta v_1 | v_1=99.99 |
| v_2= | Valor associado à variável da string de consulta v_2 | v_2=visa |
