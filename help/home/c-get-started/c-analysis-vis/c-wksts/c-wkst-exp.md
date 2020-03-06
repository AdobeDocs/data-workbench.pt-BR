---
description: Informações conceituais sobre expressões de planilhas e uso de referências de células.
solution: Analytics
title: Expressões de planilha
topic: Data workbench
uuid: be57d6bd-3e13-4c90-9034-8e0f2b8315aa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Expressões de planilha{#worksheet-expressions}

Informações conceituais sobre expressões de planilhas e uso de referências de células.

A planilha a seguir fornece detalhes sobre os visitantes que visualizam a página Assistente de aplicativos fornecida no formulário de aplicativo online do site de um banco.

![](assets/client-wkst.png)

* A coluna A mostra uma lista das categorias de visitantes que estão sendo avaliados: visitantes, visitantes de referência e visitantes de referência do Referenciador A.
* A coluna B mostra o número de visitantes em cada categoria que visualizaram a página Aplicar agora.
* A coluna C mostra os visitantes que visualizaram as páginas Aplicar agora e Assistente de aplicativos.
* A coluna D contém as porcentagens dos visualizadores Aplicar agora nas três categorias que também visualizaram a página Assistente de aplicativos.

A planilha mostra que aproximadamente 55% dos visitantes que fizeram referência ao Referenciador A que visualizaram a página Aplicar agora também visualizaram a página Assistente de aplicativos.

A tabela a seguir fornece fórmulas de amostra para a planilha no exemplo anterior:

<table id="table_0F5EFDB58040465AB599E6BE93324822"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Célula da Planilha </th> 
   <th colname="col2" class="entry"> Fórmula </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>B2 </p> <p>Visitantes que visualizaram a página Aplicar agora </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Visitantes[Página="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B3 </p> <p>Visitantes referenciados que visualizaram a página Aplicar agora </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B4 </p> <p>Visitantes referenciados do Referenciador A que visualizaram a página Aplicar agora </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Página="/applynow/default.asp" </span> </p> <p> E <span class="filepath"> Referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C2 </p> <p>Visitantes que visualizaram a página Aplicar agora e a página Assistente de aplicativos </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitantes[Página="/applynow/default.asp" </span> </p> <p> AND <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C3 </p> <p>Visitantes referenciados que visualizaram a página Aplicar agora e a página Assistente de aplicativos </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Página="/applynow/default.asp" </span> </p> <p> AND <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C4 </p> <p>Visitantes referenciados do Referenciador A que visualizaram a página Aplicar agora e a página Assistente de aplicativos </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Página="/applynow/default.asp"</span> </p> <p> AND <span class="filepath"> Page="/applynow/appwizard.asp"</span> </p> <p> E <span class="filepath"> Referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D2 </p> <p>Porcentagem de visitantes que visualizaram a página Aplicar agora e a página Assistente de aplicativos </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C2/B2*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D3 </p> <p>Porcentagem de visitantes referenciados que visualizaram a página Aplicar agora e a página Assistente de aplicativos </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C3/B3*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D4 </p> <p>Porcentagem de visitantes referenciados do Referenciador A que visualizaram a página Aplicar agora e a página Assistente de aplicativos </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C4/B4*100</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

Assim como em outras visualizações, as planilhas são atualizadas automaticamente quando você faz uma seleção em outra visualização no espaço de trabalho. Para obter mais informações sobre como fazer seleções, consulte [Fazer seleções em visualizações](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

No exemplo de dados da Web a seguir, vários dias de dados de sessão foram selecionados na visualização Sessões por dia. A planilha mostra que durante o período selecionado, aproximadamente 69% dos visitantes do Referenciador A que visualizaram a página Aplicar agora também visualizaram a página Assistente de aplicativos. Sem essa seleção (como mostrado no exemplo acima), aproximadamente 55% dos visitantes do Referenciador A visualizaram a página Aplicar agora, bem como a página Assistente de aplicativos.

![](assets/client-exp.png)

## Usando Referências de Célula {#section-0004e315c9c94d359b1a8a39794ba555}

É possível substituir qualquer string, seja ela própria ou dentro de outra expressão na planilha, por uma referência de célula.

* **Referência de célula simples:** A célula A2 contém o texto Visitantes, que é usado como um cabeçalho. A célula B2 contém [!DNL eval(A1)], o que resulta em [!DNL =Visitors].

* **Filtrar referência de célula:** A célula A5 contém a data de ontem. A célula B5 contém [!DNL Visitors[ Day=A5 ]], que avalia o número de Visitantes ontem.

* **Referência de célula concatenada:** A célula A5 contém a data de hoje e a célula A6 contém o período de 8:00 a 8:59 de uma hora. A célula B6 contém [!DNL Visitors[ Hour=A5+&quot;+A6 ]], que avalia o número de Visitantes hoje entre as 8h00 e as 9h00.

