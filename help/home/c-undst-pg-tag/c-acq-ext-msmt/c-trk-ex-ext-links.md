---
description: Captura de atividade em links de sites de terceiros para habilitar a análise de Saída do Target.
solution: Analytics
title: Rastreamento de saídas para links externos
topic: Data workbench
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Rastreamento de saídas para links externos{#tracking-exits-to-external-links}

Captura de atividade em links de sites de terceiros para habilitar a análise de Saída do Target.

As páginas da Web podem conter links para sites de terceiros, e a atividade nesses links pode ser capturada para habilitar a análise de saída do Target, especialmente no caso de o site de terceiros ser responsável pelo pagamento de taxas de referência quando tais referências forem recebidas. Como o evento click é gravado nos arquivos de log do sistema de terceiros por padrão, é necessário fazer modificações no link para que o evento click seja capturado localmente. O link de terceiros presente em seu site deve ser modificado da seguinte forma:

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

Ao fazer a solicitação para o [!DNL PageExit.htm] arquivo, o valor v_eurl é coletado para fins de análise. Além disso, quando [!DNL PageExit.htm] é carregado, ele redireciona imediatamente para o local de destino v_eurl especificado.

| Dados Coletados | Explicação | Exemplo |
|---|---|---|
| v_eurl | Valor associado à variável da string de consulta v_eurl. Esse valor representa o URL de destino do link presente na página HTML. | v_eurl=www.othersite.com |

