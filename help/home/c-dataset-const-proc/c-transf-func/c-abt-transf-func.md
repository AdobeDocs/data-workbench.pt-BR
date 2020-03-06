---
description: A funcionalidade de transformação (Transform) é executada em uma máquina de servidor de análise de big data para permitir a exportação de dados de origem de log para uso por outros aplicativos.
solution: Analytics
title: Sobre a funcionalidade de transformação
topic: Data workbench
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sobre a funcionalidade de transformação{#about-transformation-functionality}

A funcionalidade de transformação (Transform) é executada em uma máquina de servidor de análise de big data para permitir a exportação de dados de origem de log para uso por outros aplicativos.

[!DNL Transform] pode ler [!DNL .vsl] arquivos, arquivos de log, arquivos XML e dados ODBC e exportar os dados como [!DNL .vsl] arquivos, arquivos de texto ou arquivos de texto delimitados que podem ser usados por rotinas de carregamento do DataWarehouse, agências de auditoria ou outros destinos. A extração e transformação de dados podem ser realizadas de forma contínua ou programada.

>[!NOTE]
>
>Normalmente, [!DNL Transform] é configurado em um FSU de servidor de análise de big data. No entanto, sua implementação pode exigir configuração em uma DPU de servidor de análise de big data. Para obter mais informações, entre em contato com a Adobe.

Você pode exibir informações de uso de memória para [!DNL Transform] na interface de Status detalhado. Para obter mais informações, consulte o capítulo Interfaces administrativas do Guia *do usuário da Análise de* big data.

O recurso de exportação de segmento fornece outro meio de exportar dados de um aplicativo da Adobe. [!DNL Transform] permite exportar dados não processados para um destino externo, mas o recurso de exportação de segmento permite que você produza dados processados do conjunto de dados e requer que os dados exportados sejam definidos como uma dimensão no conjunto de dados. Para obter mais informações sobre exportação de segmentos, consulte o Guia *do Usuário da Análise de* big data.
