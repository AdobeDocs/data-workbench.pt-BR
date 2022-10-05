---
description: Os mapas de processos podem ser configurados para funcionar com qualquer combinação de dimensão base, dimensão de grupo, dimensão de nível e métrica que faça sentido para seu aplicativo e conjunto de dados.
title: Configurar um mapa de processos
uuid: e629191e-48b9-4b58-b6aa-3705ff7b387e
exl-id: 0b37e942-4596-45cc-bc31-db147626f4eb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 1%

---

# Configurar um mapa de processos{#configure-a-process-map}

{{eol}}

Os mapas de processos podem ser configurados para funcionar com qualquer combinação de dimensão base, dimensão de grupo, dimensão de nível e métrica que faça sentido para seu aplicativo e conjunto de dados.

Depois de configurar um mapa de processos, ele é listado com outros mapas de processos na [!DNL Add Visualization menu].

1. No [!DNL Profile Manager], clique em **[!UICONTROL Menu]**, clique em **[!UICONTROL Add Visualization]**, clique no tipo de mapa de processos que deseja configurar (Mapa de Métricas 2D, Mapa de Processos 2D ou Mapa de Processos 3D).

   Pelo menos um [!DNL *.vw] O arquivo reside no diretório .

1. Clique com o botão direito do mouse na marca de seleção do arquivo desejado e clique em **[!UICONTROL Make Local]**.
1. Clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
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
   <th colname="col2" class="entry"> Fornecer essas informações... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Nome da métrica</i> </p> </td> 
   <td colname="col2"> <p>O nome da métrica cujo valor para um determinado nó é proporcional ao tamanho do nó. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome da dimensão base</i> </p> </td> 
   <td colname="col2"> <p>O nome da dimensão cujos elementos aparecem como nós no mapa de processos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome da dimensão de nível</i> </p> </td> 
   <td colname="col2"> <p>O nome do nível (pai) da dimensão base cujos elementos você arrasta para o mapa de processos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome da dimensão do grupo</i> </p> </td> 
   <td colname="col2"> <p>O nome da dimensão que determina como os elementos da dimensão de nível são agrupados para formar as conexões entre nós. Uma conexão entre dois nós não pode estender mais de um elemento de uma dimensão de grupo. Ao fazer uma seleção com base em um nó em um mapa de processos, você está selecionando todos os elementos da dimensão de grupo que envolveu esse nó. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nome da métrica para mapa de métricas</i> </p> </td> 
   <td colname="col2"> <p>Esse parâmetro se aplica somente aos mapas de métrica 2D. </p> <p>O nome da métrica cujo valor determina a posição horizontal dos nós no mapa. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Para obter mais informações sobre a dimensão base, a dimensão de grupo, a dimensão de nível e a métrica para um mapa de processos, consulte [Mapas de processos](../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

1. No Bloco de notas, clique em **[!UICONTROL File]** > **[!UICONTROL Save As]** para salvar o arquivo com um novo nome com base na dimensão base, ou seja, *Nome da dimensão base*.vw.

   (Se você estiver configurando um mapa de métrica 2D, deverá salvar o arquivo com um nome baseado no nome da métrica para o mapa de métrica, ou seja, *Nome da métrica para mapa de métricas*.vw.) Salve o arquivo no diretório apropriado do mapa de processos.

   >[!NOTE]
   >
   >Para garantir que o mapa de processos seja salvo como um [!DNL *.vw] , na [!DNL Save As] , defina Salvar como tipo para Todos os arquivos.

1. (Opcional) Para disponibilizar as alterações para todos os usuários do perfil de trabalho, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo no [!DNL User] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
