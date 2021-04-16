---
description: O diretório do conjunto de dados inclui arquivos adicionais que são necessários para a operação do software ou que fornecem funcionalidade adicional para a implementação do Adobe.
title: Outros arquivos
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 1%

---

# Outros arquivos{#other-files}

O diretório do conjunto de dados inclui arquivos adicionais que são necessários para a operação do software ou que fornecem funcionalidade adicional para a implementação do Adobe.

* **[!DNL Client.cfg:]** O  [!DNL Client.cfg] arquivo no diretório do conjunto de dados do  [!DNL Base] perfil é necessário para a operação do software. Não exclua nem modifique qualquer um dos parâmetros no arquivo [!DNL Client.cfg].

* **[!DNL Cluster.cfg:]** O  [!DNL Cluster.cfg] arquivo no diretório do conjunto de dados do  [!DNL Base] perfil é necessário para a operação do software. No arquivo [!DNL Cluster.cfg], você deve modificar somente o parâmetro Normalizar servidor se estiver configurando um conjunto de dados a ser processado em um cluster de servidor do Data Workbench. Para obter instruções para modificar o parâmetro Normalizar servidor, consulte [Criando um servidor de normalização centralizado para um cluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]e  [!DNL Insight Transform Mode.cfg]:** se estiver usando a funcionalidade de transformação, você terá dois arquivos de configuração adicionais, o Data Workbench  [!DNL Transform.cfg] e o Data Workbench  [!DNL TransformMode.cfg], no diretório do conjunto de dados para o  [!DNL Transform] perfil. Para obter informações sobre esses arquivos e seus parâmetros, consulte [Funcionalidade de transformação](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* O arquivo **PAServer.cfg**. Se você quiser enviar trabalhos de cluster do Predictive Analytics para os Servidores Insight, será necessário configurar o arquivo [!DNL PAServer.cfg] para lidar com envios de cluster do lado do servidor.
O perfil personalizado deve herdar o [!DNL PAServer.cfg] do perfil de Análise preditiva ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Defina um *Servidor Principal* neste arquivo e salve o [!DNL PAServer.cfg] no site de implementação.
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
