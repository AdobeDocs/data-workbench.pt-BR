---
description: Um conjunto de relatórios é uma coleção de espaços de trabalho gerados pelo Servidor de relatórios com base nos valores especificados em um arquivo de configuração Report.cfg .
title: Entender conjuntos de relatórios
uuid: 421055d7-0cf0-4664-b944-327a254a97a4
exl-id: 95609a1a-e70c-41e2-ace3-0cb09f77705a
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 4%

---

# Entender conjuntos de relatórios{#understanding-report-sets}

Um conjunto de relatórios é uma coleção de espaços de trabalho gerados pelo Servidor de relatórios com base nos valores especificados em um arquivo de configuração Report.cfg .

Na pasta de instalação [!DNL Insight], cada subpasta dentro da pasta &lt;*nome do perfil de trabalho*\Reports representa um conjunto de relatórios que foi criado. Cada conjunto de relatórios tem seu próprio arquivo de configuração [!DNL Report.cfg] nessa subpasta.

>[!NOTE]
>
>No [!DNL Profile Manager] no Data Workbench, os conjuntos de relatórios aparecem como subpastas dentro da pasta [!DNL Reports]. Para obter mais informações sobre o [!DNL Profile Manager], consulte o [Guia do Usuário do Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/home.html#Data_Workbench_Help).

Ao definir configurações específicas para um conjunto de relatórios em seu arquivo [!DNL Report.cfg], é possível agendar a criação e distribuição dos relatórios, incluindo quem recebe quais relatórios e em quais formatos.
