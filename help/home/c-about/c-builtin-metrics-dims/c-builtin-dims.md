---
description: A análise de big data inclui dimensões incorporadas.
solution: Analytics
title: Dimensões incorporadas
topic: Data workbench
uuid: 0aabbc52-266d-46c1-a4b3-dd575c0f2c72
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensões incorporadas{#built-in-dimensions}

A análise de big data inclui dimensões incorporadas.

A tabela a seguir lista as dimensões incorporadas disponíveis para a análise de big data:

<table id="table_40796088B3484F98889859C59D525AD7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome </th> 
   <th colname="col2" class="entry"> Detalhes </th> 
   <th colname="col3" class="entry"> Nível </th> 
   <th colname="col4" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nenhum </td> 
   <td colname="col2"> Derivado </td> 
   <td colname="col3"> N/D </td> 
   <td colname="col4">Tem um único elemento "" que se relaciona a todos os elementos de todas as dimensões. Avaliar uma métrica em Nenhum é como avaliá-la em nenhuma dimensão. <p>O <span class="filepath"> Filtro [None=""]</span> equivale a <span class="filepath"> [True]</span>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Um (Oculto) </td> 
   <td colname="col2"> Numérico </td> 
   <td colname="col3"> N/D </td> 
   <td colname="col4">O elemento "1", que também tem valor ordinal <span class="filepath"> = 1</span>, está relacionado a todos os elementos de todas as dimensões. A dimensão Um é normalmente usada para construir contagens usando esta sintaxe: <p><span class="filepath"> sum(one,Countable_Dimension)</span></p></td> 
  </tr> 
 </tbody> 
</table>

