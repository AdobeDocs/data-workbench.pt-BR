---
description: O arquivo Log Processing.cfg controla a fase de processamento de log da construção do conjunto de dados, durante a qual os dados não ordenados são lidos das fontes de dados (chamadas de fontes de log), e os filtros e transformações são aplicados aos dados.
solution: Analytics
title: Sobre o arquivo de configuração de processamento de log
topic: Data workbench
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Sobre o arquivo de configuração de processamento de log{#about-the-log-processing-configuration-file}

O arquivo Log Processing.cfg controla a fase de processamento de log da construção do conjunto de dados, durante a qual os dados não ordenados são lidos das fontes de dados (chamadas de fontes de log), e os filtros e transformações são aplicados aos dados.

É necessário editar o [!DNL Log Processing.cfg] arquivo para executar qualquer uma das seguintes tarefas de configuração do conjunto de dados:

* Especificação de fontes de log. Consulte Fontes [de registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md).
* Determinar quais entradas de log inserem o conjunto de dados durante o processamento do log. Consulte Filtros [de dados e Condição](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md) de entrada [](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md)do registro.

* Habilitar a divisão de IDs de rastreamento com grandes quantidades de dados de evento. Consulte [Divisão](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md)de chaves.
* Configurando um servidor de análise de big data para ser executado como uma unidade de servidor de arquivos. Consulte [Configurando uma unidade](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)do servidor de arquivos do Insight Server.
* Configurando um servidor de análise de big data para ser executado como um servidor de normalização centralizado. Consulte [Configurando uma unidade](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)do servidor de arquivos do Insight Server.

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] os arquivos podem conter instruções adicionais para a fase de processamento de log da construção do conjunto de dados. Esses arquivos existem no diretório Dataset\Log Processing para qualquer perfil herdado. Normalmente, eles definem parâmetros específicos do aplicativo (como parâmetros de configuração específicos da Web para o aplicativo Site). Para obter informações sobre [!DNL Log Processing Dataset Include] arquivos, consulte [Arquivo de inclusão de conjuntos de dados](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Para obter informações sobre parâmetros de configuração específicos da Web para o Site, consulte Configurações [de configuração para dados](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md)da Web.

