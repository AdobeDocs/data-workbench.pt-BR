---
description: O processamento de arquivos XML como fontes de log para definir decodificadores para extrair dados do arquivo XML.
title: Grupos do decodificador de XML
uuid: 8fc9ab80-9a71-4fe2-a646-e830ffeb67b9
exl-id: 0b0534b7-8596-4528-a643-8a9b41dcaa33
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1295'
ht-degree: 1%

---

# Grupos do decodificador de XML{#xml-decoder-groups}

O processamento de arquivos XML como fontes de log para definir decodificadores para extrair dados do arquivo XML.

>[!NOTE]
>
>A definição de grupos do decodificador de XML para fontes de log XML requer conhecimento da estrutura e do conteúdo do arquivo XML, dos dados a serem extraídos e dos campos em que esses dados são armazenados. Esta seção fornece descrições básicas dos parâmetros que você pode especificar para decodificadores. A maneira como você usa qualquer decodificador depende do arquivo XML que contém seus dados de origem.

Para obter informações sobre os requisitos de formato para fontes de log XML, consulte [Fontes de Log](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea). Para obter assistência com a definição de decodificadores XML, entre em contato com o Adobe.

O nível superior de um decodificador XML é um grupo decodificador (XMLDecoderGroup), que é um conjunto de tabelas decodificadoras usadas para extrair dados de um arquivo XML de um formato específico. Se você tiver arquivos XML de diferentes formatos, deverá definir um grupo de decodificadores para cada formato. Cada grupo decodificador consiste em uma ou mais tabelas decodificadoras.

A tabela a seguir descreve o parâmetro Tables e todos os subparâmetros que você deve especificar para definir um grupo do decodificador de XML.

<table id="table_06C40C5149E94548A1B0C2ED4397624B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Tabelas </td> 
   <td colname="col2"> <p>Cada tabela em um grupo decodificador representa um nível de dados a serem extraídos do arquivo XML. Por exemplo, se você deseja extrair dados sobre visitantes, é possível criar uma tabela de decodificadores que consiste nas informações que você deseja extrair para cada visitante. Você também pode criar tabelas decodificadoras em tabelas decodificadoras (consulte Filhos). </p> <p> <b>Para adicionar uma tabela a um grupo decodificador</b> 
     <ul id="ul_C73CAD77440B4465B9FCE08BF4FA0749"> 
      <li id="li_C4B8CC5A85D942898F1EB76778105818"> Clique com o botão direito do mouse em <span class="uicontrol"> Tabelas </span> e clique em <span class="uicontrol"> Adicionar novo </span> &gt; <span class="uicontrol"> XMLDecoderTable </span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campos </td> 
   <td colname="col2"> <p>Os campos estendidos (por exemplo, x-trackingid, x-email) nos quais os dados são armazenados. Os dados a serem armazenados no campo são determinados pelos subcampos Path e/ou Operation . </p> <p> O Caminho é o nível do campo dentro do arquivo XML estruturado. O caminho de um campo é relativo ao caminho da tabela em que ele está definido. Os exemplos incluem <span class="filepath"> tag.tag.tag </span> ou <span class="filepath"> tag.tag.tag.tag.@attribute </span>. Observe que os caminhos fazem distinção entre maiúsculas e minúsculas. </p> <p> Uma Operação é aplicada a cada linha no caminho especificado para produzir uma saída. As seguintes operações estão disponíveis: 
     <ul id="ul_B264A411D7E3446288E7E69D62150B8B"> 
      <li id="li_5936E81C0EEF46AFB780E451A04A88E4"><b>ÚLTIMO: </b> O campo pega o valor da última ocorrência do caminho no arquivo XML. </li> 
      <li id="li_7BC4F24F2CA84C2EB64B06FE09B4CAF6"><b>RANDOM: </b> atribui um valor aleatório ao campo. Essa operação é útil se você precisar gerar uma id exclusiva, como para o campo x-trackingid . </li> 
      <li id="li_C1D34EA11BFB4859A25A275A9B63FB56"><b>HERDITA:</b> o campo definido herda seu valor do campo correspondente da tabela pai. </li> 
      <li id="li_F62FB8CD962E4E1495D9A2D5B7A78E2A"><b>"<i>constante  </i>":</b> a constante deve ser colocada entre aspas. Você pode usar uma operação constante para verificar a existência de um caminho específico; se o caminho existir, o campo recebe o valor da constante. </li> 
     </ul> </p> <p> <b>Para adicionar um campo a uma tabela de decodificador</b> </p> <p> 
     <ul id="ul_91D104D927424DEA9E788E43B2F6FEA9"> 
      <li id="li_5448B01EE82349569BBFC99C9604D7B8"> Clique com o botão direito do mouse em <span class="uicontrol"> Campos </span> e depois clique em <span class="uicontrol"> Adicionar novo </span> &gt; <span class="uicontrol"> XMLDecoderField </span>. Defina Campo, Operação e Caminho conforme apropriado. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Caminho </td> 
   <td colname="col2"> <p>O nível no arquivo XML estruturado para o qual a tabela do decodificador contém informações. Para uma tabela de decodificador XML secundário, o caminho é relativo ao caminho da tabela pai. Observe que os caminhos fazem distinção entre maiúsculas e minúsculas. </p> <p> Por exemplo, se o arquivo XML contiver a estrutura: </p> 

    &amp;lt;visitor&amp;gt;
    
    &amp;nbsp;
    
    ..
    
    &amp;nbsp;
    
    &amp;lt;/visitor&amp;gt;
    
    &amp;lt;/logdata&amp;gt;&amp;nbsp;   &lt;p> em seguida, o caminho seria &lt;span class=&quot;filepath&quot;>logdata.visitor&lt;/span> . &lt;/p> &lt;/td>
