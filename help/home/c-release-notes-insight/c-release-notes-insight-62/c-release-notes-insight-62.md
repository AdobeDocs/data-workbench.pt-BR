---
description: As notas de versão da Data Workbench 6.2 incluem novos recursos, requisitos de atualização, correções de erros e problemas conhecidos.
title: Notas de versão do Data Workbench 6.2
uuid: 8631c936-d53b-493d-9f58-72f541c3ddce
translation-type: tm+mt
source-git-commit: a276b16565634fea9b693206c8a55b528fada977
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 5%

---


# Notas de versão do Data Workbench 6.2{#data-workbench-release-notes}

As notas de versão da Data Workbench 6.2 incluem novos recursos, requisitos de atualização, correções de erros e problemas conhecidos.

## Novos recursos {#section-1225066ea8f44cf68e42e019d0bca816}

A Data Workbench 6.2 inclui estes novos recursos:

| Recursos | Descrição |
|--- |--- |
| Árvores de decisão | As árvores de decisão são uma visualização de análise preditiva usada para avaliar as características e os relacionamentos do visitante. O Construtor de árvore de decisão gera uma visualização da árvore com base em um caso positivo e um conjunto de entradas especificados. |
| Atualizar para Filtro Binário na Matriz de Correlação | O Filtro binário foi atualizado com novos recursos, exigindo que você recrie qualquer Matriz de correlação com um Filtro binário criado em versões anteriores. |
| Mapa de densidade | O mapa de densidade é uma visualização que exibe elementos como retângulos sombreados dentro de um mapa quadrado. |
| Perfil de atribuição | Para analisar rapidamente os valores de atribuição (eventos para atribuir a responsabilidade por uma conversão ou venda bem-sucedida), a Data Workbench oferece um perfil de Atribuição baseado em regras com recursos para o Arquiteto configurar os relatórios de Atribuição e o Analista para executar os relatórios. |
| Relatórios analíticos | Os modelos de relatórios padronizam os relatórios da Adobe Analytics para os usuários da análise de big data que utilizam o perfil Adobe SC. Esses relatórios são idênticos aos relatórios empregados nos Relatórios e análises de marketing (antigo SiteCatalyst). |
| Gráficos de dispersão 3D | Um Gráfico de dispersão 3D faz o gráfico dos elementos de uma dimensão de dados (como Dias ou Site de referência) em uma grade tridimensional na qual os eixos x, y e z representam várias métricas. |


## Atualizações da interface do cliente Data Workbench{#data-workbench-client-ui-updates}

A Data Workbench 6.2 inclui novas atualizações da interface do usuário para o painel de marcadores, novos ícones na barra de ferramentas do espaço de trabalho, a capacidade de arrastar o espaço de trabalho dentro de uma tela, novas teclas rápidas e atualizações para a visualização do gráfico de pizza.

## Novos recursos de marcador {#section-e361b605441540ca8213c3fddb5e0718}

Agora é possível marcar espaços de trabalho significativos para mover rapidamente entre visualizações e relatórios empregados no fluxo de trabalho.

**Trabalhar com marcadores**

1. Marque como favorito uma área de trabalho clicando no ícone Marcador ![](assets/bookmark_icon.png) no canto superior direito da barra de ferramentas.
1. Clique em **[!UICONTROL Add]** > **[!UICONTROL Bookmarks Panel]** no painel esquerdo para abrir uma lista de marcadores.

   ![](assets/bookmarks_panel.png)

1. Para abrir um espaço de trabalho marcado, clique no nome de um espaço de trabalho no **[!UICONTROL Bookmark Panel]**.

   ![](assets/bookmarks_panel_left.png)

   O espaço de trabalho selecionado será aberto. Ao clicar em outro espaço de trabalho marcado, o espaço de trabalho anterior será fechado e o espaço de trabalho selecionado recentemente será aberto, permitindo que você navegue rapidamente pelo seu fluxo de trabalho.

**Para excluir um marcador:**

* No Painel Marcador, clique com o botão direito do mouse e selecione **[!UICONTROL Remover<bookmark title>]**para excluir um marcador selecionado ou selecione **[!UICONTROL Clear All Bookmarks]**para excluir todos os marcadores.

* Você também pode clicar com o botão direito do mouse na área de trabalho na visualização em miniatura dentro da área de trabalho e selecionar **[!UICONTROL Clear Bookmark]**.

