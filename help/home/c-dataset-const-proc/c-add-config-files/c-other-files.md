---
description: O diretório Dataset inclui arquivos adicionais necessários para a operação do software ou fornece funcionalidade adicional para a implementação da Adobe.
solution: Analytics
title: Outros arquivos
topic: Data workbench
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Outros arquivos{#other-files}

O diretório Dataset inclui arquivos adicionais necessários para a operação do software ou fornece funcionalidade adicional para a implementação da Adobe.

* **[!DNL Client.cfg:]** O arquivo no diretório Dataset do [!DNL Client.cfg] [!DNL Base] perfil é necessário para a operação do software. Não exclua nem modifique nenhum dos parâmetros do [!DNL Client.cfg] arquivo.

* **[!DNL Cluster.cfg:]** O arquivo no diretório Dataset do [!DNL Cluster.cfg] [!DNL Base] perfil é necessário para a operação do software. No [!DNL Cluster.cfg] arquivo, você deve modificar somente o parâmetro Normalizar servidor se estiver configurando um conjunto de dados a ser processado em um cluster de servidor de análise de big data. Para obter instruções para modificar o parâmetro Normalizar servidor, consulte [Criação de um servidor de normalização centralizado para um cluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]e[!DNL Insight Transform Mode.cfg]:**Se estiver usando a funcionalidade de transformação, você terá dois arquivos de configuração adicionais, análise de big data[!DNL Transform.cfg]e análise de big data[!DNL TransformMode.cfg], no diretório Conjunto de dados para o[!DNL Transform]perfil. Para obter informações sobre esses arquivos e seus parâmetros, consulte[Transformar funcionalidade](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* O arquivo **PAServer.cfg** . Se você quiser enviar trabalhos de cluster do Predictive Analytics para os Servidores Insight, será necessário configurar o [!DNL PAServer.cfg] arquivo para lidar com envios de cluster do lado do servidor.
O perfil personalizado deve herdar o perfil [!DNL PAServer.cfg] do Predictive Analytics ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Defina um servidor ** mestre neste arquivo e salve-o [!DNL PAServer.cfg] no site de implementação.   >
   >
   >
   ```>
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```  >
   >



