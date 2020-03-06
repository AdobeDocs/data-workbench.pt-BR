---
description: Geralmente, as páginas da Web são estruturadas usando a linguagem de programação ASP (Ative Server Pages).
solution: Analytics
title: Informações específicas do ASP
topic: Data workbench
uuid: 552288cb-b775-4121-8869-322f2a26932b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Informações específicas do ASP{#asp-specific-information}

Geralmente, as páginas da Web são estruturadas usando a linguagem de programação ASP (Ative Server Pages).

O ASP é uma tecnologia da Microsoft que é executada dentro do IIS (Internet Information Services). Quando um navegador solicita um arquivo ASP, o IIS transmite a solicitação para o mecanismo ASP. O mecanismo ASP lê o arquivo ASP, linha por linha, e executa os scripts no arquivo. Por fim, o arquivo ASP é retornado ao navegador como HTML simples. O ASP fornece objetos RESPOND ou REQUEST que, além de outros usos, permitem a resposta ou a solicitação de consultas de usuários ou dados enviados de formulários HTML.

Em certos casos, talvez você não queira anexar os valores inseridos nos formulários ao URL que é exibido na barra de endereços do navegador de um usuário ou que é visível no próprio código HTML. O JavaScript simples do lado do servidor permite anexar nomes de campos de formulário e seus respectivos valores ao arquivo de log sem disponibilizá-los no navegador do usuário ou incorporá-los ao arquivo HTML. Para capturar os valores de formulário reais inseridos em formulários específicos dentro do site, algumas linhas de código devem ser adicionadas para anexar os valores de formulário à solicitação de log.

Na página de processamento de um formulário, inclua o seguinte código para anexar os valores de formulário inseridos aos dados de solicitação (além de gravar os valores de formulário enviados em um banco de dados externo ou em outro local):

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

Esse processo anexaria os valores do formulário, conforme definido para os dados da solicitação para a [!DNL Form Processing] página. Nos dados de log, os valores anexados estariam disponíveis como sequências de consulta da [!DNL Form Processing] página, conforme ilustrado abaixo. Por exemplo, v_1, v_2, v_3 e v_4 agora são strings de consulta que contêm os dados inseridos nos campos de formulário apropriados. A sintaxe descrita no exemplo acima pode ser duplicada para quaisquer campos de formulário e valores adicionais que você deseja capturar.

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Se quiser que todos os campos e valores de formulário sejam capturados e disponibilizados para análise, use a seguinte sintaxe:

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues); 
```

Esse exemplo pegaria todos os campos de formulário presentes no HTML junto com seus respectivos valores e os anexaria como sequências de consulta à entrada de log da [!DNL Form Processing] página. Observe que isso incluiria quaisquer campos ocultos presentes no formulário.

Os dados de log seriam aumentados conforme detalhado na tabela a seguir:

| Dados Coletados | Explicação | Exemplo |
|---|---|---|
| v_1 | Valor associado à string de consulta NAME | v_1=John Smith |
| v_2 | Valor associado à string de consulta CITY | v_2=Los Angeles |
| v_3 | Valor associado à string de consulta STATE | v_3=Califórnia |
| v_4 | Valor associado à string de consulta ZIP | v_4=90210 |

