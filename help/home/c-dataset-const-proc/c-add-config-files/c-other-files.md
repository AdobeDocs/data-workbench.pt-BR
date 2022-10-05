---
description: O diretório do conjunto de dados inclui arquivos adicionais que são necessários para a operação do software ou que fornecem funcionalidade adicional para a implementação do Adobe.
title: Outros arquivos
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 1%

---

# Outros arquivos{#other-files}

{{eol}}

O diretório do conjunto de dados inclui arquivos adicionais que são necessários para a operação do software ou que fornecem funcionalidade adicional para a implementação do Adobe.

* **[!DNL Client.cfg:]** O [!DNL Client.cfg] no diretório do conjunto de dados para o [!DNL Base] é necessário para a operação do software. Não exclua nem modifique qualquer um dos parâmetros no [!DNL Client.cfg] arquivo.

* **[!DNL Cluster.cfg:]** O [!DNL Cluster.cfg] no diretório do conjunto de dados para o [!DNL Base] é necessário para a operação do software. No [!DNL Cluster.cfg] , você deve modificar somente o parâmetro Normalizar servidor se estiver configurando um conjunto de dados a ser processado em um cluster de servidores do Data Workbench. Para obter instruções para modificar o parâmetro Normalizar servidor, consulte [Criando um servidor de normalização centralizado para um cluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]e [!DNL Insight Transform Mode.cfg]:** Se estiver usando a funcionalidade de transformação, você terá dois arquivos de configuração adicionais, o Data Workbench [!DNL Transform.cfg] e Data Workbench [!DNL TransformMode.cfg], no diretório do conjunto de dados para o [!DNL Transform] perfil. Para obter informações sobre esses arquivos e seus parâmetros, consulte [Funcionalidade de transformação](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* O **PAServer.cfg** arquivo. Se você quiser enviar trabalhos de cluster do Predictive Analytics para os servidores Insight, será necessário configurar o [!DNL PAServer.cfg] para lidar com envios de cluster do lado do servidor.
O perfil personalizado deve herdar a variável [!DNL PAServer.cfg] no perfil do Predictive Analytics ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Defina um *Servidor principal* neste arquivo e salve o [!DNL PAServer.cfg] ao local de implementação.
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
