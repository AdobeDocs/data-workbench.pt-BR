---
description: A visualização de Funil inclui recursos para criar um funil com várias dimensões, números brutos de visitantes, porcentagem de visitantes em cada etapa e escopos separados.
title: Recursos do funil
uuid: 7d2f5ff9-95d3-41f5-931c-689f140714c2
exl-id: e78dcefe-6f92-45de-9990-0beac09ad82f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 0%

---

# Recursos do funil{#funnel-features}

A visualização de Funil inclui recursos para criar um funil com várias dimensões, números brutos de visitantes, porcentagem de visitantes em cada etapa e escopos separados.

Estes são os recursos básicos da visualização de funil.

![](assets/funnel_visualization_capture.png)

<table id="table_49A08740CEE74D64B6F9C37CD91F1AE5"> 
 <tbody> 
  <tr> 
   <td colname="col01"> <img id="image_0C1701833FE049708CE38ADEB5EC7EEF" src="assets/funnel_visualization_capture_1.png" /> </td> 
   <td colname="col1"> Primeiro elemento </td> 
   <td colname="col2"> Primeira etapa do funil no processo. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_EF8AF94D833B4A249959B76F8FAF2318" src="assets/funnel_visualization_capture_2.png" /> </td> 
   <td colname="col1"> Terceiro elemento </td> 
   <td colname="col2">Terceira etapa do funil no processo. <p><p>Observação:  Os elementos selecionados não precisam ser da mesma dimensão. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_F3C5130B52234FAC9DEB50279F94FF90" src="assets/funnel_visualization_capture_3.png" /> </td> 
   <td colname="col1"> Porcentagem de Fall-through </td> 
   <td colname="col2"> Porcentagem que concluiu o caminho definido exibido em três escopos. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_3F030396CEB14528980F5B965113BD36" src="assets/funnel_visualization_capture_4.png" /> </td> 
   <td colname="col1"> Navegador de fallout </td> 
   <td colname="col2">Seta de fallout. Clique com o botão direito do mouse e selecione <span class="uicontrol"> Adicionar navegador de caminho</span> para ver o que outros visitantes de caminho tomaram. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_0DA7567BDBDF4BEF9CA840D2F88A414E" src="assets/funnel_visualization_capture_5.png" /> </td> 
   <td colname="col1"> Fallout de porcentagem </td> 
   <td colname="col2">Porcentagens que descrevem três escopos de fallout para usuários que não concluíram o caminho. <p>As porcentagens são apresentadas em três escopos: </p><p><img id="image_B85C46DDF12C41D5BF213D5F9DC04967" placement="break" src="assets/funnel_path_browser_5.png" /></p><p><img id="image_BC37007D7B4B425C8F87905CE68F0114" src="assets/funnel_path_browser_6.png" /> A porcentagem de fallout da etapa anterior a essa etapa. </p><p><img id="image_B10866B083424360AFF1B19E836A94CF" src="assets/funnel_path_browser_7.png" /> A porcentagem de fallout da primeira etapa do funil. </p><p><img id="image_19B9AE916B584E18A82F5D5E10674414" src="assets/funnel_path_browser_8.png" /> A porcentagem de fallout com base no número total de visitantes. </p></td> 
  </tr> 
 </tbody> 
</table>

## Etapas de funil {#section-96a6732558dd4740b73541844f06d3ef}

Os discos em um funil representam as etapas na navegação, os cones representam o fallthrough de uma etapa para a próxima e as setas representam o fallout. Clicar em um cone selecionará os usuários que passaram por ele nesse ponto e os incluirá no filtro do espaço de trabalho atual. Clicar em uma seta selecionará os visitantes que desistiram.

>[!NOTE]
>
>A visualização de Funil tem um limite de oito etapas que podem ser aplicadas.

## Recursos e funcionalidade adicionais do funil {#section-22a3582db8114ca8bce77f50bbbf296a}

* **Ajuste o clipe e o nível do funil**. Selecione a opção Funil no menu Visualização. Após a criação do funil, clique com o botão direito do mouse no título para ajustar o clipe e o nível a qualquer métrica contável no sistema.

   ![](assets/funnel_path_browser_9.png)

* **Arraste mais elementos**. Adicione mais elementos ao funil arrastando-os e soltando-os da tabela do Dimension para o funil usando as teclas `<Ctrl>` + `<Alt>`. Você pode arrastar várias etapas ao mesmo tempo da tabela Dimension selecionando vários itens (usando `<Ctrl>` + clique) e arrastando-os para a visualização de Funil usando as teclas `<Ctrl>` + `<Alt>`.
* **Excluir uma etapa**: Exclua elementos clicando com o botão direito do mouse na etapa da visualização e clicando em  **Sim**.

   ![](assets/funnel_path_browser_4.png)

* **Reorganize as etapas que você arrastou para o funil**. Basta clicar na etapa para selecioná-la e arrastá-la para outra posição para reorganizar as etapas.
* **Abra um navegador de caminho**. Você pode ver mais detalhes sobre onde os clientes passam ou saem do processo por meio do recurso [Adicionar um navegador de caminho](../../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-path-browser-funnel.md#concept-b0cedf7a28ae422696ded1258c9a4119).

* **Adicione mais etapas**. É possível adicionar no máximo oito etapas a cada visualização de funil.
* **Alterar a métrica**. A métrica pode ser alterada para que as etapas estejam contando visitas ou alguma outra métrica em cada etapa. As opções disponíveis variam de acordo com o conjunto de dados.
* **Exibir em uma exibição** tabular. Clique com o botão direito do mouse no título para exibir o menu Visualização de funil e clique em **[!UICONTROL Show Tabular View]**. Na exibição em tabela, você pode selecionar **[!UICONTROL Show Graph View]** para retornar à representação gráfica do funil. Para abrir a Exibição em tabela, clique com o botão direito no título e selecione Mostrar exibição em tabela no menu.

* **Comparar sequências**. Uma maneira eficiente de comparar duas sequências semelhantes é exibir suas duas visualizações lado a lado. Também é possível exibir a exibição em tabela e a exibição em gráfico lado a lado usando o recurso Duplicar . Para abrir, clique com o botão direito do mouse no título e selecione Duplicate no menu.
