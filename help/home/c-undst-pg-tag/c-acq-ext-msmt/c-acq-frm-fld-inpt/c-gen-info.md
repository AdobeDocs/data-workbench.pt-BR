---
description: Os valores inseridos em um formulário em uma página da Web podem ser coletados e anexados na sequência de consulta da página solicitada subsequentemente (no envio do formulário) por meio do uso do JavaScript.
title: Informações gerais
uuid: 401816a5-1d95-48e6-bedf-ee2a5dbd2d50
exl-id: 9effc72b-e75f-423c-87ec-6ac25edee8d6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 7%

---

# Informações gerais{#general-information}

Os valores inseridos em um formulário em uma página da Web podem ser coletados e anexados na sequência de consulta da página solicitada subsequentemente (no envio do formulário) por meio do uso do JavaScript.

Isso é mostrado no exemplo a seguir. Inclua esse JavaScript depois de qualquer script de validação de formulário usado em suas páginas HTML.

```
<html> 
<head> 
</head> 
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
for(var i = 0; i < document.formname.length; i++) 
{ 
var item = document.formname.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
formvalues += formitem + '=' + formvalue + '&'; 
} 
document.formname.action = document.formname.action + '?' + formvalues; 
 
} 
</script> 
<body> 
<form name="formname" action="thankyou.asp" method="POST" onSubmit="AppendFormValues();"> 
<input name="NAME" size="50" value=""></input>name<br/> 
<input name="CITY" size="50" value=""></input>city<br/> 
<input name="STATE" size="50" value=""></input>state<br/> 
<input name="ZIP" size="10" value=""></input>zip<br /> 
<input type="submit" name="submit" value="submit"/> 
</body> 
</html> 
```

Esse exemplo anexa os valores inseridos no formulário pelo usuário do navegador à página subsequente &quot;thankyou.asp&quot; indicada no valor da Ação de FORMULÁRIO da seguinte maneira:

```
http://www.myserver.com/thankyou.asp?v_1=John Smith&v_2=Los Angeles&v_3=California&v_4=90210
```

As seguintes medidas alargadas seriam adquiridas com este pedido, para além das medidas de base recolhidas por [!DNL Sensor]:

| Dados Coletados | Explicação | Exemplo |
|---|---|---|
| v_1 | Valor associado ao campo NAME form | v_1=John Smith |
| v_2 | Valor associado ao campo de formulário CIDADE | v_2=Los Angeles |
| v_3 | Valor associado ao campo STATE form | v_3=Califórnia |
| v_4 | Valor associado ao campo de formulário ZIP | v_4=90210 |
