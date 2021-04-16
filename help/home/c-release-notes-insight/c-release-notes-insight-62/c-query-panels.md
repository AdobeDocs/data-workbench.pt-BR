---
description: Use os painéis do Localizador no Data Workbench para selecionar métricas, dimensões e filtros. Esses painéis fornecem suporte de pesquisa, opções de classificação e recursos de arrastar e soltar.
title: Localizadores
uuid: 7a4144f5-133f-48ed-9613-1e42b1313120
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 2%

---


# Localizadores{#finders}

Use os painéis do Localizador no Data Workbench para selecionar métricas, dimensões e filtros. Esses painéis fornecem suporte de pesquisa, opções de classificação e recursos de arrastar e soltar.

Um painel Localizador pode ser aberto na barra lateral esquerda ou em um espaço de trabalho.

![](assets/query_entity_panel_main.png)

<table id="table_3E43DBA0646842898F14F31374F9E39C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Localizador de Dimension </th> 
   <th colname="col2" class="entry"> Localizador de métricas </th> 
   <th colname="col3" class="entry"> Localizador de filtros </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Uma lista de todas as dimensões no modelo de query. </p><img placement="break" id="image_D7D317D84C0843BE8D324E5B9F7AF20D" src="assets/query_entity_dim_panel.png" /> </td> 
   <td colname="col2"> <p>Uma lista de todas as métricas no modelo de consulta. </p><img placement="break" id="image_04553B2F2C6A48FE897B4EFF002BED59" src="assets/query_entity_metric_panel.png" /> </td> 
   <td colname="col3"> <p>Uma lista de todos os filtros criados para sua organização. </p><img placement="break" id="image_920E72D795644634A82D1955CB64B355" src="assets/query_entity_filters_panel.png" /> </td> 
  </tr> 
 </tbody> 
</table>

**Para abrir um Localizador:**

* Clique com o botão direito do mouse em um espaço de trabalho e selecione **[!UICONTROL Tools]** > **[!UICONTROL Finder]**.

   O painel Localizador com guias para Métricas, Dimension e Filtros será aberto no espaço de trabalho.

* Clique com o botão direito do mouse na barra lateral esquerda e selecione **[!UICONTROL Add]** > **[!UICONTROL Finder]**.

   O painel Localizador será aberto no painel esquerdo.

O **Localizador** inclui os seguintes recursos:

