---
description: A visualização do mapa de densidade exibe elementos como retângulos sombreados em um mapa quadrado.
title: Mapa de densidade
uuid: c13cecee-f322-4757-aa90-12039173ff9f
exl-id: da37d954-cadb-42a6-a44b-9b38c0354a5d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 1%

---

# Mapa de densidade{#density-map}

{{eol}}

A visualização do mapa de densidade exibe elementos como retângulos sombreados em um mapa quadrado.

Os tamanhos dos retângulos dependem dos valores do elemento, onde valores maiores são representados por retângulos de área maior. Semelhante a um gráfico de pizza, essa visualização permite ver rapidamente quais elementos constituem a maior porcentagem da dimensão selecionada.

![](assets/density_map_day_visits.png)

Para criar um mapa de densidade:

1. Abra um novo espaço de trabalho.

   Depois de abrir um novo espaço de trabalho, talvez seja necessário clicar em **Adicionar** > **Desbloquear temporariamente**.
1. Clique em **[!UICONTROL Visualization]** > **[!UICONTROL Density Map]**.

1. Selecione um **[!UICONTROL Dimension]** no menu .

   Por exemplo, selecione **[!UICONTROL Time]** > **[!UICONTROL Days]**.

   Por outro lado, selecionar **[!UICONTROL Time]** > **[!UICONTROL Hours]** daria mais elementos com valores menores exibidos como retângulos menores.

   >[!NOTE]
   >
   >Você desejará escolher uma dimensão com vários elementos de acordo com suas necessidades. O limite atual é 200 dos maiores elementos para cada dimensão.

1. Você pode alterar visualizações de dimensão abrindo **[!UICONTROL Visualization]** > **[!UICONTROL Table]** e selecionando entre elementos da tabela para exibir no mapa.

   ![](assets/density_map_day_selections.png)

   O mapa responderá às seleções da tabela.

1. Passar o mouse sobre elementos pequenos exibirá seu nome e valor no texto que aparece perto do cursor do mouse.
1. Mascarar elementos clicando com o botão direito do mouse e selecionando **[!UICONTROL Mask]** e escolha uma opção.

   ![](assets/density_map_day_mask.png)

   Para exibir todos os nós mascarados, selecione **[!UICONTROL Unhide All]**.

1. Destaque os elementos clicando com o botão direito do mouse e selecionando **[!UICONTROL Spotlight]** e escolha uma opção. O destaque permite que você destaque e escureça elementos em um intervalo.
1. Adicione uma legenda de cores ao espaço de trabalho. Você pode identificar valores no mapa usando a legenda de cores.

   Você pode adicionar uma legenda de cores ao espaço de trabalho e os nós mudarão de cor com base na dimensão adicional dos dados.
1. Altere a dimensão ou métrica clicando com o botão direito do mouse no título do mapa e selecionando no menu .

   ![](assets/density_map_change_dim.png)

1. Adicione chamadas clicando com o botão direito do mouse em uma célula e selecionando **[!UICONTROL Add Callout]**. Você pode selecionar de diferentes tipos ou visualizações no menu.

   ![](assets/density_map_callout.png)

1. Como em todas as visualizações, você pode clicar com o botão direito do mouse acima da barra de título para obter comandos básicos como Fechar, Salvar, Exportar para o Microsoft Excel, Ordem, Copiar, Minimizar e Sem Borda para exibir uma visualização sem borda.

   ![](assets/density_map_export.png)

1. O Mapa de densidade permite selecionar e desmarcar vários elementos semelhantes a outras visualizações:

* Clique com o botão esquerdo do mouse para selecionar um elemento.
* Ctrl + clique para selecionar vários elementos.
* Shift + clique para desmarcar um elemento.
* Clique com o botão direito do mouse nos elementos selecionados para abrir um menu. Em seguida, escolha **[!UICONTROL Deselect]** ou **[!UICONTROL Deselect All]** para limpar os elementos selecionados.

## Opções adicionais {#section-d77defb012424de4a7ced8e5c93115bc}

Clique com o botão direito do mouse no Mapa de densidade para abrir um menu com estas opções:

<table id="table_3ADA85031C834792BFD041E186962A41"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Adicionar Chamada </td> 
   <td colname="col2">Adicione um texto ou gráfico como uma chamada na visualização para identificar ou descrever um elemento. <p>Você também pode selecionar uma legenda de métrica, tabela, gráfico de linha ou gráfico de dispersão em branco com base no elemento selecionado no Mapa de densidade. Em seguida, você pode adicionar métricas e dimensões a essas visualizações em branco, conforme necessário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Máscara </td> 
   <td colname="col2">As opções de mascaramento permitem ocultar os elementos selecionados. Clique com o botão direito do mouse para exibir as opções de Máscara. <p><span class="uicontrol"> Ocultar este elemento</span>—Escolha essa opção para mascarar um único elemento selecionado. </p> <p><span class="uicontrol"> Ocultar selecionados</span>—Escolha essa opção para mascarar vários elementos que você selecionou. </p> <p><span class="uicontrol"> Mostrar parte superior</span>— escolha essa opção para exibir apenas os 100, 50, 25 ou 10 elementos principais com base nos valores no Mapa de densidade. </p> <p><span class="uicontrol"> Mostrar abaixo</span>—Escolha essa opção para exibir apenas os 100, 50, 25 ou 10 elementos principais inferiores com base nos valores no Mapa de densidade. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Spot </td> 
   <td colname="col2"> O destaque permite que você destaque e escureça elementos em um intervalo. Clique com o botão direito do mouse para abrir um menu de opções. <p><span class="uicontrol"> Mostrar parte superior</span>— Escolha essa opção para realçar apenas os 100, 50, 25 ou 10 elementos principais com base nos valores no Mapa de densidade. </p> <p><span class="uicontrol"> Mostrar abaixo</span>—Escolha essa opção para realçar apenas os 100, 50, 25 ou 10 elementos principais inferiores com base nos valores no Mapa de densidade. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Desmarcar </p> <p>Desmarcar tudo </p> </td> 
   <td colname="col2"> <p> Selecione esses comandos para desmarcar o elemento atual, se selecionado, ou desmarcar todos os elementos selecionados. </p> </td> 
  </tr> 
 </tbody> 
</table>
