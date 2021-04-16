---
description: Como parte dos dados de Avaliação da linha de base coletados, o Sensor coleta os cookies de domínio enviados de uma máquina do visitante ao fazer uma solicitação do servidor da Web.
title: Adquirir dados de medição por meio de cookies
uuid: 34cd6baf-6317-4774-8165-58208698b53c
exl-id: 37c7b5f6-33bf-4373-963a-e08a826e05df
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 2%

---

# Adquirir dados de medição por meio de cookies{#acquiring-measurement-data-through-cookies}

Como parte dos dados de Avaliação da linha de base coletados, o Sensor coleta os cookies de domínio enviados de uma máquina do visitante ao fazer uma solicitação do servidor da Web.

Isso inclui cookies persistentes e de sessão definidos pelo site quando um visitante interage com o sistema.

Na maioria dos casos, os sites configuram cookies persistentes para identificar visitantes ou capturar entradas de usuários para uso em sessões de visitante subsequentes. Qualquer informação gravada e armazenada em cookies persistentes pode ser capturada e usada juntamente com todos os outros dados de medição no servidor do Data Workbench.

Um exemplo desse cookie persistente pode envolver um identificador de cliente na forma de uma chave numérica presente em um cookie específico de domínio residente na máquina do visitante. Além de identificar o usuário como um visitante recorrente, o cookie persistente também pode ser usado para identificar ainda mais o visitante como um cliente recorrente ou para vincular o visitante às informações contidas em um banco de dados do cliente para permitir que as informações demográficas do cliente offline sejam exibidas dentro de [!DNL Site] e usadas para análise interativa.

Os cookies de sessão podem ser um bom mecanismo para coletar informações do usuário por meio de campos de formulário ou outros elementos interativos dinâmicos em seu site. No caso de um site que implementa formulários para capturar dados de entrada específicos do usuário, as informações permanecem no cookie da sessão somente enquanto a sessão estiver ativa. Quando um usuário deixa seu site ou, em seguida, encerra uma sessão, as informações não são mais armazenadas no computador do usuário. No entanto, as informações inseridas são capturadas por [!DNL Sensor] e disponibilizadas como dados de medição em [!DNL Site].

A seguir, um exemplo de uso de um cookie de sessão para capturar uma única variável de formulário inserida por um visitante.

```
<html> 
<head> 
<title>Cookie Collection </title> 
 
<script language="JavaScript"> 
function AppendFormValues() 
{ 
 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
document.cookie = cookie; 
 
testform.submit(); 
 
} 
</script> 
</head> 
<body> 
<form name="testform" method="post" action="nextpage.asp"> 
<input type="text" size=15 name="name"><br />enter name 
<br><br> 
 
<a href="javascript:AppendFormValues();">Click Here To </a><br /><br /> 
<br /><br /><br /> 
 
</body> 
</html> 
```

Neste exemplo, uma função é chamada para definir um cookie de sessão no computador do visitante com o nome do campo e o valor inserido no campo de formulário. Conforme o formulário é enviado e a página da Web subsequente é solicitada, o conjunto de cookies da sessão é passado para o servidor da Web e coletado por [!DNL Sensor]. Os seguintes dados estão disponíveis no servidor do Data Workbench para uso na análise de dados:

| Dados Coletados | Explicação | Exemplo |
|---|---|---|
| v_1 | Valor associado ao cookie v_1. Esse valor representa o NOME inserido no campo de formulário que resultou na definição do cookie de sessão. | v_1=John Smith |

Os cookies de sessão também podem ser utilizados para capturar iterativamente campos de formulário ou uma variedade de variáveis JavaScript incorporadas presentes em uma página HTML. No exemplo a seguir, o JavaScript é usado para capturar recursivamente qualquer campo de formulário presente em um arquivo HTML e definir um cookie de sessão com os pares de nome=valor apropriados.

```
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
var cookie="formcookie="; 
for (i=0; i<document.testform.length; i++){ 
if (document.testform.elements[i].type =="radio") {            
if (document.testform.elements[i].checked){ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
else if (document.testform.elements[i].type =="select") { 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var optionindex = eval(document.testform.elements[i].selectedIndex); 
var formvalue = document.testform.elements[i].options[optionindex].value;             
cookie += formitem + "=" + formvalue + "&"; 
} 
else{ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
document.cookie = cookie; 
document.testform.submit(); 
} 
 
</script>
```

Neste exemplo, um cookie de sessão é definido no computador do visitante com o nome e o valor de cada campo de formulário existente no formulário. Isso inclui campos de entrada, caixas de seleção, botões de opção, caixas de seleção e áreas de texto. Como você pode notar neste exemplo, como o número de campos de formulário é desconhecido, é necessário capturar todos os nomes de formulário e valores de campo como uma única string, delimitada por um E comercial (&amp;). Essa etapa deve ser realizada devido a um limite no número de cookies que um usuário pode ter em seu computador em um momento. O Microsoft Internet Explorer permite que apenas vinte (20) cookies de sessão estejam presentes antes de começar a soltar o mais antigo.
