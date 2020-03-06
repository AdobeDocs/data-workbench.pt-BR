---
description: As transformações permitem extrair informações disponíveis nos arquivos de dados e manipulá-las em um formulário mais útil.
solution: Analytics
title: Sobre transformações
topic: Data workbench
uuid: 9366f607-741d-4512-9e1b-4165f4291246
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Sobre transformações{#about-transformations}

As transformações permitem extrair informações disponíveis nos arquivos de dados e manipulá-las em um formulário mais útil.

As transformações operam nas entradas de log (você pode considerar as entradas de log como linhas de dados) nas fontes de log. Para cada linha de dados, a transformação toma o valor do campo de entrada especificado, executa um conjunto de etapas de processamento e registra o resultado no campo de saída que você especificar. Você pode definir transformações a serem executadas durante a fase de processamento ou transformação do log do processo de construção do conjunto de dados:

* **Durante o processamento do log:** As transformações executadas durante a fase de processamento de log da construção do conjunto de dados são aplicadas a cada registro de dados de evento (entrada de log) para atualizar campos de log existentes ou produzir novos campos. Os resultados das transformações são usados juntamente com as condições de entrada do log para avaliar quais entradas do log são filtradas do conjunto de dados durante o processamento do log.
* **Durante a transformação:** As transformações executadas durante a fase de transformação da construção do conjunto de dados operam nos campos de dados passados do processamento de log para criar dimensões estendidas que podem ser usadas em suas análises. Consulte Dimensões [estendidas](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

>[!NOTE]
>
>A entrada de dados para transformação do processamento de log é ordenada por tempo e agrupada pela ID de rastreamento nos dados de origem. Várias transformações exigem que os dados estejam nessa forma e funcionem somente quando definidos durante a transformação.

As mudanças nas transformações devem ser feitas com cuidado. As transformações não afetam quais entradas de log fluem no processo de construção do conjunto de dados, mas afetam os resultados apresentados. Isso permite alterar o que está sendo analisado sem alterar os dados nos quais a análise se baseia. Mas mudanças nas transformações podem alterar fundamentalmente os valores produzidos nas análises.
