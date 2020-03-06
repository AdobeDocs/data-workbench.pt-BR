---
description: Os mapas de processo podem ser configurados para funcionar com qualquer combinação de dimensão básica, dimensão de grupo, dimensão de nível e métrica que faça sentido para seu aplicativo e conjunto de dados.
solution: Analytics
title: Configurar um mapa de processos
topic: Data workbench
uuid: e629191e-48b9-4b58-b6aa-3705ff7b387e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurar um mapa de processos{#configure-a-process-map}

Os mapas de processo podem ser configurados para funcionar com qualquer combinação de dimensão básica, dimensão de grupo, dimensão de nível e métrica que faça sentido para seu aplicativo e conjunto de dados.

Depois de configurar um mapa de processo, ele é listado com outros mapas de processo no [!DNL Add Visualization menu].

1. No [!DNL Profile Manager], clique em **[!UICONTROL Menu]**, em **[!UICONTROL Add Visualization]** e, em seguida, clique no tipo de mapa de processo que deseja configurar (Mapa de métrica 2D, Mapa de processo 2D ou Mapa de processo 3D).

   Pelo menos um [!DNL *.vw] arquivo reside no diretório.

1. Clique com o botão direito do mouse na marca de seleção do arquivo desejado e clique em **[!UICONTROL Make Local]**.
1. Clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Edite os parâmetros do arquivo usando o arquivo de amostra e a tabela a seguir como guias:

   ```
   window = simpleBorderWindow: 
     client = processMap: 
       Traffic Metric = ref: wdata/model/metric/metric name
       center = v3d: (-0.741014, 0, 0.0639476)
       color_links = bool: true
       Map = PrefixDim: 
         Name = string: Map
         Base Dimension = ref: wdata/model/dim/base dimension name
         Element Prefixes = vector: 0 items
         Element Names = vector: 0 items
       Map Level = ref: wdata/model/dim/level dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       node_label = vector<bool>: 
       node_positions = vector: 0 items
       quantify_links = int: 2
       range = double: 2.37386
       size = v3d: (430, 290, 0)
       xAxisMetric = ref: wdata/model/metric/metric name for metric map
     pos = v3d: (880, 595, 0)
     size = v3d: (430, 309, 0)
   ```

<table id="table_3F072DB1B68746C49DF9332718982EBE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para este parâmetro... </th> 
   <th colname="col2" class="entry"> Fornecer estas informações... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Nome da métrica</i> </p> </td> 
   <td colname="col2"> <p>O nome da métrica cujo valor para um determinado nó é proporcional ao tamanho do nó. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome da dimensão básica</i> </p> </td> 
   <td colname="col2"> <p>O nome da dimensão cujos elementos aparecem como nós no mapa de processos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome da dimensão de nível</i> </p> </td> 
   <td colname="col2"> <p>O nome do nível (pai) da dimensão base cujos elementos você arrasta para o mapa de processos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome da dimensão do grupo</i> </p> </td> 
   <td colname="col2"> <p>O nome da dimensão que determina como os elementos da dimensão de nível são agrupados para formar as conexões entre nós. Uma conexão entre dois nós não pode abranger mais de um elemento de uma dimensão de grupo. Quando você faz uma seleção com base em um nó dentro de um mapa de processo, está selecionando todos os elementos da dimensão de grupo que envolveram esse nó. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome da métrica para o mapa de métricas</i> </p> </td> 
   <td colname="col2"> <p>Esse parâmetro se aplica somente a mapas de métrica 2D. </p> <p>O nome da métrica cujo valor determina a posição horizontal dos nós no mapa. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Para obter mais informações sobre a dimensão básica, a dimensão de grupo, a dimensão de nível e a métrica para um mapa de processos, consulte [Mapas](../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e)de processos.

1. No Bloco de notas, clique em **[!UICONTROL File]** > **[!UICONTROL Save As]** para salvar o arquivo com um novo nome com base na dimensão base, ou seja, nome *da dimensão* básica.vw.

   (Se você estiver configurando um mapa de métrica 2D, salve o arquivo com um nome baseado no nome da métrica para o mapa de métrica, ou seja, nome da *métrica para o mapa* de métrica.vw.) Certifique-se de salvar o arquivo no diretório apropriado do mapa de processos.

   >[!NOTE]
   >
   >Para certificar-se de que seu mapa de processos esteja salvo como um [!DNL *.vw] arquivo, na [!DNL Save As] janela, defina Salvar como tipo para Todos os arquivos.

1. (Opcional) Para disponibilizar as alterações para todos os usuários do perfil de trabalho, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
