---
description: Informações sobre como trabalhar com condições de filtro, incluindo a criação de um novo filtro e a adição de uma condição a um novo filtro.
title: Trabalhar com condições de filtro
uuid: a75fcb21-be5c-452a-8632-86cd78db15cb
exl-id: 15745b0c-2754-4f8b-acfd-a6bd5886ecf8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 1%

---

# Trabalhar com condições de filtro{#working-with-filter-conditions}

{{eol}}

Informações sobre como trabalhar com condições de filtro, incluindo a criação de um novo filtro e a adição de uma condição a um novo filtro.

## Criar um filtro {#section-70ba51ae625e493fa3ca70b93ffba406}

* Abra um editor de filtro no seu espaço de trabalho clicando com o botão direito do mouse **[!UICONTROL Add Visualization]** > **[!UICONTROL Filter Editor]**.

   -ou-

* Se já tiver um editor de filtro aberto e um filtro carregado, clique com o botão direito do mouse no nome do filtro atual e clique em **[!UICONTROL New Blank Filter]**.

## Adicionar uma condição a um novo filtro {#section-50986db80f1148c489630a8a63fe9f28}

1. Crie um novo filtro. Certifique-se de que o Filtro de design esteja realçado (em vez de Aplicar filtro), indicando que você está trabalhando no modo Filtro de design.
1. Clique com o botão direito do mouse na área marcada **[!UICONTROL Right-click to build filter]** e selecione uma das seguintes opções:

   * Para criar um filtro de inclusão, clique em **[!UICONTROL Include group with]**.
   * Para criar um filtro de exclusão, clique em **[!UICONTROL Exclude group with]**.

1. Selecione o tipo de condição a ser adicionada ao filtro.

   A tabela a seguir fornece descrições dos tipos de condição de filtro disponíveis:

<table id="table_3B35B57FF32349F09E91E8256FF1672A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de condição </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>seleção do espaço de trabalho </p> </td> 
   <td colname="col2"> <p>Define uma condição de filtro com base nas seleções no espaço de trabalho. Essa opção só estará disponível se uma ou mais seleções existirem no espaço de trabalho. </p> <p>Para exibir mais informações sobre a seleção, clique com o botão direito do mouse na condição e clique em <span class="uicontrol"> Exibir detalhes</span>. Uma chamada para a condição é exibida. </p> <p>Se você fizer outra seleção no espaço de trabalho, poderá adicionar a seleção como uma subcondição da primeira seleção. As seleções são agrupadas como ANDs lógicos. Portanto, os dados incluídos ou excluídos pela condição devem atender a todas as seleções de espaço de trabalho. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pelo menos um </p> </td> 
   <td colname="col2">Define uma condição de filtro com base na existência de pelo menos um (qualquer) elemento de uma dimensão que você escolher. Para editar a condição, clique com o botão direito do mouse na condição e clique em <span class="uicontrol"> Alterar</span> para. Clique em uma das dimensões disponíveis. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>fórmula </p> </td> 
   <td colname="col2"> <p>Define uma condição de filtro com base na fórmula inserida. Você deve usar a sintaxe apropriada para que o filtro funcione. </p> <p> <p>Observação: Para obter informações sobre a sintaxe para definir filtros, consulte <a href="../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> Sintaxe para expressões de filtro</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>valor da métrica </p> </td> 
   <td colname="col2"> <p>Define uma condição de filtro com base em um valor de métrica especificado. </p> <p>Para definir a condição, siga estas etapas: 
     <ul id="ul_B69D31258A36460E94535709239CD165"> 
      <li id="li_51317A681E654DD7A9D997DF9F2F22BA">Clique com o botão direito do mouse <span class="uicontrol"> [escolha o nível]</span> &gt; <span class="uicontrol"> Alterar nível</span> para selecionar o nível e a métrica de uma lista de dimensões no conjunto de dados. </li> 
      <li id="li_975E56C335824FDCB988344952DE2E9F">Clique com o botão direito do mouse <span class="uicontrol"> [escolha métrica]</span> &gt; <span class="uicontrol"> Alterar métrica</span> para selecionar a métrica de uma lista de métricas em seu conjunto de dados. </li> 
      <li id="li_D00B3AF3D8DE472C9D0E9EABBBCAAF61">Clique com o botão direito do mouse em menor que e clique em <span class="uicontrol"> Alterar comparação</span> para selecionar uma das condições de comparação disponíveis (menos do que, mais do que, exatamente, pelo menos ou no máximo). </li> 
      <li id="li_3334CE0A0950448590E5442AB243F46B">Digite o valor desejado para a métrica. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>primeiro/último </p> </td> 
   <td colname="col2"> <p>Define um filtro que permite incluir ou excluir um nível com uma dimensão especificada. Por exemplo, você pode especificar um primeiro/último filtro para incluir (ou excluir): </p> <p>Sessões cuja última Exibição de página tem uma Página de <span class="filepath"> /home/rts/Our Rates</span>. </p> <p>Para definir uma condição First/Last : 
     <ul id="ul_5AD916DA093844B8AC70127B1EB9BFC8"> 
      <li id="li_AB9FF22ADC8843A79856FED60B9478FA">Choose <span class="uicontrol"> Incluir grupo com</span> ou <span class="uicontrol"> Excluir grupo com</span> &gt; <span class="uicontrol"> primeiro/último</span> como uma nova condição no Editor de filtros. </li> 
      <li id="li_92F536FCC2A74DDE97F66C6C45ACC3DC">Clique com o botão direito do mouse <span class="uicontrol"> [escolha contêiner]</span> &gt; <span class="uicontrol"> Alterar contêiner</span> para selecionar o contêiner. </li> 
      <li id="li_1E5DBE04ABC74D84B7C0EF6886CDB5DC">Clique com o botão direito <span class="uicontrol"> first</span> ou <span class="uicontrol"> last</span> para especificar o nível. </li> 
      <li id="li_8B73EBF5D06E4513B5F0376EB2805D1C">Clique com o botão direito do mouse para especificar uma dimensão e digite um valor no campo disponível. </li> 
      <li id="li_A9E02EF6C6004DDF9B00EB853B6E54EE">Clique em <span class="uicontrol">Aplicar</span>. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

