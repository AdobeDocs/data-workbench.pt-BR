---
description: O texto ou as expressões podem ser inseridos em qualquer célula de uma planilha.
solution: Analytics
title: Trabalhar com dados em planilhas
topic: Data workbench
uuid: c2331fa5-aa07-4622-8f44-5124c22dffcb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Trabalhar com dados em planilhas{#work-with-data-in-worksheets}

O texto ou as expressões podem ser inseridos em qualquer célula de uma planilha.

Todas as expressões em uma planilha são precedidas por um sinal de igual (=), a menos que use [!DNL eval( )], que trata o texto na célula referenciada como uma expressão.

Para obter uma lista completa das regras de métricas, dimensões e sintaxe de filtros, consulte Sintaxe [de linguagem de](../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)consulta.

**Para digitar dados em uma planilha**

1. Clique duas vezes em uma célula na planilha para entrar no modo de edição. A célula selecionada é realçada.
1. Digite ou cole os dados desejados na célula.

**Para copiar e colar de uma célula para outra**

1. Clique com o botão direito do mouse na célula que contém os dados que deseja copiar e clique em **[!UICONTROL Copy]**.
1. Clique com o botão direito do mouse na célula na qual deseja colar os dados copiados e clique em **[!UICONTROL Paste]**.

A Análise de big data atualiza automaticamente as referências na nova célula para fazer referência às colunas e linhas apropriadas.

**Para copiar e colar de um grupo de células para outro**

1. Selecione as células que contêm os dados que deseja copiar.
1. Clique com o botão direito do mouse nas células que contêm os dados que você deseja copiar e clique em **[!UICONTROL Copy]**.
1. Clique com o botão direito do mouse na primeira célula na qual deseja começar a colar os dados copiados e clique em **[!UICONTROL Paste]**. Os dados são colados na primeira célula e abaixo dela.

A Análise de big data atualiza automaticamente as referências na nova célula para fazer referência às colunas e linhas apropriadas.

**Inserção de uma coluna**

* Clique com o botão direito do mouse em uma coluna e clique em **[!UICONTROL Insert Column]**. A nova coluna é inserida à esquerda da coluna selecionada.

**Para excluir uma coluna**

* Clique com o botão direito do mouse na coluna que deseja excluir e clique em **[!UICONTROL Delete Column]**. A coluna é removida.

**Para inserir uma linha**

* Clique com o botão direito do mouse em uma linha e clique em **[!UICONTROL Insert Row]**. A nova linha é inserida acima da linha selecionada.

**Para excluir uma linha**

* Clique com o botão direito do mouse na linha que deseja excluir e clique em **[!UICONTROL Delete Row]**. A linha é removida.

**Para redimensionar uma coluna**

1. Na linha de cabeçalho da coluna, posicione o cursor sobre a linha divisória à direita da coluna cujo tamanho você deseja alterar.
1. Clique e arraste para a direita para aumentar a largura da coluna, ou para a esquerda para reduzir a largura da coluna.

**Para formatar uma célula**

1. Clique com o botão direito do mouse na célula e clique em **[!UICONTROL Format]**.

   ![](assets/mnu_Worksheet_Format.png)

1. Clique no formato desejado no menu de opções disponíveis:

<table id="table_5788E01E52CC44E7927A0D23760D9EDD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção de menu </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Número </p> </td> 
   <td colname="col2"> <p>Aplica o formato numérico selecionado aos seus dados, como hora, data, porcentagem ou decimal. </p> <p>Clique em <span class="uicontrol"> Padrão</span> para remover a formatação selecionada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Justificar </p> </td> 
   <td colname="col2"> <p>Justifica os dados dentro da célula à esquerda, no centro ou à direita. A justificação padrão é deixada. </p> <p>Clique em <span class="uicontrol"> Padrão</span> para remover a formatação selecionada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cor do canal </p> </td> 
   <td colname="col2"> <p>Aplica a cor da fonte selecionada aos dados dentro da célula. A cor da fonte padrão é branca. </p> <p>Clique em <span class="uicontrol"> Padrão</span> para remover a formatação selecionada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indicador </p> </td> 
   <td colname="col2"> <p>Cria um indicador de métrica usando esta célula. Para obter mais informações, consulte <a href="../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#concept-f0e911b23b2c4e8da3e1ea7b9ae04183"> Criação de indicadores</a>de métrica. </p> <p>Clique em <span class="uicontrol"> Padrão</span> para remover a formatação selecionada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Célula de entrada </p> </td> 
   <td colname="col2"> <p>Transforma a célula selecionada em uma célula de entrada. Para obter mais informações, consulte <a href="../../../home/c-get-started/c-analysis-vis/c-wksts/c-input-cells.md#concept-08cd2c05a28a43dd9f7698b37e23e590"> Criação de células</a>de entrada. </p> <p>Clique em <span class="uicontrol"> Padrão</span> para remover a formatação selecionada. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Atalhos de teclado {#section-05301f4d2c60418e86902635a7aeee20}

Em planilhas, você pode usar muitos dos atalhos básicos do teclado de edição que podem ser usados em qualquer editor de texto, como Bloco de notas ou Microsoft Word.

A tabela a seguir lista os atalhos básicos do teclado que podem ser usados ao inserir dados em uma planilha.

<table id="table_8E6F73F253B3451CA1DE45EE4F4E69EF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Atalho </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Teclas de seta </p> </td> 
   <td colname="col2"> <p>Mova de célula para célula na planilha usando as teclas de seta para cima, para baixo, para a esquerda e para a direita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F2 </p> </td> 
   <td colname="col2"> <p>Edite a célula colocando o cursor na célula selecionada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enter </p> </td> 
   <td colname="col2"> <p>Completa a edição da célula selecionada. O cursor é removido da célula e o conteúdo da célula reflete sua edição. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esc </p> </td> 
   <td colname="col2"> <p>Cancele a edição da célula selecionada. O cursor é removido da célula e o conteúdo da célula reverte para o que era antes de você começar a editar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Excluir </p> </td> 
   <td colname="col2"> <p>Exclua o conteúdo da(s) célula(s). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+A </p> </td> 
   <td colname="col2"> <p>Selecione o conteúdo da célula. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+c </p> </td> 
   <td colname="col2"> <p>Copie o conteúdo da(s) célula(s). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+x </p> <p>Shift+Delete </p> </td> 
   <td colname="col2"> <p>Copie e remova o conteúdo da(s) célula(s). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+v </p> <p>Shift+Insert </p> </td> 
   <td colname="col2"> <p>Cole o conteúdo da(s) célula(s) copiada(s) nas células selecionadas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+z </p> </td> 
   <td colname="col2"> <p>Desfazer digitação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+Shift+z </p> </td> 
   <td colname="col2"> <p>Refazer digitação. </p> </td> 
  </tr> 
 </tbody> 
</table>

