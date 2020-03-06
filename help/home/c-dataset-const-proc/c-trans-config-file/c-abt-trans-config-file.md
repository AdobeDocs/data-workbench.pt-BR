---
description: O arquivo Transformation.cfg controla a fase de transformação da construção do conjunto de dados durante a qual transformações adicionais de dados são aplicadas aos dados já processados durante o processamento de log para criar dimensões estendidas para uso na análise.
solution: Analytics
title: Sobre o arquivo de configuração de transformação
topic: Data workbench
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Sobre o arquivo de configuração de transformação{#about-the-transformation-configuration-file}

O arquivo Transformation.cfg controla a fase de transformação da construção do conjunto de dados durante a qual transformações adicionais de dados são aplicadas aos dados já processados durante o processamento de log para criar dimensões estendidas para uso na análise.

É necessário editar o [!DNL Transformation.cfg] arquivo para executar qualquer uma das seguintes tarefas de configuração do conjunto de dados:

* Filtragem de dados do processamento de log definindo o para transformação [!DNL log entry condition] .
* Definir o fuso horário a ser usado para criar dimensões de tempo e fazer conversões de tempo. Consulte Fusos [horários](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956).

>[!NOTE]
>
>[!DNL Transformation Dataset Include] os arquivos podem conter instruções adicionais para a fase de transformação da construção do conjunto de dados. Esses arquivos existem no diretório Dataset\Transformation para qualquer perfil herdado e normalmente definem parâmetros específicos do aplicativo (como parâmetros de configuração específicos da Web para o [!DNL Site] aplicativo). Para obter informações sobre [!DNL Transformation Dataset Include] arquivos, consulte [Arquivo de inclusão de conjuntos de dados](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Para obter informações sobre parâmetros de configuração específicos da Web para o Site, consulte Configurações [de configuração para dados](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)da Web.

