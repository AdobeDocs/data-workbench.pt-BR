---
description: A análise de big data utiliza expressões regulares (regex) para operações de pesquisa e classificação.
solution: Analytics
title: Expressões regulares
topic: Data workbench
uuid: dc8c1e88-4d95-4011-8a38-70fae0c5cf6d
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Regular expressions{#regular-expressions}

A análise de big data utiliza expressões regulares (regex) para operações de pesquisa e classificação.

No **[!UICONTROL Search]** campo, é possível realizar uma pesquisa seguindo a instrução &quot;re:&quot; usando expressões comuns, por exemplo:

```
<b>re: *.s</b>
```

<table id="table_BA125AB039794EE382B33003BE4E0AFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> metacaractere </th> 
   <th colname="col2" class="entry"> descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>. (ponto) </p> </td> 
   <td colname="col2"> <p>Corresponde a um único caractere, por exemplo: <span class="filepath"> re:x.z </span> corresponde a "xyz" ou "xxz". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>* (estrela) </p> </td> 
   <td colname="col2"> <p>Corresponde a um ou mais caracteres, por exemplo: <span class="filepath"> re:Z* </span> corresponde a "ZZZ". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>? (curinga) </p> </td> 
   <td colname="col2"> <p>Corresponde a 0 ou 1 da expressão anterior para forçar a correspondência mínima, por exemplo: <span class="filepath"> xy?z </span> corresponde a "xy" e "xyz". </p> </td> 
  </tr> 
 </tbody> 
</table>

Expressões regulares comuns adicionais também podem ser usadas para criar strings de pesquisa mais complexas. Expressões regulares são usadas em todos os campos de pesquisa da Análise de big data, incluindo os painéis da entidade de consulta.

Consulte informações detalhadas em expressões [](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html#Regular_Expressions)regulares.
