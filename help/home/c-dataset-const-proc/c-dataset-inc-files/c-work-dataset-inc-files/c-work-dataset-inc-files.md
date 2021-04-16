---
description: Os arquivos de inclusão do conjunto de dados fornecem uma maneira flexível para configurar seu conjunto de dados.
title: Trabalhar com arquivos de inclusão do conjunto de dados
uuid: 258226c4-22e5-4d9d-9044-8312709e0460
exl-id: 94044c85-030c-4912-9546-d4a34b4115e0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 4%

---

# Trabalhar com arquivos de inclusão do conjunto de dados{#working-with-dataset-include-files}

Os arquivos de inclusão do conjunto de dados fornecem uma maneira flexível para configurar seu conjunto de dados.

Em cada arquivo, é possível definir quantos campos, transformações ou dimensões desejar e organizar os arquivos de inclusão com base no perfil herdado ao qual eles pertencem. Ao configurar seu conjunto de dados, você tem a opção de editar os arquivos de inclusão do conjunto de dados fornecidos com os perfis internos para seu aplicativo do Adobe ou criar novos arquivos de inclusão do conjunto de dados para qualquer perfil herdado que você criar.

Ao editar os parâmetros de um conjunto de dados, inclua um arquivo para um perfil interno e salve o arquivo atualizado no perfil do conjunto de dados ou em um perfil herdado que você criou, você está substituindo as configurações originais do arquivo. O Adobe recomenda editar um arquivo de inclusão de conjunto de dados para um perfil interno sempre que for necessário fazer pequenas alterações no conteúdo do conjunto de dados, como alterar um parâmetro de Condição ou a configuração padrão de um parâmetro. Consulte [Editar arquivos de inclusão existentes do conjunto de dados](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077). No entanto, quando você deseja especificar um novo campo que será transmitido do processamento de log para a transformação, atualizar ou criar novos campos usando transformações ou definir dimensões estendidas, é melhor criar um novo arquivo de inclusão de conjunto de dados. Consulte [Criar novos arquivos de inclusão do conjunto de dados](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e). Você pode editar o arquivo que criar sempre ou onde quiser.
