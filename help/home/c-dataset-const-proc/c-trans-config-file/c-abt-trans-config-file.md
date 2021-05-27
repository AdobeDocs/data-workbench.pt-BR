---
description: O arquivo Transformation.cfg controla a fase de transformação da construção do conjunto de dados, durante a qual transformações de dados adicionais são aplicadas aos dados já processados durante o processamento de log para criar dimensões estendidas para uso na análise.
title: Sobre o arquivo de configuração de transformação
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
exl-id: 860562d7-6ed3-486b-9f62-1bd06878bf7e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 5%

---

# Sobre o arquivo de configuração de transformação{#about-the-transformation-configuration-file}

O arquivo Transformation.cfg controla a fase de transformação da construção do conjunto de dados, durante a qual transformações de dados adicionais são aplicadas aos dados já processados durante o processamento de log para criar dimensões estendidas para uso na análise.

Você deve editar o arquivo [!DNL Transformation.cfg] para executar qualquer uma das seguintes tarefas de configuração do conjunto de dados:

* Filtrar dados do processamento de log definindo o [!DNL log entry condition] para transformação.
* Definir o fuso horário a ser usado para criar dimensões de tempo e fazer conversões de tempo. Consulte [Fusos horários](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956).

>[!NOTE]
>
>[!DNL Transformation Dataset Include] os arquivos podem conter instruções adicionais para a fase de transformação da construção do conjunto de dados. Esses arquivos existem no diretório Dataset\Transformation para qualquer perfil herdado e normalmente definem parâmetros específicos do aplicativo (como parâmetros de configuração específicos da Web para o aplicativo [!DNL Site]). Para obter informações sobre arquivos [!DNL Transformation Dataset Include], consulte [Arquivos de inclusão do conjunto de dados](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Para obter informações sobre parâmetros de configuração específicos da Web para o Site, consulte [Configurações para Dados da Web](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).
