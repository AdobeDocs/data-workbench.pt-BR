---
description: O Insight Server permite que você defina dimensões contáveis, simples, muitas para muitas, numéricas, desnormalizadas e de tempo para inclusão em seu conjunto de dados.
solution: Analytics
title: Tipos de dimensões estendidas
topic: Data workbench
uuid: 68f42903-0599-43f2-8b5b-da9e171d77b1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Tipos de dimensões estendidas{#types-of-extended-dimensions}

O Insight Server permite que você defina dimensões contáveis, simples, muitas para muitas, numéricas, desnormalizadas e de tempo para inclusão em seu conjunto de dados.

Cada tipo de dimensão tem um conjunto de parâmetros cujos valores você edita para fornecer instruções específicas para que o Insight Server crie as dimensões durante a fase de transformação da construção do conjunto de dados.

Embora alguns dos parâmetros sejam diferentes entre os tipos de dimensão, todos exigem a especificação de uma dimensão pai (o parâmetro Pai). A dimensão pai determina quais entradas de log das fontes de log são fornecidas como entrada para a nova dimensão. Em outras palavras, as entradas de log associadas aos elementos da dimensão pai são aquelas associadas à nova dimensão antes da aplicação de qualquer filtro. A dimensão pai também determina a posição da nova dimensão na hierarquia do conjunto de dados, chamada de esquema do conjunto de dados. Para obter informações sobre a interface que mostra o esquema do conjunto de dados, consulte Ferramentas [de Configuração do](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)Conjunto de Dados.

Depois que o Insight Server usa a dimensão pai para determinar quais entradas de log devem ser consideradas na criação da dimensão, ele aplica as condições especificadas (o parâmetro Condição) para deixar em branco as entradas de log que não satisfazem a condição. Em seguida, o servidor identifica o valor do campo de entrada especificado (o parâmetro Input) para cada entrada de log e aplica a operação especificada (o parâmetro Operation), se aplicável.

>[!NOTE]
>
>Se uma entrada de log não atender à Condição de uma dimensão estendida, o Insight Server substituirá valores em branco para todos os campos na entrada de log. A entrada do log real ainda existe e a Operação especificada determina se o valor em branco do [!DNL Input] campo é usado.