</tr> 
  <tr> 
   <td colname="col1"> Tabela </td> 
   <td colname="col2"> <p>O valor desse parâmetro deve sempre ser "Entrada de log". </p> <p> <p>Observação:  Não altere esse valor sem consultar o Adobe. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Crianças </td> 
   <td colname="col2"> <p>Opcional. Uma ou mais tabelas de decodificador incorporadas. Cada filho inclui os parâmetros Campos, Caminho e Tabela descritos acima. </p> <p> <b>Para adicionar um filho a uma tabela de decodificador</b> </p> <p> 
     <ul id="ul_902AC6CA5D66457D84CBA3194FF49BBE"> 
      <li id="li_07B4D60E7E2E4630B4878691E575936A"> Clique com o botão direito do mouse em <span class="uicontrol"> Filhos </span> e clique em <span class="uicontrol"> Adicionar novo </span> &gt; <span class="uicontrol"> XMLDecderTable </span>. Defina Campo, Operação e Caminho conforme apropriado. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Para usar um arquivo XML como uma fonte de log para um conjunto de dados, os grupos e as tabelas do decodificador de XML devem ser definidos para extrair as informações que devem ser processadas no conjunto de dados. Neste exemplo, você pode ver como definir grupos e tabelas de decodificadores para uma fonte de log XML de amostra para um conjunto de dados da Web.

O arquivo XML a seguir contém informações sobre um visitante do site, incluindo uma ID de Experience Cloud, endereço de email, endereço físico e informações sobre as exibições de página do visitante.

![](assets/xmlFile_LogSource.png)

Como temos um único arquivo XML, precisamos de apenas um grupo decodificador, que nomeamos &quot;Formato XML de Amostra&quot;. Esse grupo decodificador se aplica a qualquer outro arquivo XML do mesmo formato desse arquivo. Para começar a construir tabelas do decodificador de XML nesse grupo do decodificador, devemos primeiro determinar quais informações queremos extrair e os campos nos quais os dados serão armazenados.

Neste exemplo, extraímos informações sobre o visitante e as exibições de página associadas a esse visitante. Para fazer isso, criamos uma tabela do decodificador de XML de nível superior (pai) com informações sobre o visitante e uma tabela do decodificador de XML (filho) incorporada com informações sobre as exibições de página do visitante.

**As informações da tabela pai (visitante) são as seguintes**

