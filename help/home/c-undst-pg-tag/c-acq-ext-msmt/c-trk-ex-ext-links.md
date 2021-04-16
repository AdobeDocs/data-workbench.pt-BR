---
description: Captura de atividades em links de sites de terceiros para permitir a análise de Saída do Target.
title: Rastrear saídas para links externos
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
exl-id: fd7434e9-cd66-408e-baa9-6a0df4039786
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 6%

---

# Rastrear saídas para links externos{#tracking-exits-to-external-links}

Captura de atividades em links de sites de terceiros para permitir a análise de Saída do Target.

As páginas da Web podem conter links para sites de terceiros e a atividade nesses links pode ser capturada para habilitar a análise de Saída do Target, especialmente no caso de o site de terceiros ser responsável por pagar taxas de referência quando tais referências forem recebidas. Como o evento click é gravado nos arquivos de log do sistema de terceiros por padrão, as modificações precisam ser feitas no link para que o evento click seja capturado localmente. O link de terceiros presente no seu site deve ser modificado da seguinte maneira:

```
<A HREF=”http://www.myserver.com/PageExit.htm?v_eurl=http://www.othersite.com”>
```

O arquivo referenciado [!DNL PageExit.htm] deve ser criado e deve ser estruturado para conter o seguinte script:

```
<html> 
<head> 
 
<script> 
function getExitURLQuery(variable) 
{ 
 
var query = window.location.search.substring(1); 
var vars = query.split("&"); 
for (var i=0; i<vars.length; i++) 
{ 
var pair = vars[i].split("="); 
if (pair[0] == variable) 
{ 
return pair[1]; 
} 
 }  
} 
</script> 
 
<script> 
location.replace(getExitURLQuery("v_eurl")); 
</script>  
 
</head> 
</html>
```

Ao fazer a solicitação para o arquivo [!DNL PageExit.htm], o valor v_eurl é coletado para fins de análise. Além disso, quando [!DNL PageExit.htm] é carregado, ele redireciona imediatamente para o local de destino v_eurl especificado.

| Dados Coletados | Explicação | Exemplo |
|---|---|---|
| v_eurl | Valor associado à variável da string de consulta v_eurl. Esse valor representa o URL de destino do link presente na página HTML. | v_eurl=www.othersite.com |
