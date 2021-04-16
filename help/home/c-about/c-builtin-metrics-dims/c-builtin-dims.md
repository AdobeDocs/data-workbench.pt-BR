---
description: O Data Workbench inclui dimensões incorporadas.
title: Dimensões embutidas
uuid: 0aabbc52-266d-46c1-a4b3-dd575c0f2c72
exl-id: c08a487d-60b8-4db7-8776-7ae1b9f1f27c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 14%

---

# Dimensões embutidas{#built-in-dimensions}

O Data Workbench inclui dimensões incorporadas.

A tabela a seguir lista as dimensões internas disponíveis para o Data Workbench:

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
   <td colname="col4">Possui um único elemento "" que se relaciona a todos os elementos de todas as dimensões. Avaliar uma métrica sobre Nenhum é como avaliá-la em nenhuma dimensão. <p>O <span class="filepath"> Filtro [None="]</span> é equivalente a <span class="filepath"> [True]</span>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Um (Oculto) </td> 
   <td colname="col2"> Numérico </td> 
   <td colname="col3"> N/D </td> 
   <td colname="col4">O elemento "1", que também tem o valor ordinal <span class="filepath"> = 1</span>, está relacionado a todos os elementos de todas as dimensões. Normalmente, a dimensão Um é usada para construir contagens usando essa sintaxe: <p><span class="filepath"> sum(one,Countable_Dimension)</span></p></td> 
  </tr> 
 </tbody> 
</table>
