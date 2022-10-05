---
description: O arquivo Log Processing.cfg controla a fase de processamento de log da construção do conjunto de dados, durante a qual os dados não ordenados são lidos a partir das fontes de dados (chamadas de fontes de log), e filtros e transformações são aplicados aos dados.
title: Sobre o arquivo de configuração de processamento de log
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
exl-id: 11ee3298-272d-46c8-bcfe-e485b01606b1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 5%

---

# Sobre o arquivo de configuração de processamento de log{#about-the-log-processing-configuration-file}

{{eol}}

O arquivo Log Processing.cfg controla a fase de processamento de log da construção do conjunto de dados, durante a qual os dados não ordenados são lidos a partir das fontes de dados (chamadas de fontes de log), e filtros e transformações são aplicados aos dados.

Você deve editar o [!DNL Log Processing.cfg] para executar qualquer uma das seguintes tarefas de configuração do conjunto de dados:

* Especificação de fontes de log. Consulte [Fontes de log](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md).
* Determinar quais entradas de log inserem o conjunto de dados durante o processamento do log. Consulte [Filtros de dados](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md) e [Condição de entrada de log](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).

* Habilitar a divisão das IDs de rastreamento por grandes quantidades de dados de evento. Consulte [Divisão de chave](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).
* Configurar um servidor do Data Workbench para ser executado como uma unidade de servidor de arquivos. Consulte [Configurar uma unidade de servidor de arquivos do servidor Insight](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).
* Configurar um servidor do Data Workbench para ser executado como um servidor de normalização centralizado. Consulte [Configurar uma unidade de servidor de arquivos do servidor Insight](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] os arquivos podem conter instruções adicionais para a fase de processamento de log da construção do conjunto de dados. Esses arquivos existem no diretório Dataset\Log Processing para qualquer perfil herdado. Normalmente, eles definem parâmetros específicos do aplicativo (como parâmetros de configuração específicos da Web para o aplicativo Site). Para obter informações sobre [!DNL Log Processing Dataset Include] arquivos, consulte [Arquivos de inclusão do conjunto de dados](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Para obter informações sobre parâmetros de configuração específicos da Web para o Site, consulte [Configurações para dados da Web](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md).