O filtro neste exemplo define um primeiro/último filtro para usuários cuja última exibição de página foi [!DNL /hme/rts/Our Rates]:

![](assets/client-fil2.png)

1. (Opcional) Para adicionar mais condições ao filtro, clique com o botão direito do mouse na área da janela onde você está criando o filtro e selecione o tipo de filtro (consulte Etapa 2) e a regra de condição (consulte Etapa 3).

   >[!NOTE]
   >
   >Várias condições de inclusão são agrupadas como ORs lógicos. Por conseguinte, os dados incluídos no filtro devem satisfazer pelo menos uma das condições de inclusão definidas. Várias condições de exclusão também são agrupadas como ORs lógicos. Para serem excluídos, os dados devem satisfazer pelo menos uma das condições de exclusão.

O filtro neste exemplo define um subconjunto de dados que consiste em visualizadores de filmes (usuários) que classificaram muitos filmes, mas não deram a nenhum filme uma pontuação alta (4 ou 5). Este filtro (adequadamente nomeado Muito difícil de agradar) consiste em duas condições:

* **Uma condição de valor de métrica:** A condição inclui usuários que classificaram pelo menos 500 filmes.
* **Uma condição de seleção de espaço de trabalho:** A condição exclui usuários que tenham dado um filme com pontuação de 4 ou 5. A chamada informa que 4 e 5 foram os elementos selecionados da dimensão de Pontuação.

![](assets/vis_FilterEditor_ExampleMovies.png)

## Excluir uma condição de filtro {#section-3092e0d7ac624885b8fe24616279de13}

>[!NOTE]
>
>Só é possível excluir condições quando você está trabalhando no modo Filtro de design . Se você tiver aplicado um filtro ao seu espaço de trabalho, clique em Filtro de design para retornar ao modo Filtro de design antes de excluir uma ou mais condições do filtro.

* Clique no botão **x** à esquerda da condição para excluí-la.

## Editar uma descrição de condição {#section-5015fd2c88ed4b6a95be7f0d53be2db0}

Você pode adicionar descrições a cada uma das condições adicionadas a um filtro. Você pode editar ou remover as descrições, conforme desejado.

>[!NOTE]
>
>As descrições das condições aparecem somente quando você está trabalhando no modo Filtro de design .

* Clique com o botão direito do mouse na condição e clique em **[!UICONTROL Edit description]**.

   * Para adicionar ou editar uma descrição, digite a descrição no [!DNL Edit condition description] campo. A descrição é exibida entre aspas acima da condição na janela do editor de filtro.

      ![](assets/vis_FilterEditor_ConditionDescription.png)

* Para remover uma descrição, clique em **[!UICONTROL Remove description]**. A condição permanece na janela do editor de filtro.
