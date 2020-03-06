---
description: Explicação dos Contadores no Dataworkbench (DWB) para projetar e implementar o esquema.
title: Estruturas Contáveis de Design de Esquema
uuid: 2530980d-1c6b-4a96-b9c1-431fc75678bb
translation-type: tm+mt
source-git-commit: 6443bdf8856ba51252685fa0c1ed65f831142956

---


# Estruturas Contáveis de Design de Esquema{#schema-design-countable-structures}

Explicação dos Contadores no Dataworkbench (DWB) para projetar e implementar o esquema.

## Compreensão Contável no Análise de big data {#section-6e6b8d1c17634d669e62c91a80a0bc62}

No nível mais alto estão dimensões contáveis. Dimensões contáveis servem duas funções principais. Primeiro, são dimensões cujos elementos você deseja contar. Em outras palavras, os contadores respondem a perguntas como:

* Quantos visitantes visitaram sua página inicial?

* Quantas visitas vieram do Google.com?

`<discoiqbr>`Normalmente, as dimensões contáveis são usadas para criar métricas de soma, que retornam a contagem, ou soma, de todos os elementos da dimensão. É possível definir dimensões contáveis para contar instâncias como reservas ou pedidos de produtos. Por exemplo, você pode definir ordens de dimensão contáveis cujos elementos (entradas de log correspondentes a pedidos da loja online) podem ser contados. Se você quiser mostrar uma contagem de ordens em uma visualização, defina a métrica de soma das ordens, que pode ser avaliada em uma dimensão ou ter filtros aplicados a ela.

As dimensões contáveis podem ser pais de outras dimensões ou filhos de outras dimensões contáveis.

Embora sua dimensão contável raiz não precise ser associada às IDs de rastreamento nos dados, a Adobe recomenda que você configure a dimensão contável raiz do conjunto de dados para usar o campo de ID de rastreamento (x-trackingid) como Chave. Como resultado, cada elemento da contagem raiz é associado a um valor exclusivo de x-trackingid, e todos os dados sobre cada elemento são agrupados.

As dimensões contáveis são definidas pelos seguintes parâmetros:

<table id="table_5E00B72CFDD645368ADCC25AB9B5E53D"> 
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
   <td colname="col2"> Nome descritivo da dimensão como aparece para o usuário na análise de big data. O nome da dimensão não pode incluir um hífen (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Comentários </p> </td> 
   <td colname="col2"> <p>Opcional. Notas sobre a dimensão estendida.

    &lt;/p> &lt;/td>
<td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Condição </p> </td> 
   <td colname="col2"> <p>As condições em que o campo de entrada contribui para a criação da dimensão contável. Se especificada, uma condição restringe o conjunto de entradas de log visíveis à dimensão e a todos os seus filhos no esquema do conjunto de dados. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Determina se a dimensão aparece na interface da análise de big data. Por padrão, esse parâmetro é definido como false. Se, por exemplo, a dimensão for usada apenas como base de uma métrica, você poderá definir esse parâmetro como verdadeiro para ocultar a dimensão da exibição da análise de big data. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chave </td> 
   <td colname="col2"> <p>Opcional. O nome do campo a ser usado como a chave. Se você definir esse parâmetro, um elemento da dimensão contável existe para cada combinação de um elemento do pai da dimensão contável e um valor distinto do campo especificado como a chave. </p> <p>Cada elemento da dimensão contável é necessário para relacionar-se a um conjunto contíguo de entradas de log. Portanto, se as entradas de log não forem ordenadas pela chave, um elemento da dimensão contável será criado sempre que o campo chave for alterado. Para evitar essa situação, a Adobe recomenda que você use uma chave exclusiva que seja contígua em ordem de tempo. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pai </td> 
   <td colname="col2"> <p> O nome da dimensão pai. Qualquer dimensão contável pode ser uma dimensão pai. Para tornar uma dimensão a dimensão de nível superior no esquema do conjunto de dados, defina o parâmetro como "raiz". A dimensão definida se torna a dimensão contável raiz do conjunto de dados. Por exemplo, se você estiver trabalhando com o Site, a dimensão Visitante será a dimensão contável raiz do conjunto de dados. </p> <p>Observação: Embora sua dimensão contável raiz não precise ser associada às IDs de rastreamento nos dados, a Adobe recomenda que você configure a dimensão contável raiz do conjunto de dados para usar o campo de ID de rastreamento (x-trackingid) como sua Chave. Como resultado, cada elemento da contagem raiz é associado a um valor exclusivo de x-trackingid, e todos os dados sobre cada elemento são agrupados. Se você quiser configurar seu conjunto de dados de forma diferente, entre em contato com a Adobe. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Este exemplo ilustra a definição de uma dimensão contável usando dados de evento coletados do tráfego do site. A dimensão contável conta os eventos de campanha da Web em uma determinada sessão. Supõe-se que todos os recursos de campanha por email sejam solicitados ao servidor da Web com &quot;email=&quot; como parte da consulta cs-uri. No exemplo, o número de vezes que o visitante responde a uma campanha de email durante uma sessão específica é de interesse, não o valor real do campo cs-uri-query(email).

![](assets/dwb_impl_arch_1.png)

A segunda grande função dos contadores é que eles formam a espinha dorsal da estrutura do esquema do conjunto de dados. Seu esquema de dados e todas as outras dimensões estão organizados para serem agrupados e pertencem a um contável. Em outras palavras, se considerarmos dimensões como &quot;categorias&quot;, então os contáveis são a forma como organizamos essas &quot;categorias&quot; em grupos.
Quando as dimensões são agrupadas em uma dimensão contável, elas devem estar no &quot;nível&quot; da dimensão contável. Por exemplo, na figura abaixo, você pode ver que &quot;Endereço de email&quot; está no nível do Visitante e &quot;Navegador&quot; no nível da Visita. &quot;Pai&quot; e &quot;filho&quot; referem-se à relação entre o contável e as dimensões agrupadas abaixo dele. Por exemplo, Visitante é um &quot;pai&quot; do endereço de email. Por outro lado, o endereço de email é um &quot;filho&quot; do Visitante. ![](assets/dwb_impl_arch_2.png) ![](assets/dwb_impl_arch_3.png)

## Criando Contável no Análise de big data {#section-491f3e8e4fbc429e95d6c97f012a208e}

Execute as seguintes etapas para criar o Contável no Dataworkbench:

1. Abrir gerenciador de perfis
1. Em Transformation folder, crie um arquivo de configuração e abra-o na estação de trabalho.
1. Em Dimensões estendidas, clique com o botão direito do mouse e escolha Adicionar novo -> Contável, conforme mostrado abaixo: ![](assets/dwb_impl_arch_4.png)

1. Informe o Nome para o novo Contável. No exemplo abaixo, Contador de clientes é definido. Se for o Nível mais alto contável, então no Pai escreva raiz. ![](assets/dwb_impl_arch_5.png)

   Se Contável não for o nível superior, então no campo pai, forneça o nome do Contável Principal. No exemplo abaixo, o Contador de envolvimento é criado e o Pai para este contável é Cliente. ![](assets/dwb_impl_arch_5.png)

Para obter informações adicionais sobre a arquitetura do Análise de big data para o design de esquema, estruturas contáveis e configurações de feed de dados offline, consulte a Interface [do esquema do](https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-dtst-sch-intrf.html) conjunto de dados e a Referência [de](../../assets/insight_sc_implementation.pdf)dimensões e métricas.
