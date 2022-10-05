---
description: Informações conceituais sobre expressões de planilhas e uso de referências de células.
title: Expressões de planilhas
uuid: be57d6bd-3e13-4c90-9034-8e0f2b8315aa
exl-id: 1ff3ec24-0363-4b6c-8c91-31e49ed0f7c4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 2%

---

# Expressões de planilhas{#worksheet-expressions}

{{eol}}

Informações conceituais sobre expressões de planilhas e uso de referências de células.

A planilha a seguir fornece detalhes sobre os visitantes que visualizam a página Assistente de aplicativos fornecida no formulário de aplicativo online do site de um banco.

![](assets/client-wkst.png)

* A coluna A mostra uma lista das categorias de visitantes que estão sendo avaliados: visitantes, visitantes de referência e visitantes de referência A.
* A coluna B mostra o número de visitantes em cada categoria que visualizaram a página Aplicar agora.
* A Coluna C mostra os visitantes que visualizaram as páginas Aplicar agora e Assistente de aplicativo.
* A coluna D contém as porcentagens dos visualizadores do Aplicar agora nas três categorias que também visualizaram a página Assistente de aplicativos .

A planilha mostra que aproximadamente 55% dos visitantes referenciados pelo Referenciador A que visualizaram a página Aplicar agora também visualizaram a página Assistente de aplicativo.

A tabela a seguir fornece fórmulas de exemplo para a planilha no exemplo anterior:

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
   <td colname="col2"> <p><span class="filepath"> =Visitors[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B3 </p> <p>Visitantes referenciados que visualizaram a página Aplicar agora </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B4 </p> <p>Visitantes referenciados do Referenciador A que visualizaram a página Aplicar agora </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp" </span> </p> <p> E <span class="filepath"> Referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C2 </p> <p>Visitantes que visualizaram a página Aplicar agora e a página Assistente de aplicativo </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitors[Page="/applynow/default.asp" </span> </p> <p> E <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C3 </p> <p>Visitantes referenciados que visualizaram a página Aplicar agora e a página Assistente de aplicativo </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp" </span> </p> <p> E <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C4 </p> <p>Visitantes referenciados do Referenciador A que visualizaram a página Aplicar agora e a página Assistente de aplicativo </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp"</span> </p> <p> E <span class="filepath"> Page="/applynow/appwizard.asp"</span> </p> <p> E <span class="filepath"> Referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D2 </p> <p>Porcentagem de visitantes que visualizaram a página Aplicar agora e a página Assistente de aplicativo </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C2/B2*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D3 </p> <p>Porcentagem de visitantes referenciados que visualizaram a página Aplicar agora e a página Assistente de aplicativo </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C3/B3*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D4 </p> <p>Porcentagem de visitantes referenciados do Referenciador A que visualizaram a página Aplicar agora e a página Assistente de aplicativo </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C4/B4*100</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

Assim como em outras visualizações, as planilhas são atualizadas automaticamente quando você faz uma seleção em outra visualização no espaço de trabalho. Para obter mais informações sobre como fazer seleções, consulte [Fazer seleções em visualizações](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

No exemplo de dados da Web a seguir, vários dias de dados de sessão foram selecionados na visualização Sessões por dia . A planilha mostra que, durante o período selecionado, aproximadamente 69% dos visitantes do Referenciador A que visualizaram a página Aplicar agora também visualizaram a página Assistente de aplicativos . Sem essa seleção (como mostrado no exemplo acima), aproximadamente 55% dos visitantes do Referenciador A visualizaram a página Aplicar Agora, bem como a página Assistente de Aplicativo.

![](assets/client-exp.png)

## Uso de referências de célula {#section-0004e315c9c94d359b1a8a39794ba555}

É possível substituir qualquer string, seja ela própria ou em outra expressão da planilha, por uma referência de célula.

* **Referência de célula simples:** A célula A2 contém o texto Visitantes, que é usado como um cabeçalho. A célula B2 contém [!DNL eval(A1)], que avalia como [!DNL =Visitors].

* **Filtrar referência da célula:** A célula A5 contém a data de ontem. A célula B5 contém [!DNL Visitors[ Day=A5 ]], que avalia o número de Visitantes ontem.

* **Referência de célula concatenada:** A célula A5 contém a data de hoje e a Célula A6 contém o período de 8:00 a 8:59 de uma hora. A célula B6 contém [!DNL Visitors[ Hour=A5+” ”+A6 ]], que avalia o número de Visitantes hoje entre as 8h e 9h.