>[!IMPORTANT]
>
>* 25 marcadores podem ser salvos.
>* Se você adicionar um marcador e mover o local do espaço de trabalho, o marcador será inválido e deverá ser excluído do Painel de marcadores e redefinido.

>



## Novos ícones no Workspace {#section-c108bbd1661249e79c146727ff3d2470}

A Data Workbench 6.2 agora substitui o texto no espaço de trabalho por ícones. Você ainda pode passar o mouse sobre o mouse e ver a mensagem de dica de ferramenta que identifica o ícone, incluindo **[!UICONTROL File]**, **[!UICONTROL Add]** e **[!UICONTROL Export]**.

![](assets/new_icons.png)

Um novo **[!UICONTROL Help]** ícone é adicionado para acessar a documentação e outros centros de conhecimento, incluindo os seguintes links:

<table id="table_64BBC67B1BB44B1197FF7E5E7B067696"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Links de documentação </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Reports &amp; Analytics de marketing </td> 
   <td colname="col2">Abra a página de ajuda dos Relatórios e análises <span class="uicontrol"> de marketing do</span> Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Troca de ideias </td> 
   <td colname="col2">Abra o logon <span class="uicontrol"></span>do Idea Exchange. Este portal online permite que os usuários forneçam alterações de atualização e ideias de aprimoramento para a análise de big data. Essas ideias voltadas para o cliente podem ser votadas por todos os usuários. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ajuda </td> 
   <td colname="col2">Abra a documentação <span class="uicontrol"> da</span>Data Workbench. <p>Você também pode pressionar <span class="uicontrol"> &lt;F1&gt;</span> para abrir a ajuda em um espaço de trabalho. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sobre </td> 
   <td colname="col2">Abra para identificar a versão <span class="uicontrol"> do</span> cliente da análise de big data. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Você também pode pressionar `<F1>` para abrir a documentação a partir de uma área de trabalho.

## Arrastar Visualizações da Workspace {#section-9129c340c21d45a3864c923884cd4382}

Se um espaço de trabalho for maior que a tela visualizável, você poderá mover a visualização para ver todos os elementos dentro do espaço de trabalho. Você pode clicar em segundo plano (fora das visualizações e tabelas) e arrastar a tela para mover a área visível dentro da área de trabalho. O cursor se transformará em um ícone de mão ao arrastar a visualização dentro do quadro do espaço de trabalho.

![](assets/drag_workspace.png)

## Atalhos rápidos para alterar Visualizações da Workspace {#section-d8322f72423f437aa2e34f2188b1341c}

Novas teclas rápidas permitem redimensionar e reajustar espaços de trabalho entre visualizações de janela e de página inteira.