* Um identificador de tipo de dados para cada linha de dados no arquivo XML. Usamos o VISITOR como nosso identificador para identificar rapidamente as linhas de dados pertencentes ao visitante e não às exibições de página. Esse valor pode ser armazenado no campo x-rowtype .
* A ID do visitante, que armazenamos no campo x-trackingid .
* O endereço de email do visitante (contact.email), que armazenamos no campo x-email.
* O status de registro do visitante. Se o visitante for um usuário registrado, podemos armazenar o valor &quot;1&quot; no campo x-is-register.
* O valor de Path é [!DNL logdata.visitor] e o valor de Table é [!DNL Log Entry]. Para obter informações sobre esses parâmetros, consulte a tabela XMLDecoderGroup acima.

**As informações para a tabela secundária (exibições de página) são as seguintes:**

* Um identificador de tipo de dados para cada linha de dados no arquivo XML. Usamos &quot;PAGEVIEW&quot; como nosso identificador para identificar rapidamente as linhas de dados pertencentes às exibições de página do visitante e não somente ao visitante. Armazenamos esse valor no campo x-rowtype .
* A ID do visitante. Esse valor é herdado da tabela pai e armazenado no campo x-trackingid .
* O carimbo de data e hora de cada exibição de página, que é armazenado no campo x-event-time .
* O URI de cada exibição de página, que é armazenado no campo cs-uri-stream.
* O valor de Caminho é pageview e o valor de Tabela é &quot;Entrada de Log&quot;. Para obter informações sobre esses parâmetros, consulte a tabela XMLDecoderGroup acima.

A captura de tela a seguir mostra uma parte do arquivo [!DNL Log Processing Dataset Include] com o grupo de decodificador de XML resultante para o arquivo XML de amostra com base na estrutura discutida das tabelas de decodificador de XML pai e filho.

![](assets/cft_LogProc_xmldecodergroup_top.png)

![](assets/cfg_LogProcessingInclude_XMLDecoderGroup_bottom.png)

Uma tabela que mostra a saída desse decodificador para nosso arquivo XML de amostra é semelhante ao seguinte:

| x-rowtype | cs—uri-stem | x-email | x-is-register | x-event-time | x-tracking-id |
|---|---|---|---|---|---|
| VISITANTE |  | foo@bar.com | 1 |  | 1 |
| PAGEVIEW | /index.html |  |  | 2006-01-01 08:00:00 | 1 |
| PAGEVIEW | / |  |  | 2006-01-01 08:00:30 | 1 |

Você pode criar uma tabela como a acima no Data Workbench usando uma interface do visualizador de campo. Para obter informações sobre a interface do visualizador de campo, consulte [Ferramentas de configuração do conjunto de dados](../../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

## Usando #value no elemento XML para ler seu valor de atributo {#section-88758428afb94f0baa5a986604d53bc1}

Agora você pode usar a tag **[!DNL #value]** em caminhos XML para obter o valor de um elemento XML.

Por exemplo, especificar anteriormente um caminho de **`<Hit><Page name="Home Page" index="20">home.html</Page></Hit>`** deixou o usuário incapaz de ler o valor da tag `<Page>`. Para ler o valor de uma tag `<Page>` e seus atributos, você pode usar [!DNL Hit.Page.@name] e [!DNL Hit.Page.@index] respectivamente. Também é possível obter o valor da tag usando a expressão **`Hit.Page.#value`**.

Por exemplo, você pode ler o valor da tag `<varValue>` adicionando o seguinte campo no decodificador:

```
7 = XMLDecoderField: 
Field = string: x-varvalue-name-added 
Operation = string: LAST 
Path = string:  
<b>#value</b> 
Path = string: varValue 
Table = string: Log Entry
```

Da mesma forma, é possível ler o valor da tag `<Rep>` adicionando o seguinte campo no decodificador:

```
7 = XMLDecoderField: 
Field = string: x-rep-name-added 
Operation = string: LAST 
Path = string: Rep.# 
<b>value</b> 
Path = string: Reps 
Table = string: Log Entry
```

Por outro lado, para ler o valor da tag de elemento sem atributo, uma tag `<text>` em uma tag `<line>` e seu valor podem ser lidos diretamente, fornecendo &quot; [!DNL text]&quot; em um caminho ou usando [!DNL line.text], dependendo de como você criou o decodificador.

```
2 = XMLDecoderField: 
Field = string: x-chat-text 
Operation = string: LAST 
Path = string:  
<b>text</b> 
Path = string:  
<b>line</b> 
Table = string: Log Entry
```
