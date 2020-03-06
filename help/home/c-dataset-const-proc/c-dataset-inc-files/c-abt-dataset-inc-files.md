---
description: Muitos dos perfis internos que você recebeu com seu aplicativo Adobe vêm com seus próprios arquivos de configuração de conjunto de dados.
solution: Analytics
title: Sobre os arquivos de inclusão de conjuntos de dados
topic: Data workbench
uuid: e04d412e-7d73-4a7d-b0b6-0c2347c6201b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sobre os arquivos de inclusão de conjuntos de dados{#about-dataset-include-files}

Muitos dos perfis internos que você recebeu com seu aplicativo Adobe vêm com seus próprios arquivos de configuração de conjunto de dados.

Como os perfis internos são subperfis do perfil do conjunto de dados, seus arquivos de configuração do conjunto de dados contêm regras que fornecem parâmetros adicionais para as fases de processamento de log ou transformação da construção do conjunto de dados. Os arquivos de configuração do conjunto de dados para perfis internos e para qualquer perfil herdado criado são chamados de arquivos de inclusão do conjunto de dados.

Um arquivo de inclusão de conjunto de dados contém um subconjunto dos parâmetros contidos nos arquivos de configuração do conjunto de dados principal ( [!DNL Log Processing.cfg] ou [!DNL Transformation.cfg]) para o perfil do conjunto de dados. O conjunto de dados inclui arquivos que contêm parâmetros associados ao processamento de log chamados de [!DNL Log Processing Dataset Include] arquivos (consulte Arquivos [Incluir Conjunto de Dados de Processamento de](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)Log), enquanto o conjunto de dados inclui arquivos associados à transformação chamados de [!DNL Transformation Dataset Include] Arquivos. Consulte [Transformation Dataset Incluir Arquivos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace). É possível criar vários arquivos de inclusão de conjunto de dados para uso no processo de construção do conjunto de dados. O conjunto de dados completo inclui todos os campos, transformações e dimensões estendidas definidas em todos os arquivos de configuração do conjunto de dados para o perfil do conjunto de dados e quaisquer perfis herdados.
