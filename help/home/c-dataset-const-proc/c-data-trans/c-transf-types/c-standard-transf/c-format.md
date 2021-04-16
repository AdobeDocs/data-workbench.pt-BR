---
description: A transformação Format usa um conjunto de entradas e as formata para criar uma saída correspondente à estrutura específica.
title: Formato
uuid: c596902e-21bc-4ce6-9ca4-7ca86dfc0a6c
exl-id: 842b502e-cd16-45b3-ada8-6f2d899f1d54
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 3%

---

# Formato{#format}

A transformação Format usa um conjunto de entradas e as formata para criar uma saída correspondente à estrutura específica.

A transformação funciona em strings simples ou em vetores de string e produz a saída aplicando o formato fornecido a cada valor de entrada até que todos os valores de entrada tenham sido transformados.

<table id="table_3953C993167248AA9A47964A51C4AB5D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Nome descritivo da transformação. Você pode inserir qualquer nome aqui. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Observações sobre a transformação. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição </td> 
   <td colname="col2"> Condições de aplicação desta transformação. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Formato </td> 
   <td colname="col2"> <p>Uma string de formatação usada para especificar a aparência da saída. </p> <p> %1% refere-se a um valor do primeiro vetor de entrada, %2% refere-se a um valor do segundo vetor de entrada e assim por diante. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entradas </td> 
   <td colname="col2"> <p>Campos contendo strings simples ou vetores de string. No caso de vetores de string como entradas, a saída também será um vetor de string resultante da aplicação do parâmetro <span class="wintitle"> Format</span> para cada conjunto de valores de entrada. </p> <p> <p>Observação:  A numeração de entradas começa em 0, mas a numeração dos valores de substituição de formato começa em %1%. </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Saída </td> 
   <td colname="col2"> O nome do campo criado para conter os resultados da transformação. Se as entradas forem vetores de string, o comprimento do vetor de string de saída será o comprimento do vetor de entrada mais longo. Se alguns dos vetores de string de entrada tiverem um comprimento menor, strings vazias serão usadas para sua posição na string de formato até que o comprimento do vetor de saída seja atingido. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

Neste exemplo, dois vetores, um vetor de strings representando categorias de produto e outro um vetor de string correspondente representando a quantidade de cada produto comprado, são transformados em um único vetor de comprimento equivalente que assume a forma: Produto %1%, Quantidade %2%.

![](assets/cfg_TransformationType_Format.png)

Se os vetores de entrada contivessem categorias de produtos de (683, 918) e quantidades de (10, 4), o resultado seria um vetor de saída final contendo as duas strings seguintes: (&quot;Produto 683, Quantidade 10&quot;, &quot;Produto 918, Quantidade 4&quot;).
