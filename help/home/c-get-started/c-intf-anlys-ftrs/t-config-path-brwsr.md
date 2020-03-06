---
description: Os navegadores de caminho podem ser configurados para funcionar com qualquer combinação de dimensão básica, dimensão de grupo, dimensão de nível e métrica que faça sentido para seu aplicativo e conjunto de dados.
solution: Analytics
title: Configurar um navegador de caminho
topic: Data workbench
uuid: 1ba3fb6e-b76f-428f-b6ec-077669c3b305
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurar um navegador de caminho{#configure-a-path-browser}

Os navegadores de caminho podem ser configurados para funcionar com qualquer combinação de dimensão básica, dimensão de grupo, dimensão de nível e métrica que faça sentido para seu aplicativo e conjunto de dados.

Depois de configurar um navegador de caminho, ele é listado com outros navegadores de caminho no [!DNL Add Visualization] menu.

1. No [!DNL Profile Manager], clique em **[!UICONTROL Menu]**, em seguida, clique **[!UICONTROL Add Visualization]** e **[!UICONTROL Path Browser]**.

   Pelo menos um [!DNL *.vw] arquivo reside no diretório Navegador de caminhos.

1. Clique com o botão direito do mouse na marca de seleção do arquivo desejado e clique em **[!UICONTROL Make Local]**.
1. Clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Edite os parâmetros do arquivo usando o arquivo de amostra e a tabela a seguir como guias:

   ```
   window = simpleBorderWindow: 
     client = pathBrowser: 
       Left Path = vector: 0 items
       Map = ref: wdata/model/dim/base dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       Map Level = ref: wdata/model/dim/level dimension name
       Metric = ref: wdata/model/metric/metric name
       Right Path = vector: 0 items
       size = v3d: (673, 279, 0)
     pos = v3d: (714, 143, 0)
     size = v3d: (673, 298, 0)
   ```

<table id="table_1DCCB4B24B554B72A781B304B5EB155E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para este parâmetro... </th> 
   <th colname="col2" class="entry"> Fornecer estas informações... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Nome da dimensão básica</i> </p> </td> 
   <td colname="col2"> <p>O nome da dimensão cujos elementos aparecem no navegador de caminho. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome da dimensão do grupo</i> </p> </td> 
   <td colname="col2"> <p>O nome da dimensão que determina como os elementos da dimensão de nível são agrupados para formar os caminhos em um navegador de caminho. Especificamente, os elementos de dimensão de nível associados a um único caminho em um navegador de caminho não podem abranger mais de um elemento de uma dimensão de grupo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome da dimensão de nível</i> </p> </td> 
   <td colname="col2"> <p>O nome do nível (pai) da dimensão base cujos elementos você arrasta para o navegador de caminho. Conforme você segue um caminho de um elemento de dimensão base para o seguinte, você move de um elemento de dimensão de nível para o seguinte. Quando você seleciona um caminho de elementos de dimensão base, está selecionando dados para os elementos correspondentes da dimensão de nível. A seleção sempre inclui os elementos da dimensão de nível que se relacionam à raiz e é refinada adicionando mais elementos ao caminho. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome da métrica</i> </p> </td> 
   <td colname="col2"> <p>O nome da métrica cujo valor para um determinado elemento é proporcional à espessura do caminho que leva a esse elemento. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Para obter mais informações sobre a dimensão básica, dimensão de grupo, dimensão de nível e métrica para um navegador de caminho, consulte Navegadores de [caminho](../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-path-browsers.md#concept-f2e9fdafed6e49c2bd111ab425cd6e2b).

1. No Bloco de notas, clique em **[!UICONTROL File]** > **[!UICONTROL Save As]** para salvar o arquivo com um novo nome com base na dimensão do grupo, ou seja, nome *da dimensão* Grupo.vw.

   Certifique-se de salvar o arquivo no diretório Navegador de caminhos.

   >[!NOTE]
   >
   >Para certificar-se de que seu navegador de caminho esteja salvo como um [!DNL *.vw] arquivo, na [!DNL Save As] janela, defina Salvar como tipo para Todos os arquivos.

1. (Opcional) Para disponibilizar as alterações para todos os usuários do perfil de trabalho, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
