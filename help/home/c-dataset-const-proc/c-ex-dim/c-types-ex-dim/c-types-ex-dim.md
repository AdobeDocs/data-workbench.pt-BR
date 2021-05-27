---
description: O servidor Insight permite que você defina dimensões contáveis, simples, muitas para muitas, numéricas, desnormalizadas e de tempo para inclusão em seu conjunto de dados.
title: Tipos de dimensões estendidas
uuid: 68f42903-0599-43f2-8b5b-da9e171d77b1
exl-id: 13a52ece-b68b-45bc-ac2d-d68c91742c9d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 2%

---

# Tipos de dimensões estendidas{#types-of-extended-dimensions}

O servidor Insight permite que você defina dimensões contáveis, simples, muitas para muitas, numéricas, desnormalizadas e de tempo para inclusão em seu conjunto de dados.

Cada tipo de dimensão tem um conjunto de parâmetros cujos valores você edita para fornecer instruções específicas para o Servidor Insight criar as dimensões durante a fase de transformação da construção do conjunto de dados.

Embora alguns dos parâmetros sejam diferentes entre os tipos de dimensão, todos exigem a especificação de uma dimensão pai (o parâmetro Pai ). A dimensão pai determina quais entradas de log das fontes de log são fornecidas como entrada para a nova dimensão. Em outras palavras, as entradas de log associadas aos elementos da dimensão pai são aquelas que estão associadas à nova dimensão antes de qualquer filtragem ser aplicada. A dimensão pai também determina a posição da nova dimensão na hierarquia do conjunto de dados, chamada de schema do conjunto de dados. Para obter informações sobre a interface que mostra o esquema do conjunto de dados, consulte [Ferramentas de Configuração do Conjunto de Dados](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

Depois que o Servidor Insight usa a dimensão pai para determinar quais entradas de log devem ser consideradas na criação da dimensão, ele aplica as condições especificadas (o parâmetro Condição ) para deixar em branco as entradas de log que não atendem à condição. O servidor identifica o valor do campo de entrada especificado (o parâmetro Input ) para cada entrada de log e aplica a operação especificada (o parâmetro Operation ), se aplicável.

>[!NOTE]
>
>Se uma entrada de log não atender à condição de uma dimensão estendida, o Insight Server substituirá valores em branco para todos os campos na entrada de log. A entrada de log real ainda existe e a Operação especificada determina se o valor em branco do campo [!DNL Input] é usado.
