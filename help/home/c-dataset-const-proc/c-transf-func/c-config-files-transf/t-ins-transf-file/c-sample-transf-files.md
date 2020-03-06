---
description: Informações sobre como especificar parâmetros no arquivo Transform.cfg com base nos vários cenários.
solution: Analytics
title: Arquivos Transform.cfg do Análise de big data de amostra
topic: Data workbench
uuid: cb473a5a-54e2-4bf7-84fb-c9c27910ef64
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Arquivos Transform.cfg do Análise de big data de amostra{#sample-data-workbench-transform-cfg-files}

Informações sobre como especificar parâmetros no arquivo Transform.cfg com base nos vários cenários.

* [Um arquivo Simples Insight Transform.cfg](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-b7e83cafa3a947c597bd09d316930190)
* [Saída com valores separados por vírgula](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-03916934ad574efc8695abbae54a1816)
* [Arquivos de registro de amostra](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-113b3b0c0c7547ea9536bb2f465c0875)
* [Divisão de Arquivos de Log por Seção de Site](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-2cac205cd3934d31abb6c6ed8780196d)

Em cada amostra, o arquivo é exibido como uma [!DNL Transform.cfg] janela na análise de big data.

## Um arquivo Transform.cfg do Análise de big data simples {#section-b7e83cafa3a947c597bd09d316930190}

A [!DNL Transform.cfg] janela a seguir fornece instruções para ler [!DNL .vsl] arquivos do [!DNL Logs] diretório e exportar os campos x-timestring e x-trackingid para um arquivo de texto armazenado no diretório Logs\VT. Como nenhum período de rotação de arquivo ou formato de nome de arquivo de saída é especificado, cada arquivo contém dados de um dia de calendário e tem um nome no formato padrão [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SimpleExample.png)

## Saída com valores separados por vírgula {#section-03916934ad574efc8695abbae54a1816}

A [!DNL Transform.cfg] janela a seguir fornece instruções para ler [!DNL .vsl] arquivos do diretório Logs e exportar os campos de 0 a 13 para um arquivo delimitado por vírgulas ( [!DNL .csv]) armazenado no diretório Logs\VT\CSV directory. Como nenhum período de rotação de arquivos é especificado, cada arquivo contém dados de um dia de calendário. Os arquivos de saída são [!DNL .csv] arquivos nomeados no formato [!DNL %yyyy%%mm%%dd%-%x-mask%.csv].

![](assets/cfg_VisualTransform_CSVExample.png)

## Arquivos de registro de exemplo {#section-113b3b0c0c7547ea9536bb2f465c0875}

Você pode configurar a funcionalidade de transformação para criar e manter uma versão atualizada e compacta dos arquivos de registro completos. Isso permite testar rapidamente suas configurações de conjunto de dados, com tempos de reprocessamento de segundos ou minutos em vez de horas necessárias para reprocessar todo o conjunto de dados. O exemplo a seguir fornece um exemplo de como configurar a funcionalidade de transformação para fazer isso.

A [!DNL Transform.cfg] janela a seguir fornece instruções para ler [!DNL .vsl] arquivos do diretório Logs e exportar os campos x-timestring e x-trackingid para um arquivo de texto armazenado no diretório Logs\VT. O Limite de Hash especificado filtra determinadas IDs de rastreamento do conjunto de dados, criando assim um conjunto de dados que é amostrado por um fator de 100. Como nenhum período de rotação de arquivos é especificado, cada arquivo contém dados de um dia de calendário. Os nomes dos arquivos de saída estão no formato padrão [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SampledExample.png)

## Divisão de Arquivos de Log por Seção de Site {#section-2cac205cd3934d31abb6c6ed8780196d}

A [!DNL Transform.cfg] janela a seguir fornece instruções para ler [!DNL .vsl]arquivos do diretório Logs e exportar os campos x-timestring e x-trackingid para um arquivo de texto armazenado no diretório Logs\VT. A transformação de expressão regular ( [!DNL RETransform]) assume como entrada o campo de tronco cs-uri e cria um novo campo (x-site) que define uma seção do site. O campo x-site é incluído no nome dos arquivos de texto de saída, cada um dos quais contém dados de um dia de calendário.

![](assets/cfg_VisualTransform_SplittingExample.png)

