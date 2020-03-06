---
description: Como parte dos dados de Avaliação da linha de base coletados, o Sensor coleta os cookies de domínio enviados de uma máquina do visitante ao fazer uma solicitação do servidor da Web.
solution: Analytics
title: Aquisição de dados de avaliação por meio de cookies
topic: Data workbench
uuid: 34cd6baf-6317-4774-8165-58208698b53c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aquisição de dados de avaliação por meio de cookies{#acquiring-measurement-data-through-cookies}

Como parte dos dados de Avaliação da linha de base coletados, o Sensor coleta os cookies de domínio enviados de uma máquina do visitante ao fazer uma solicitação do servidor da Web.

Isso inclui cookies persistentes e de sessão que seu site define quando um visitante interage com seu sistema.

Na maioria dos casos, os sites definem cookies persistentes para identificar visitantes ou capturar entradas de usuários para uso em sessões subsequentes do visitante. Qualquer informação gravada e armazenada em cookies persistentes pode ser capturada e usada juntamente com todos os outros dados de medição no servidor de análise de big data.

Um exemplo desse cookie persistente pode envolver um identificador de cliente na forma de uma chave numérica presente em um cookie específico do domínio que reside na máquina do visitante. Além de identificar o usuário como um visitante recorrente, o cookie persistente também pode ser usado para identificar ainda mais o visitante como um cliente recorrente ou para vincular o visitante às informações contidas em um banco de dados do cliente para permitir que as informações demográficas do cliente offline sejam exibidas dentro [!DNL Site] e usadas para análise interativa.

Os cookies da sessão podem ser um bom mecanismo para coletar a entrada do usuário por meio de campos de formulário ou outros elementos interativos dinâmicos dentro do seu site. No caso de um site que implementa formulários para capturar dados de entrada específicos do usuário, as informações permanecerão no cookie da sessão apenas enquanto a sessão estiver ativa. Quando um usuário sai de seu site ou encerra uma sessão posteriormente, as informações não são mais armazenadas no computador do usuário. No entanto, as informações inseridas são captadas [!DNL Sensor] e disponibilizadas como dados de medição no interior [!DNL Site].

Veja a seguir um exemplo de como usar um cookie de sessão para capturar uma única variável de formulário inserida por um visitante.

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

Neste exemplo, uma função é chamada para definir um cookie de sessão no computador do visitante com o nome do campo e o valor digitado no campo de formulário. Conforme o formulário é enviado e a página da Web subsequente é solicitada, o conjunto de cookies da sessão é passado para o servidor da Web e coletado por [!DNL Sensor]. Os seguintes dados estão disponíveis no servidor da análise de big data para uso na análise de dados:

| Dados Coletados | Explicação | Exemplo |
|---|---|---|
| v_1 | Valor associado ao cookie v_1. Esse valor representa o NOME inserido no campo de formulário que resultou na definição do cookie da sessão. | v_1=John Smith |

Os cookies de sessão também podem ser utilizados para capturar repetidamente campos de formulário ou uma variedade de variáveis JavaScript incorporadas presentes em uma página HTML. No exemplo a seguir, o JavaScript é usado para capturar recursivamente qualquer campo de formulário presente em um arquivo HTML e definir um cookie de sessão com os pares de nome=valor apropriados.

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

Neste exemplo, um cookie de sessão é definido no computador do visitante com o nome e o valor de cada campo de formulário existente no formulário. Isso inclui campos de entrada, caixas de seleção, botões de opção, caixas de seleção e áreas de texto. Como você pode observar neste exemplo, como o número de campos de formulário é desconhecido, é necessário capturar todos os valores de nome de formulário e de campo como uma única string, delimitada por um E comercial. Esta etapa deve ser realizada devido a um limite no número de cookies que um usuário pode ter no computador em um determinado momento. O Microsoft Internet Explorer permite que apenas vinte (20) cookies de sessão estejam presentes antes de começar a soltar o mais antigo.
