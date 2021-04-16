---
description: As páginas da Web geralmente são estruturadas usando a linguagem de programação ASP (Ative Server Pages).
title: Informações específicas do ASP
uuid: 552288cb-b775-4121-8869-322f2a26932b
exl-id: f73235e1-d44a-4056-b1f4-a86879c19483
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# Informações específicas do ASP{#asp-specific-information}

As páginas da Web geralmente são estruturadas usando a linguagem de programação ASP (Ative Server Pages).

ASP é uma tecnologia da Microsoft que é executada no IIS (Serviços de Informações da Internet). Quando um navegador solicita um arquivo ASP, o IIS transmite a solicitação para o mecanismo ASP. O mecanismo ASP lê o arquivo ASP, linha por linha, e executa os scripts no arquivo. Finalmente, o arquivo ASP é retornado ao navegador como HTML simples. O ASP fornece objetos RESPOND ou REQUEST que, além de outros usos, permitem a resposta ou a solicitação de consultas de usuários ou dados enviados de formulários HTML.

Em certos casos, talvez você não queira anexar os valores inseridos nos formulários ao URL exibido na barra de endereços do navegador de um usuário ou que seja visível no próprio código HTML. O JavaScript simples do lado do servidor permite anexar nomes de campos de formulário e seus respectivos valores ao arquivo de log sem disponibilizá-los no navegador do usuário ou incorporá-los ao arquivo HTML. Para capturar os valores de formulário reais inseridos em formulários específicos dentro do site, algumas linhas de código devem ser adicionadas para anexar os valores do formulário à solicitação de log.

Na página de processamento de um formulário, inclua o seguinte código para anexar os valores de formulário inseridos aos dados da solicitação (além de gravar os valores de formulário enviados em um banco de dados externo ou outro local):

```
var sName= Request.Form("Name"); 
var sCity= Request.Form("City"); 
var sState= Request.Form("State"); 
var sZip= Request.Form("Zip"); 
 
Response.AppendToLog("&v_1=" +  sName); 
Response.AppendToLog("&v_2=" +  sCity); 
Response.AppendToLog("&v_3=" +  sState); 
Response.AppendToLog("&v_4=" +  sZip);
```

Esse processo anexaria os valores do formulário, conforme definido para os dados da solicitação para a página [!DNL Form Processing]. Nos dados de log, os valores anexados estariam disponíveis como sequências de consulta da página [!DNL Form Processing], conforme ilustrado abaixo. Por exemplo, v_1, v_2, v_3 e v_4 agora seriam cadeias de caracteres de consulta contendo os dados inseridos nos campos de formulário apropriados. A sintaxe descrita no exemplo acima pode ser duplicada para quaisquer campos e valores de formulário adicionais que você deseja capturar.

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Se quiser que cada campo de formulário e valor sejam capturados e disponibilizados para análise, use a seguinte sintaxe:

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues); 
```

Esse exemplo usaria todos os campos de formulário presentes no HTML junto com seus respectivos valores e os anexaria como cadeias de caracteres de consulta à entrada de log da página [!DNL Form Processing]. Observe que isso incluiria quaisquer campos ocultos presentes no formulário.

Os dados de log seriam aumentados conforme detalhado na tabela a seguir:

| Dados Coletados | Explicação | Exemplo |
|---|---|---|
| v_1 | Valor associado à sequência de consulta NAME | v_1=John Smith |
| v_2 | Valor associado à sequência de consulta CITY | v_2=Los Angeles |
| v_3 | Valor associado à sequência de consulta STATE | v_3=Califórnia |
| v_4 | Valor associado à sequência de consulta ZIP | v_4=90210 |
