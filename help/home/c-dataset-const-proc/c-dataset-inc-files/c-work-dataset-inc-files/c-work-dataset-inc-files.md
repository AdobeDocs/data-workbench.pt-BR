---
description: O conjunto de dados inclui arquivos que fornecem uma maneira flexível de configurar seu conjunto de dados.
solution: Analytics
title: Trabalhar com arquivos de inclusão de conjunto de dados
topic: Data workbench
uuid: 258226c4-22e5-4d9d-9044-8312709e0460
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Trabalhar com arquivos de inclusão de conjunto de dados{#working-with-dataset-include-files}

O conjunto de dados inclui arquivos que fornecem uma maneira flexível de configurar seu conjunto de dados.

Dentro de cada arquivo, é possível definir quantos campos, transformações ou dimensões desejar e organizar os arquivos de inclusão com base no perfil herdado ao qual eles pertencem. Ao configurar seu conjunto de dados, você tem a opção de editar o conjunto de dados e incluir arquivos fornecidos com os perfis internos para seu aplicativo Adobe ou criar um novo conjunto de dados incluindo arquivos para qualquer perfil herdado que você criar.

Ao editar os parâmetros de um conjunto de dados, inclua um arquivo para um perfil interno e salve o arquivo atualizado no seu perfil de conjunto de dados ou em um perfil herdado que você criou, você está substituindo as configurações originais do arquivo. A Adobe recomenda que a edição de um conjunto de dados inclua um arquivo para um perfil interno sempre que for necessário fazer pequenas alterações no conteúdo do conjunto de dados, como alterar um parâmetro Condition ou a configuração padrão de um parâmetro. Consulte [Edição De Conjuntos De Dados Existentes Incluir Arquivos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077). No entanto, quando você deseja especificar um novo campo a ser transmitido do processamento de log para a transformação, atualizar ou criar novos campos usando transformações ou definir dimensões estendidas, é melhor criar um novo arquivo de inclusão de conjunto de dados. Consulte [Criação de novos conjuntos de dados que incluem arquivos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e). É possível editar o arquivo que você cria sempre que quiser ou no lugar que quiser.
