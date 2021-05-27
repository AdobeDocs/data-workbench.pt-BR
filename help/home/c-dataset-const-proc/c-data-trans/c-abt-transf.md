---
description: As transformações permitem extrair informações disponíveis nos arquivos de dados e manipulá-las em um formulário mais útil.
title: Sobre transformações
uuid: 9366f607-741d-4512-9e1b-4165f4291246
exl-id: 9bd533ef-a87e-400a-9bb0-5af1851cca0a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 1%

---

# Sobre transformações{#about-transformations}

As transformações permitem extrair informações disponíveis nos arquivos de dados e manipulá-las em um formulário mais útil.

As transformações operam nas entradas de log (você pode considerar as entradas de log como linhas de dados) nas fontes de log. Para cada linha de dados, a transformação pega o valor do campo de entrada especificado, executa um conjunto de etapas de processamento e registra o resultado no campo de saída especificado. Você pode definir transformações a serem executadas durante a fase de processamento de log ou de transformação do processo de construção do conjunto de dados:

* **Durante o processamento de log:** as transformações executadas durante a fase de processamento de log da construção do conjunto de dados são aplicadas a cada registro de dados do evento (entrada de log) para atualizar campos de log existentes ou produzir novos campos. Os resultados das transformações são usados junto com as condições de entrada de log para avaliar quais entradas de log são filtradas do conjunto de dados durante o processamento do log.
* **Durante a transformação:** as transformações executadas durante a fase de transformação da construção do conjunto de dados operam nos campos de dados transmitidos do processamento de log para criar dimensões estendidas que podem ser usadas em suas análises. Consulte [Dimension estendido](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

>[!NOTE]
>
>A entrada de dados para transformação a partir do processamento de log é solicitada por tempo e agrupada pela ID de rastreamento nos dados de origem. Várias transformações exigem que os dados estejam nesse formulário e funcionem somente quando definidos durante a transformação.

As alterações às transformações devem ser feitas com cuidado. As transformações não afetam quais entradas de log fluem no processo de construção do conjunto de dados, mas afetam os resultados apresentados. Isso permite alterar o que está sendo analisado sem alterar os dados em que se baseia a análise. Mas mudanças nas transformações podem alterar fundamentalmente os valores produzidos nas análises.