<table id="table_A01C514C99F043338D183A6839E03DEA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Comandos </th> 
   <th colname="col2" class="entry"> Teclas rápidas </th> 
   <th colname="col3" class="entry"> Comandos de menu combinados </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Visualização</b>em tela cheia. O Workspace preenche a tela e se adapta ao novo tamanho. </td> 
   <td colname="col2"><b>Ctrl mais</b> <p>Ctrl + (no teclado numérico) </p> <p><i>ou</i> </p> <p>Ctrl Shift + (no teclado) </p> </td> 
   <td colname="col3"> 
    <ul id="ul_C7C731B894D946D9916F50806F015857"> 
     <li id="li_452B4C119B1A40038A408CFFC53653A9">Arquivo &gt; Tamanho da página &gt; Tela de preenchimento <p><i>seguido por</i> </p> </li> 
     <li id="li_DE9B8B31B9F24A6AA68A1D0DB886B501">Arquivo &gt; Refazer área de trabalho </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Visualização</b>da janela. O Workspace é exibido em uma visualização de janela padrão e é atualizado para o novo tamanho. </td> 
   <td colname="col2"><b>Ctrl menos</b> <p>Ctrl - </p> </td> 
   <td colname="col3"> 
    <ul id="ul_3474B9EFD69343C09BC84E485D896C28"> 
     <li id="li_820BAED76FF24A5785E6D89C5C692DD5">Arquivo &gt; Tamanho da página &gt; Padrão <p><i>seguido por</i> </p> </li> 
     <li id="li_337789F282CE4C2C990C67B115782454">Arquivo &gt; Refazer área de trabalho </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Correções de erros {#section-8704a9ac358246cd81233dd0982d534f}

* Atualização do arquivo de pesquisa do Visual Site para tratar das alterações no mecanismo de pesquisa para o termo de pesquisa do query.
* Correção de uma mensagem de erro imprecisa, &quot;Falha ao importar espaço de trabalho&quot;, ao importar um espaço de trabalho na estação de trabalho do cliente mesmo que a importação tenha sido bem-sucedida.
* O erro de conexão da estação de trabalho que exibe a mensagem &quot;Conflito de configuração 412&quot; agora é substituído por uma mensagem amigável que identifica a ação do sistema.
* O comando &quot;postar&quot; pode ser executado no Servidor de relatórios.
* Correção de erros de interface do usuário na interface do usuário cliente para chinês simplificado.
* A Adobe Analytics atualizou o feed de dados que alimenta a Data Workbench para tirar proveito dos Perfis e Audiências que se integram ao Adobe Experience Cloud. Todos os usuários da Data Workbench precisaram preparar seu ambiente para essa transição até 21 de abril de 2014.

   Perfis e Audiências foram introduzidos para fornecer uma visualização completa de clientes em toda a Adobe Analytics. Esse novo serviço está disponível na Adobe Experience Cloud para agregar mais valor entre as ferramentas de análise e estabelecer a base para esses recursos no Analytics. O novo identificador do visitante de Experience Cloud será adicionado ao feed de dados, juntamente com outros aprimoramentos e melhorias para adaptar-se ao novo feed de dados e ao identificador global do visitante.
* Ao importar um espaço de trabalho, uma mensagem de erro é exibida mesmo que a importação tenha sido bem-sucedida.

## Requisito de atualização {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* O perfil de Atribuição é configurado para usuários que implementaram o perfil Adobe SC para empregar o feed de dados do Analytics (SC/Insight). Por padrão, os eventos de Marketing e Conversão são empregados como interações padrão avaliadas nos modelos baseados em regras.
* Para os usuários do perfil Adobe SC que atualizam para a Data Workbench 6.2, se você não estiver usando as configurações padrão, verifique se o [!DNL x-bot_id] valor no arquivo [!DNL SC Fields.cfg] está sendo decodificado corretamente e se o [!DNL x-bot_id] campo está listado corretamente nos arquivos [!DNL Decoding Instructions.cfg] e [!DNL Exclude Hit.cfg] arquivos. Isso só será um problema se você tiver modificado o arquivo de configuração da configuração padrão.

* Se você tiver excluído campos não utilizados no arquivo **[!UICONTROL Dataset]** > **[!UICONTROL Log Processing]** > **[!DNL SC Fields.cfg]** para o perfil Adobe SC, precisará atualizar para acomodar os valores de campo atualizados usados para o perfil de Atribuição.

## Problemas conhecidos {#section-dbb307639835493a83409f5f461932b8}

* Quando a Visualização de gráfico de dispersão 3D inclui avisos, o zoom pode exibir os gráficos fora da borda da visualização.

   Solução: Aplique zoom no Gráfico de dispersão 3D primeiro e, em seguida, adicione chamadas à sua visualização.
* Arrastar a métrica do painel Localizadores para Legenda de métrica fora da coluna de métrica excluirá a Legenda de métrica do espaço de trabalho.

   Solução: Os usuários que desejam arrastar métricas para a Legenda da métrica devem soltar na primeira coluna (coluna de métricas).
* As opções Imprimir espaço de trabalho usando a barra lateral e Ambas não incluirão as informações de direitos autorais na página impressa.
* O uso da estação de trabalho em uma sessão de área de trabalho remota travará ao renomear áreas de trabalho.
* (Na versão em chinês simplificado) As saídas de relatório reais são válidas no Servidor de relatórios, mas as linhas de assunto de email e os nomes de arquivo de anexo são distorcidos.
* (Na versão em chinês simplificado) Ao usar a quebra automática de texto na visualização da planilha, as palavras localizadas não estão sendo vinculadas corretamente, resultando em caracteres inúteis adicionados à sequência.
* (Na versão em chinês simplificado) Não é possível iniciar o Insight.exe se o diretório de instalação for nomeado com caracteres que não sejam o inglês.

   Solução: Mantenha os nomes padrão ou renomeie usando apenas caracteres em inglês no caminho da pasta para iniciar executáveis.

