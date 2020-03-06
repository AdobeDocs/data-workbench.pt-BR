---
description: Links para informações adicionais sobre parâmetros específicos no arquivo Log Processing.cfg.
solution: Analytics
title: Parâmetros de processamento de log
topic: Data workbench
uuid: 97b25665-f588-4f44-8f71-2382600d1b6f
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Parâmetros de processamento de log{#log-processing-parameters}

Links para informações adicionais sobre parâmetros específicos no arquivo Log Processing.cfg.

<!--
c_data_filters.xml
-->

## Filtros de dados {#data-filters}

Os filtros definidos no [!DNL Log Processing.cfg] arquivo incluem o seguinte:

* Hora de término
* Limite de hash
* Hora inicial

A filtragem definida por esses parâmetros ocorre depois que as entradas de log deixam os decodificadores e depois das transformações, mas antes de sua avaliação pelo [!DNL Log Entry Condition]. Em geral, alterar qualquer um desses parâmetros resulta em alterações na composição do conjunto de dados.

A técnica recomendada para usar fontes de [!DNL Sensor] dados para construir um conjunto de dados que abrange um período específico é usar os parâmetros Hora de início e Hora de término para o conjunto de dados.

O uso dos parâmetros Hora de início e Hora de término é preferido a outras técnicas, como mover arquivos de log para separá-los por diretório. Ao definir as horas de início e término do conjunto de dados, o servidor da análise de big data usa automaticamente apenas as entradas de log que ocorreram dentro de um determinado intervalo. Supondo que a Hora de término já tenha sido ultrapassada, o servidor da análise de big data normalmente atualiza o conjunto de dados usando o mesmo conjunto de entradas de log, mesmo se o conjunto de dados for atualizado, por exemplo, adicionando uma nova transformação.

<!--
c_log_entry_con.xml
-->

## Entrada do registro

Em essência, é um processo de filtragem nas entradas de log disponíveis. Se o [!DNL Log Entry Condition] retornar um valor de false, a entrada de log será filtrada do conjunto disponível de entradas de log.

O teste [!DNL Log Entry Condition] é descrito por meio de operações de condição (consulte [Condições](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) e pode usar qualquer um dos campos de entrada coletados por [!DNL Sensor] (consulte o Guia *da Bancada de[!DNL Sensor]Dados ) ou quaisquer campos estendidos produzidos por transformações contidas no* [!DNL Log Processing.cfg] arquivo para definir as condições de teste. [!DNL Log Entry] são aplicadas durante o processamento de log e opcionalmente podem ser aplicadas durante a transformação.

Este exemplo demonstra o uso do para dados do site [!DNL log entry condition] . Você pode usar o para [!DNL Log Entry Condition] criar conjuntos de dados que se concentrem em uma parte específica do site ou visitantes que executam alguma ação específica no site.

O [!DNL Log Entry Condition] neste exemplo cria um conjunto de dados que inclui apenas as entradas de log que fazem parte da loja do site. Ao usar o padrão [!DNL RECondition test] com o padrão correspondente [!DNL "/store/.*"] e o [!DNL cs-uri-stem] campo como entrada para a expressão regular, somente as páginas da Web que começam com a string [!DNL "/store/"] são incluídas no conjunto de dados.

![](assets/cfg_LogProcessing_LogEntryCondition.png)

<!--
c_key_split.xml
-->

## Divisão de chave {#key-split}

O número de IDs de rastreamento no conjunto de dados aumenta artificialmente, mas o número total de entradas de log processadas pelo servidor da análise de big data não aumenta artificialmente, preservando assim o número total de eventos contáveis no conjunto de dados. Depois que os dados de um único elemento são divididos, os dados são sempre associados a duas IDs de rastreamento diferentes e não podem ser relacionados.

Por exemplo, se você estiver trabalhando com dados da Web, cada ID de rastreamento representa um visitante único. Se você ativar a divisão de chaves, os visitantes em seu conjunto de dados com grandes quantidades de dados de eventos serão divididos em vários visitantes. Embora o número de visitantes no conjunto de dados seja aumentado artificialmente, o número total de eventos contáveis, como exibições de página ou marcações, não aumenta artificialmente. Após a divisão, os dados dos subvisitantes não podem ser relacionados.

A divisão de chaves usa um algoritmo probabilístico. Como resultado, há uma compensação entre o uso da memória, a probabilidade de falha, o limite de divisão da chave ( [!DNL Split Key Bytes]) e o tamanho do conjunto de dados. Com as configurações recomendadas (conforme listadas abaixo), a taxa de falha é baixa. Dos elementos cujos dados de evento excedem o limite de divisão principal, aproximadamente 1 em 22.000 (normalmente menos de 1 por conjunto de dados) terá alguns de seus dados truncados em vez de divididos.

Os valores recomendados para cada parâmetro (sem e com divisão de chaves) são mostrados na tabela a seguir.

| Parâmetro | Nenhuma divisão de chave | Divisão de chave |
|---|---|---|
| Número Máximo de Bytes de Chave do Grupo | 1e6 | 2e6 |
| Dividir espaço do compartimento de chaves | 6e6 | 6e6 |
| Dividir bytes de chave | 0 | 1e6 |
| Proporção de espaço de chave dividida | 10 | 10 |

[!DNL Group Maximum Key Bytes] especifica a quantidade máxima de dados de evento que podem ser processados para uma única ID de rastreamento. Os dados que excedem esse limite são filtrados do processo de construção do conjunto de dados. [!DNL Split Key Bytes] representa o número de bytes em que uma única ID de rastreamento é dividida em vários elementos. Os elementos são divididos aproximadamente nesse número de bytes de acordo com uma distribuição de probabilidade. [!DNL Split Key Space Ratio] e [!DNL Split Key Bucket Space] controlar a utilização da memória e a taxa de falha da divisão da chave.

>[!NOTE]
>
>[!DNL Group Maximum Key Bytes], [!DNL Split Key Bytes], [!DNL Split Key Space Ratio]e [!DNL Split Key Bucket Space] todos devem ser declarados para que a divisão de chaves funcione corretamente. Não altere os valores desses parâmetros sem consultar a Adobe.

