---
description: Links para informações adicionais sobre parâmetros específicos no arquivo Log Processing.cfg .
title: Parâmetros de processamento de log
uuid: 97b25665-f588-4f44-8f71-2382600d1b6f
exl-id: f373e954-6827-4afa-9557-73e0a884a602
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 2%

---

# Parâmetros de processamento de log{#log-processing-parameters}

Links para informações adicionais sobre parâmetros específicos no arquivo Log Processing.cfg .

<!--
c_data_filters.xml
-->

## Filtros de dados {#data-filters}

Os filtros definidos no arquivo [!DNL Log Processing.cfg] incluem o seguinte:

* Hora de Término
* Limite de hash
* Hora inicial

A filtragem definida por esses parâmetros ocorre após as entradas de log deixarem os decodificadores e depois das transformações, mas antes de sua avaliação pelo [!DNL Log Entry Condition]. Em geral, alterar qualquer um desses parâmetros resulta em alterações na composição do conjunto de dados.

A técnica recomendada para usar fontes de dados [!DNL Sensor] para criar um conjunto de dados que cubra um período específico é usar os parâmetros Hora inicial e Hora final para o conjunto de dados.

O uso dos parâmetros Hora de início e Hora de término é preferível a outras técnicas, como mover arquivos de log para separá-los por diretório. Ao definir as horas de início e término do conjunto de dados, o servidor do Data Workbench usa automaticamente apenas as entradas de log que ocorreram dentro de um determinado intervalo. Supondo que a Hora final esteja no passado, o servidor do Data Workbench normalmente atualiza o conjunto de dados usando o mesmo conjunto de entradas de log, mesmo se o conjunto de dados for atualizado, por exemplo, adicionando uma nova transformação.

<!--
c_log_entry_con.xml
-->

## Entrada de log

Em essência, é um processo de filtragem nas entradas de log disponíveis. Se [!DNL Log Entry Condition] retornar um valor de false, a entrada do log será filtrada do conjunto disponível de entradas de log.

O [!DNL Log Entry Condition] é descrito por meio do uso de operações de condição (consulte [Condições](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) e pode usar qualquer um dos campos de entrada coletados por [!DNL Sensor] (consulte o *Guia [!DNL Sensor]* ) ou quaisquer campos estendidos produzidos por transformações contidas no arquivo [!DNL Log Processing.cfg] para definir as condições de teste. [!DNL Log Entry] as condições são aplicadas durante o processamento do log e, opcionalmente, podem ser aplicadas durante a transformação.

Este exemplo demonstra o uso do [!DNL log entry condition] para dados do site. Você pode usar o [!DNL Log Entry Condition] para criar conjuntos de dados que se concentram em uma porção específica do site ou visitantes que executam alguma ação específica no site.

O [!DNL Log Entry Condition] neste exemplo cria um conjunto de dados que inclui apenas as entradas de log que fazem parte do armazenamento do site. Ao usar [!DNL RECondition test] com o padrão correspondente [!DNL "/store/.*"] e o campo [!DNL cs-uri-stem] como entrada para a expressão regular, somente as páginas da Web que começam com a string [!DNL "/store/"] são incluídas no conjunto de dados.

![](assets/cfg_LogProcessing_LogEntryCondition.png)

<!--
c_key_split.xml
-->

## Divisão de chave {#key-split}

O número de IDs de rastreamento no conjunto de dados aumenta artificialmente, mas o número total de entradas de log processadas pelo servidor do Data Workbench não aumenta artificialmente, preservando o número total de eventos contáveis no conjunto de dados. Após a divisão dos dados de um único elemento, os dados são associados para sempre a duas IDs de rastreamento diferentes e não podem ser relacionados.

Por exemplo, se você estiver trabalhando com dados da Web, cada ID de rastreamento representa um visitante exclusivo. Se você ativar a divisão de chaves, os visitantes em seu conjunto de dados com grandes quantidades de dados do evento serão divididos em vários visitantes. Embora o número de visitantes no conjunto de dados seja aumentado artificialmente, o número total de eventos contáveis, como exibições de página ou reservas, não aumenta artificialmente. Após a divisão, os dados dos subvisitantes não poderão ser relacionados.

A divisão de chave usa um algoritmo probabilístico. Como resultado, há uma compensação entre o uso da memória, a probabilidade de falha, o limite de divisão de chave ( [!DNL Split Key Bytes]) e o tamanho do conjunto de dados. Com as configurações recomendadas (conforme listadas abaixo), a taxa de falha é baixa. Dos elementos cujos dados de evento excedem o limite de divisão de chave, aproximadamente 1 em 22.000 (geralmente menos de 1 por conjunto de dados) terão alguns de seus dados truncados em vez de divididos.

Os valores recomendados para cada parâmetro (sem e com divisão de chave) são mostrados na tabela a seguir.

| Parâmetro | Sem divisão de chave | Divisão de chave |
|---|---|---|
| Bytes de Chave Máximos do Grupo | 1e6 | 2e6 |
| Dividir espaço do bucket da chave | 6e6 | 6e6 |
| Dividir Bytes de Chave | 0 | 1e6 |
| Proporção de espaço da chave dividida | 10 | 10º |

[!DNL Group Maximum Key Bytes] especifica a quantidade máxima de dados de evento que podem ser processados para uma única ID de rastreamento. Os dados que excedem esse limite são filtrados do processo de construção do conjunto de dados. [!DNL Split Key Bytes] representa o número de bytes em que uma única ID de rastreamento é dividida em vários elementos. Os elementos são divididos aproximadamente nesse número de bytes de acordo com uma distribuição de probabilidade. [!DNL Split Key Space Ratio] e  [!DNL Split Key Bucket Space] controlar a utilização da memória e a taxa de falha da divisão de chaves.

>[!NOTE]
>
>[!DNL Group Maximum Key Bytes],  [!DNL Split Key Bytes],  [!DNL Split Key Space Ratio], e  [!DNL Split Key Bucket Space] todos devem ser declarados para que a divisão de chave funcione corretamente. Não altere os valores desses parâmetros sem consultar o Adobe.
