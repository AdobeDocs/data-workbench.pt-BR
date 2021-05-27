---
description: Vários tipos de dimensões estão disponíveis no servidor do Data Workbench. Dessa forma, é importante saber o tipo de dimensão ao usar uma dimensão para criar métricas, filtros ou dimensões derivadas.
title: Tipos de dimensão
uuid: 07659373-8d9b-473d-8daa-ca8e7ac4afe8
exl-id: cbc25504-2c1c-4622-adc1-c9bbac8e12fb
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 68%

---

# Tipos de dimensão{#dimension-types}

Vários tipos de dimensões estão disponíveis no servidor do Data Workbench. Dessa forma, é importante saber o tipo de dimensão ao usar uma dimensão para criar métricas, filtros ou dimensões derivadas.

O servidor Insight pode criar e manter os seguintes tipos de dimensões:

<table id="table_1A79B6C57ED145B6AA3BB05DD37AAD1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipos de dimensão </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Contável </td> 
   <td colname="col2">Um tipo de dimensão em que o número de elementos na dimensão pode ser contado pelo sistema. As Dimensões contáveis devem ser derivadas de outras dimensões contáveis. As dimensões contáveis podem ser pais de outras dimensões ou filhos de outras dimensões contáveis. <p>Exemplos: Visitante, Sessão, Exibição de página, Reserva e Pedido. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Simples </td> 
   <td colname="col2">Uma dimensão que tem uma relação um para muitos com uma dimensão contável. Uma dimensão simples pode ser pensada como a representação de uma propriedade de elementos da dimensão pai. <p>Exemplo: Referenciador de visitantes é uma dimensão simples com um pai da dimensão Visitante. Cada Visitante pode ter apenas um Referenciador de visitantes (o primeiro referenciador HTTP), mas vários Visitantes pode ter o mesmo Referenciador de visitantes. Portanto, o Referenciador de visitantes é “um para muitos” com a dimensão Visitante. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numérico </td> 
   <td colname="col2">Uma dimensão que tem valores ordenados e numéricos e uma relação um para muitos com uma dimensão contável. Uma dimensão numérica pode ser pensada como representando uma propriedade numérica de elementos da dimensão pai. Normalmente as dimensões numéricas são usadas para definir métricas de “soma”. <p>Exemplo: a dimensão numérica Receita da sessão define a receita, em dólares, para cada Sessão. Cada Sessão tem uma única quantia de receita, mas qualquer número de Sessões pode ter a mesma receita, portanto a Receita da sessão é “um para muitos” com a Sessão. Uma métrica "Receita" pode ser definida como <span class="filepath"> sum(Session_Revenue, Sessão)</span>, fornecendo a quantia total de receita das Sessões selecionadas. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Muitas para muitas </td> 
   <td colname="col2">Uma dimensão que tem uma relação muitos para muitos com uma dimensão contável. Uma dimensão muitas para muitas pode ser pensada como representando um “conjunto” de valores para cada elemento da dimensão pai. Uma dimensão muitas para muitas equivale a uma dimensão contável (anônima) com o pai e uma dimensão Simples com um pai da dimensão contável anônima. <p>Exemplo: a dimensão muitas para muitas Frase de pesquisa tem um pai de Sessão. Cada Sessão pode usar nenhuma ou mais Frases de pesquisa e uma Frase de pesquisa pode ser usada em qualquer quantidade de Sessões. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2">uma dimensão que tem uma relação um para um com uma dimensão contável. Os nomes de elemento da dimensão denormal podem carregar informações sobre os elementos correspondentes da dimensão pai. Uma dimensão desnormalizada pode ser pensada como armazenamento de um valor de sequência de caracteres arbitrário para cada elemento do pai. As dimensões denormal podem ser usadas com o recurso de exportação de segmento do Insight Server para exportar detalhes sobre um subconjunto ou “segmento” de uma dimensão contável. Além disso, as dimensões denormal pode ser referenciadas em fórmulas de métricas e visualizações de planilhas, bem como pode ser usadas (com restrições) para definir filtros. <p>Exemplo: a dimensão denormal Endereço de email tem um pai de Visitante. Cada Visitante tem um Endereço de email e cada elemento da dimensão Endereço de email está associado a um único Visitante. Mesmo que dois visitantes tenham o mesmo endereço de email, seus endereços serão elementos diferentes da dimensão Endereço de email. Uma Exportação de segmento pode fazer referência à dimensão Endereço de email para exportar o Endereço de email de cada visitantes em um Segmento. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora </td> 
   <td colname="col2">Uma dimensão que permite criar um conjunto de dimensões de hora local periódicas ou absolutas (como Dia, Dia da semana, Hora, Hora do dia e assim por diante) com base em um campo de carimbo de data/hora especificado. Ao definir dimensões de hora, você também pode escolher um dia diferente de Segunda para ser usado como início da semana especificando a parâmetro Dia de início da semana. <p>Exemplo: a dimensão de tempo Hora da sessão tem o pai de Sessão. Portanto, a dimensão define um conjunto de dimensões de tempo (Dia, Dia da semana, Hora, Hora do dia, Mês e Semana) cujos elementos correspondem aos horários em que as sessões dos visitantes do site começaram. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Derivado </td> 
   <td colname="col2">As dimensões derivadas, em vez de serem definidas na configuração do conjunto de dados com base nos dados processados, são definidas no perfil com base em outras dimensões ou métricas. Várias dimensões derivadas são criadas automaticamente para ativar tipos diferentes de visualizações. <p>Por exemplo, quando um usuário cria um site ou mapa de processos, o Insight Server cria silenciosamente uma dimensão "Prefixo". Outras, como as dimensões de hora de relatório, são definidas por arquivos no diretório Dimensões de um perfil. </p></td> 
  </tr> 
 </tbody> 
</table>
