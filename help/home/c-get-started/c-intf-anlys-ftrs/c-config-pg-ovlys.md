---
description: As sobreposições de página são configuradas somente no aplicativo Site, mas podem ser configuradas para outros aplicativos.
solution: Analytics
title: Configurar uma sobreposição de página
topic: Data workbench
uuid: c4c612ed-5154-4b20-96ab-24b74fba19a2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurar uma sobreposição de página{#configure-a-page-overlay}

As sobreposições de página são configuradas somente no aplicativo Site, mas podem ser configuradas para outros aplicativos.

Para obter informações sobre como configurar a sobreposição de página para outro aplicativo, entre em contato com os Serviços de consultoria da Adobe.

A visualização da sobreposição de página é uma ferramenta para a análise de links HTML. Quando você solicita uma sobreposição para uma página específica, o Análise de big data captura um instantâneo da página real, como seria exibido em um navegador da Web, e analisa o código HTML que representa links de acordo com uma lista de expressões regulares definidas. Para cada link na página selecionada, o software tenta encontrar uma correspondência de padrão de expressão regular trabalhando na lista até que a primeira correspondência seja encontrada. Se houver uma correspondência, o link aparecerá realçado na sobreposição da página.

A sobreposição de página mostra dados somente quando você adiciona uma legenda colorida ao espaço de trabalho que contém a sobreposição de página.

>[!NOTE]
>
>A configuração da sobreposição de página requer um trabalho de configuração cuidadoso e é possível criar resultados enganosos se os links forem mapeados incorretamente para os dados. O trabalho envolvido na configuração da sobreposição de página para um site específico depende de como os links são apresentados dentro do código HTML nas páginas do site.

A sobreposição de página, por sua natureza, sugere ao usuário o modelo mental que ele exibe &quot;onde as pessoas clicam&quot;. Se os dados que suportam a visualização não corresponderem a esse modelo, o potencial de confusão é alto.

Em [!DNL Site], um link geralmente representa um elemento da dimensão Próximo URI ou Próximo link, mas você pode mapear um link para qualquer dimensão que faça sentido para a sua análise. Para obter informações sobre como configurar a sobreposição de página para outras dimensões, entre em contato com os Serviços de consultoria da Adobe.

>[!NOTE]
>
>Não é recomendado usar a dimensão Página para sobreposição de página. Os usuários podem renomear os elementos das dimensões de Página, alterando assim a sintaxe do link na qual a funcionalidade de sobreposição de página depende.

Para configurar a sobreposição de página para [!DNL Site], você deve editar dois arquivos:

* **[!DNL Page Overlay.vw]:**Esse arquivo é um arquivo de modelo para criar visualizações de sobreposição de página. Pelo menos um arquivo de modelo deve estar presente no perfil para o qual você está configurando a sobreposição de página.
* **[!DNL Page Overlay Link Templates.cfg]:**Quando a visualização da sobreposição de página carrega uma página, ela identifica automaticamente os links na página e seus destinos. Para relacionar esses links a elementos nos dados, é necessário definir um conjunto de expressões regulares neste arquivo.

   É possível definir várias expressões regulares para corresponder aos elementos da dimensão. A ordem em que você define as expressões é importante. Quando você solicita uma sobreposição para uma página específica, o Análise de big data captura um instantâneo da página real, como seria exibido em um navegador da Web, e analisa o código HTML que representa links de acordo com uma lista de expressões regulares definidas. Para cada link na página selecionada, o software tenta encontrar uma correspondência de padrão de expressão regular trabalhando na lista até que a primeira correspondência seja encontrada. A primeira expressão para corresponder a um elemento de dimensão é a usada. Portanto, é melhor listar a expressão regular com o padrão de correspondência mais específico primeiro, seguido por expressões menos específicas. Se houver uma correspondência, o link aparecerá realçado na visualização da sobreposição da página.

**Para configurar a sobreposição de página para o Site**

1. I

   Na guia [!DNL Profile Manager], navegue até **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.

   >[!NOTE]
   >
   >O diretório Elemento de dimensão contém os itens de menu de contexto que aparecem quando você clica com o botão direito do mouse em um elemento de dimensão. Por exemplo, abra uma tabela URI e selecione um elemento URI. Clique com o botão direito do mouse no URI e na Sobreposição da página será exibida.

1. Na pasta URI, clique com o botão direito do mouse na marca de seleção ao lado do [!DNL Page Overlay.vw] arquivo e clique em **[!UICONTROL Make Local]**. Uma marca de seleção para este arquivo é exibida na [!DNL User] coluna.
1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Especifique o domínio (e a altura do navegador, se necessário).

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
1. Para disponibilizar essa alteração para todos os usuários do perfil de trabalho, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do [!DNL .vw] arquivo na [!DNL User] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >Você pode criar arquivos de modelo adicionais para outros sites ou subdomínios. Cada modelo criado é exibido no [!DNL Page Overlay menu].

1. Na pasta Contexto do [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção ao lado do [!DNL Page Overlay Link Templates.cfg] arquivo e clique em **[!UICONTROL Make Local]**.

   Uma marca de seleção para este arquivo é exibida na [!DNL User] coluna.

1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Clique com o botão direito do mouse **[!UICONTROL Link Templates]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.
1. Edite os parâmetros do vetor LinkRegex conforme necessário:

<table id="table_24DD4BB5009542F7BB1DA3318E2E6E2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para este parâmetro... </th> 
   <th colname="col2" class="entry"> Fornecer estas informações... </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Dimensão </p> </td> 
   <td colname="col2"> <p>A dimensão (normalmente a dimensão de URI seguinte) que é representada pelo link. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expressão </p> </td> 
   <td colname="col2"> <p>A expressão regular usada para selecionar a parte relevante do link HTML para localizar o próximo elemento da Dimensão. A expressão regular deve ser uma correspondência exata, e o padrão de saída desejado é agrupado com parênteses. Para obter detalhes sobre expressões regulares, consulte o Guia <i>de configuração de</i>conjuntos de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Padrão de saída </p> </td> 
   <td colname="col2"> <p>O padrão de saída da expressão regular usada para extrair o elemento resultante do parâmetro Dimensão. </p> </td> 
  </tr> 
 </tbody> 
</table>

O arquivo de amostra a seguir mostra três expressões regulares:

![](assets/cfg_PageOverlayLinkTemplates_Example.png)

1. Para salvar o arquivo, clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
1. Para disponibilizar essa alteração para todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção para [!DNL Page Overlay Link Templates.cfg] na [!DNL User] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

