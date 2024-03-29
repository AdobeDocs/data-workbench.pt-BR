---
description: Muitos dos perfis internos recebidos com seu aplicativo Adobe vêm com seus próprios arquivos de configuração de conjunto de dados.
title: Sobre os arquivos de inclusão do conjunto de dados
uuid: e04d412e-7d73-4a7d-b0b6-0c2347c6201b
exl-id: a23d3f83-4e92-4787-9f77-ee9914cb8893
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 4%

---

# Sobre os arquivos de inclusão do conjunto de dados{#about-dataset-include-files}

{{eol}}

Muitos dos perfis internos recebidos com seu aplicativo Adobe vêm com seus próprios arquivos de configuração de conjunto de dados.

Como os perfis internos são subperfis do perfil do conjunto de dados, seus arquivos de configuração do conjunto de dados contêm regras que fornecem parâmetros adicionais para as fases de processamento ou transformação do log da construção do conjunto de dados. Os arquivos de configuração do conjunto de dados para perfis internos e para qualquer perfil herdado criado são chamados de arquivos de inclusão do conjunto de dados.

Um arquivo de inclusão do conjunto de dados contém um subconjunto dos parâmetros contidos nos arquivos de configuração do conjunto de dados principal ( [!DNL Log Processing.cfg] ou [!DNL Transformation.cfg]) para o perfil do conjunto de dados. Os arquivos de inclusão do conjunto de dados que contêm parâmetros associados ao processamento de log são chamados [!DNL Log Processing Dataset Include] arquivos (consulte [Arquivos de dados do conjunto de dados de processamento de log](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)), enquanto o conjunto de dados inclui arquivos associados à transformação são chamados [!DNL Transformation Dataset Include] Arquivos. Consulte [Arquivos de inclusão do conjunto de dados de transformação](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace). Você pode criar vários arquivos de inclusão do conjunto de dados para uso no processo de construção do conjunto de dados. O conjunto de dados completo inclui todos os campos, transformações e dimensões estendidas definidas em todos os arquivos de configuração do conjunto de dados para o perfil do conjunto de dados e qualquer perfil herdado.