<table id="table_072047E919204577AE85789BAE0F4EE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recursos do Localizador </th> 
   <th colname="col2" class="entry"> Detalhes </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Arrastar e soltar</b> </td> 
   <td colname="col2"> <p> Você pode arrastar e soltar dimensões ou métricas do painel para uma visualização no espaço de trabalho para alterar a dimensão ou adicionar novas métricas. </p> 
    <ol id="ol_612DC76EC04C4FCE938B20B388C43CE8"> 
     <li id="li_7F73B781141E4B8CAE9800F580F62E44">Mantenha pressionadas as teclas <span class="uicontrol"> &lt;Ctrl&gt;</span> e <span class="uicontrol"> &lt;Alt&gt;</span> e selecione a dimensão ou métrica no painel Localizador. </li> 
     <li id="li_631D57976F71415AA61F33EBBFDD128A">Arraste uma nova dimensão do painel e solte-a na visualização para alterar ou adicionar dimensões. </li> 
     <li id="li_5329FB82225F46EBBE3A996A641058DE">Para adicionar métricas, arraste uma nova métrica do painel e solte-a no cabeçalho da métrica da visualização selecionada. </li> 
    </ol> <p>Isso funcionará para todas as visualizações relevantes, incluindo tabelas, cluster de visitantes, matriz de correlação, gráficos de dispersão e o gráfico de barras 2D (dependendo do eixo). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Pesquisar</b> </td> 
   <td colname="col2">Uma caixa <span class="uicontrol"> Pesquisar</span> nos painéis do Localizador permite filtrar nomes para Dimension, Métricas e Filtros. 
    <ul id="ul_0F6F377E9906472E99008EBE7483F689"> 
     <li id="li_75857895EDB045C8B2960393854B257D"> <p>Correspondência de padrão (pesquisa glob simples). Comece a digitar o nome de uma dimensão, métrica ou entidade de filtro necessária no campo Pesquisar e somente as strings correspondentes contidas em qualquer lugar do nome serão filtradas e exibidas no painel Localizadores . </p> <p>Por exemplo, digite: </p> <code><b>Search:</b>click</code> <p>Você pode obter os seguintes resultados no Localizador do Dimension: </p> <p><img placement="break" id="image_7CBAAABA92BB47658B7F9F5C0263CF20" src="assets/finders_glob_search.png" /> </p> <p>A correspondência padrão permite usar caracteres curingas, como . (ponto), "?" e "*" (estrela). </p> </li> 
     <li id="li_044F9EC1399B44CD81E1852F85137704"> <p>Expressões regulares. Expressões regulares mais complexas também são compatíveis com recursos de pesquisa adicionados. Adicione o prefixo "re:" antes do termo de pesquisa (sem espaços) para interpretar como uma expressão regular. </p> <p>Por exemplo, digite: </p> <code><b>Search:</b>re.*ip</code> <p>Você pode obter os seguintes resultados no Localizador do Dimension: </p> <p><img placement="break" id="image_F47DB90B36504997AA1C509855B89A47" src="assets/finders_regex_search.png" /> </p> </li> 
    </ul> <p>Para obter informações de pesquisa aprofundadas, consulte <a href="https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-reg-exp.html" format="http" scope="external"> expressões regulares</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Tipo de Dimension</b> </td> 
   <td colname="col2">Na guia Dimension , é possível clicar com o botão direito do mouse no cabeçalho da guia para classificar pelo tipo de dimensão. <p><img id="image_FB44D0F4D36B4AD7A6165E0432211AB6" placement="break" src="assets/query_entity_search_types.png" /> 
     <ul id="ul_D36B8474730F4859BC7AA015CC1B8EF0"> 
      <li id="li_4AE1D5699D0E45AF880A134F886B8B19">Atributos — Dimension criadas com base nas características do visitante, produtos, geografia, tempo, vídeo e outros atributos. </li> 
      <li id="li_0B2A08F8CBE94356AC506F95DC268C47">Clusters — Dimension no construtor de cluster. </li> 
      <li id="li_4BC3396A680B49A4B6BDAAD066826864">Pontuações — Dimension criadas dentro da pontuação de propensão. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Rótulo</b> </td> 
   <td colname="col2">Em cada guia, clique com o botão direito do mouse e selecione <span class="uicontrol"> Label</span> para renomear o painel Localizador. <p><img placement="break" id="image_F61C57F6548646069242DFB2490C67B9" src="assets/label_change.png" /> </p> <p>Os rótulos Dimension, Métricas e Filtros padrão podem ser alterados para um nome de guia que atenda às convenções de sua organização. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Adicionar Item</b> </td> 
   <td colname="col2">Em cada guia, é possível clicar com o botão direito do mouse e selecionar <span class="uicontrol"> Adicionar item</span> para abrir uma tabela e adicionar manualmente Dimension, métricas e filtros. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Barra de localizadores</b> </td> 
   <td colname="col2">Clique com o botão direito do mouse na barra <span class="uicontrol"> Localizadores</span> na barra lateral esquerda para abrir um menu para obter recursos adicionais. <p><img placement="break" id="image_4DA4930294B84308A1E627C828C35663" src="assets/finders_menu.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Close</b> </td> 
   <td colname="col2">Clique com o botão direito do mouse na barra <span class="uicontrol"> Localizadores</span> e selecione <span class="uicontrol"> Fechar</span> para fechar um painel Localizadores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Salvar</b> </td> 
   <td colname="col2">Salve a lista localmente clicando com o botão direito do mouse na barra de cabeçalho e selecionando a opção <span class="uicontrol"> Salvar</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Exportar</b> </td> 
   <td colname="col2">Você pode exportar uma lista de dimensões, métricas ou filtros selecionados do painel Localizador clicando com o botão direito do mouse na barra Localizadores e selecionando <span class="uicontrol"> Exportar</span> no menu. <p> Adicione um nome e exporte para o Microsoft Excel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Copiar</b> </td> 
   <td colname="col2"> Copie uma lista de Dimension, métricas ou filtros. Você pode copiar como arquivo ou gráfico em Fundo escuro, Plano de fundo claro ou Monocromático. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Minimizar</b> </td> 
   <td colname="col2"> Minimize o painel Localizador. Somente a barra Localizadores será exibida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Borderless</b> </td> 
   <td colname="col2"> Exibe um painel sem linhas de borda para Localizadores no espaço de trabalho (mas não na barra lateral esquerda). </td> 
  </tr> 
 </tbody> 
</table>

