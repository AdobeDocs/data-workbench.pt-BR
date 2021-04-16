---
description: A funcionalidade de transformação (Transform) é executada em uma máquina de servidor do Data Workbench para permitir a exportação de dados de fonte de log para uso por outros aplicativos.
title: Sobre a funcionalidade de transformação
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
exl-id: db5d6329-407d-43f3-92fc-1b40f7289916
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 2%

---

# Sobre a funcionalidade de transformação{#about-transformation-functionality}

A funcionalidade de transformação (Transform) é executada em uma máquina de servidor do Data Workbench para permitir a exportação de dados de fonte de log para uso por outros aplicativos.

[!DNL Transform] O pode ler  [!DNL .vsl] arquivos, arquivos de log, arquivos XML e dados ODBC e exportar os dados como  [!DNL .vsl] arquivos, arquivos de texto ou arquivos de texto delimitados que podem ser usados por rotinas de carregamento de DataWarehouse, agências de auditoria ou outros destinos. A extração e transformação de dados podem ser realizadas de forma contínua ou programada.

>[!NOTE]
>
>Normalmente, [!DNL Transform] é configurado em uma FSU do servidor do Data Workbench. No entanto, sua implementação pode exigir configuração em uma DPU do servidor do Data Workbench. Para obter mais informações, entre em contato com o Adobe.

Você pode exibir informações de uso de memória para [!DNL Transform] na interface de Status detalhado. Para obter mais informações, consulte o capítulo Interfaces Administrativas do *Guia do Usuário do Data Workbench*.

O recurso de exportação de segmento fornece outro meio de exportar dados de um aplicativo Adobe. [!DNL Transform] permite exportar dados não processados para um destino externo, mas o recurso de exportação de segmento permite exportar dados processados do conjunto de dados e requer que os dados exportados sejam definidos como uma dimensão no conjunto de dados. Para obter mais informações sobre a exportação de segmentos, consulte o *Guia do Usuário do Data Workbench*.
