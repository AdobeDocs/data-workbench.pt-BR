---
description: As sobreposições de página são configuradas somente no aplicativo Site, mas podem ser configuradas para outros aplicativos.
title: Configurar uma sobreposição de página
uuid: c4c612ed-5154-4b20-96ab-24b74fba19a2
exl-id: 4e0dfce8-def2-49f3-93e8-41d82922fb88
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 1%

---

# Configurar uma sobreposição de página{#configure-a-page-overlay}

As sobreposições de página são configuradas somente no aplicativo Site, mas podem ser configuradas para outros aplicativos.

Para obter informações sobre como configurar a sobreposição de página para outro aplicativo, entre em contato com os Serviços de consultoria do Adobe.

A visualização de sobreposição de página é uma ferramenta para análise de link HTML. Quando você solicita uma sobreposição para uma página específica, o Data Workbench captura um instantâneo da página real como apareceria em um navegador da Web e analisa o código HTML que representa links de acordo com uma lista de expressões regulares definidas. Para cada link na página selecionada, o software tenta encontrar uma correspondência de padrão de expressão regular ao trabalhar na lista até que a primeira correspondência seja encontrada. Se houver uma correspondência, o link aparecerá realçado na sobreposição da página.

A sobreposição de página mostra dados somente quando você adiciona uma legenda de cor ao espaço de trabalho que contém a sobreposição de página.

>[!NOTE]
>
>Configurar a sobreposição de página requer um trabalho de configuração cuidadoso e é possível criar resultados enganosos se os links forem mapeados de maneira imprópria para os dados. O trabalho envolvido na configuração da sobreposição de página para um site específico depende de como os links são apresentados no código HTML nas páginas do site.

A sobreposição de página, por sua natureza, sugere ao usuário o modelo mental que ele exibe &quot;onde as pessoas clicam&quot;. Se os dados que suportam a visualização não corresponderem a este modelo, o potencial de confusão será alto.

Em [!DNL Site], um link normalmente representa um elemento da dimensão Próximo URI ou Próximo link , mas você pode mapear um link para qualquer dimensão que faça sentido para a análise. Para obter informações sobre como configurar a sobreposição de página para outras dimensões, entre em contato com os Serviços de consultoria do Adobe.

>[!NOTE]
>
>Não é recomendado usar a dimensão Página para sobreposição de página. Os usuários podem renomear os elementos das dimensões da Página , alterando assim a sintaxe do link na qual a funcionalidade de sobreposição de página depende.

Para configurar a sobreposição de página para [!DNL Site], você deve editar dois arquivos:

* **[!DNL Page Overlay.vw]:** Esse arquivo é um arquivo de modelo para criar visualizações de sobreposição de página. Pelo menos um arquivo de modelo deve estar presente no perfil para o qual você está configurando a sobreposição de página.
* **[!DNL Page Overlay Link Templates.cfg]:** Quando a visualização de sobreposição de página carrega uma página, ela identifica automaticamente os links na página e seus destinos. Para relacionar esses links com elementos nos dados, você deve definir um conjunto de expressões regulares nesse arquivo.

   É possível definir várias expressões regulares para corresponder aos elementos da dimensão. A ordem em que você define as expressões é importante. Quando você solicita uma sobreposição para uma página específica, o Data Workbench captura um instantâneo da página real como apareceria em um navegador da Web e analisa o código HTML que representa links de acordo com uma lista de expressões regulares definidas. Para cada link na página selecionada, o software tenta encontrar uma correspondência de padrão de expressão regular ao trabalhar na lista até que a primeira correspondência seja encontrada. A primeira expressão a corresponder a um elemento de dimensão é a usada. Portanto, é melhor listar a expressão regular com o padrão de correspondência mais específico primeiro, seguido por expressões menos específicas. Se houver uma correspondência, o link aparecerá realçado na visualização da sobreposição da página.

**Para configurar a sobreposição de página para o Site**

1. I

   No [!DNL Profile Manager], navegue até **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.

   >[!NOTE]
   >
   >O diretório Dimension Element contém os itens do menu de contexto que são exibidos ao clicar com o botão direito do mouse em um elemento de dimensão. Por exemplo, abra uma tabela de URI e selecione um elemento de URI. Clique com o botão direito do mouse no URI e na sobreposição da página.

1. Na pasta URI, clique com o botão direito do mouse na marca de seleção ao lado do arquivo [!DNL Page Overlay.vw] e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece na coluna [!DNL User].
1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Especifique o Domínio (e a Altura do Navegador, se necessário).

   ```
   window = simpleBorderWindow: 
     client = scrollWindow: 
       client = PageOverlay: 
         URI Template = string: http://%Domain%%Element%
         URI Parameters = map: 
           Domain = string: domain name
           Element = ref: Element/Name
         Dim = ref: wdata/model/dim/URI
         Dim Element = ref: Element/Name
         Level = ref: wdata/model/dim/Page View
         Group = ref: wdata/model/dim/Session
         Browser Height = int: browser height
     pos = v3d: (518, 202, 0)
     size = v3d: (810, 610, 0)
     titleBar = editor: 
       size = v3d: (61, 19, 0)
       text = string: 
   ```

1. Salve o arquivo.
1. Para disponibilizar essa alteração a todos os usuários do perfil de trabalho, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo [!DNL .vw] na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.

   >[!NOTE]
   >
   >Você pode criar arquivos de modelo adicionais para outros sites ou subdomínios. Cada modelo criado aparece no [!DNL Page Overlay menu].

1. Na pasta Contexto do [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção ao lado do arquivo [!DNL Page Overlay Link Templates.cfg] e clique em **[!UICONTROL Make Local]**.

   Uma marca de verificação para este arquivo aparece na coluna [!DNL User].

1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Clique com o botão direito do mouse em **[!UICONTROL Link Templates]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.
1. Edite os parâmetros do vetor LinkRegex conforme necessário:

<table id="table_24DD4BB5009542F7BB1DA3318E2E6E2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para este parâmetro... </th> 
   <th colname="col2" class="entry"> Fornecer essas informações... </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Dimensão </p> </td> 
   <td colname="col2"> <p>A dimensão (normalmente a dimensão Próximo URI) que é representada pelo link. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expressão </p> </td> 
   <td colname="col2"> <p>A expressão regular usada para selecionar a parte relevante do link HTML para localizar o próximo elemento no Dimension. A expressão regular deve ser uma correspondência exata, e o padrão de saída desejado é agrupado com parênteses. Para obter detalhes sobre expressões regulares, consulte o <i>Guia de Configuração de Conjunto de Dados</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Padrão de saída </p> </td> 
   <td colname="col2"> <p>O padrão de saída da expressão regular usada para extrair o elemento resultante do parâmetro Dimension. </p> </td> 
  </tr> 
 </tbody> 
</table>

O arquivo de exemplo a seguir mostra três expressões regulares:

![](assets/cfg_PageOverlayLinkTemplates_Example.png)

1. Para salvar o arquivo, clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
1. Para disponibilizar essa alteração a todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção [!DNL Page Overlay Link Templates.cfg] na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.
