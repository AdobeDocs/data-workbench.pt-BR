---
description: Conceitualmente, o arquivo de endereço tem a mesma finalidade do arquivo ETC&bsol;HOSTS em uma máquina em rede.
title: Locais de rede
uuid: a2097eca-dd75-4d43-b8a8-fb4c768df38d
exl-id: 938217da-8935-4f2a-b5f8-9afc1dd489f3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 2%

---

# Locais de rede{#network-locations}

{{eol}}

Conceitualmente, o arquivo de endereço tem a mesma finalidade do arquivo ETC&amp;bsol;HOSTS em uma máquina em rede.

No entanto, ao contrário do arquivo HOSTS, que descreve uma única coleção de nomes, o arquivo de endereço contém várias coleções de nomes chamadas locais de rede.

Um local de rede é uma coleção nomeada de definições de endereço. Cada definição de endereço na coleção associa um nome comum a um endereço IP.

No arquivo de endereço, um local de rede é definido em uma estrutura chamada NetworkLocation. O NetworkLocation no exemplo a seguir define um local de rede chamado &quot;MyCorporate Intranet&quot;. Ele contém uma definição de endereço que mapeia o nome comum [!DNL VS01.myCompany.com] ao endereço IP &quot;10.2.1.70&quot;.

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
```

Como mostrado no exemplo acima, a estrutura NetworkLocation consiste em três parâmetros principais:

<table id="table_9142A0EFA15E4C37975E7ACE234F6FDD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Endereços </td> 
   <td colname="col2"> Define zero ou mais AddressDefinition. Cada AddressDefintion associa um nome comum a um endereço IP. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Atribui um nome à NetworkLocation. O nome atribuído a uma NetworkLocation deve ser exclusivo no ficheiro de endereço. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pai </td> 
   <td colname="col2"> <p>Especifica o nome de outra NetworkLocation cujos membros estão incluídos nesta NetworkLocation. Este parâmetro permite que uma NetworkLocation estenda outra. </p> <p>Você pode definir o parâmetro Pai como "DNS", para estender um NetworkLocation para o sistema DNS normal do cliente. </p> <p>Exemplo: Pai = cadeia de caracteres: DNS </p> <p>Quando o DNS é o pai, os clientes tentam resolver um nome comum usando o sistema DNS da máquina cliente quando não conseguem resolver o nome por meio da NetworkLocation. </p> </td> 
  </tr> 
 </tbody> 
</table>
