---
description: Um conjunto de dados da Adobe contém os dados que foram carregados e processados pelo servidor da análise de big data.
solution: Analytics
title: Como entender a construção de conjuntos de dados
topic: Data workbench
uuid: 540d159d-3f72-49dd-9929-107f1fc62b2b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Como entender a construção de conjuntos de dados{#understanding-dataset-construction}

Um conjunto de dados da Adobe contém os dados que foram carregados e processados pelo servidor da análise de big data.

As etapas envolvidas no carregamento e no processamento dos dados pelo servidor da análise de big data (InsightServer64.exe) compõem o processo de construção do conjunto de dados.

>[!NOTE]
>
>Um servidor de análise de big data que processa e fornece dados de um conjunto de dados da Adobe é chamado de unidade de processamento de dados ou DPU. Às vezes, é chamado de servidor de processamento ou de consulta. A análise de big data e [!DNL Report] os clientes interagem diretamente com as DPUs.

Durante a construção do conjunto de dados, o servidor da análise de big data lê dados de origem de fontes de log, aplica transformações a campos de dados específicos e define dimensões estendidas a serem criadas a partir dos campos transformados. O processo de construção ocorre em duas fases: Processamento *e* transformação ** do log. Após a construção do conjunto de dados, é possível usar as dimensões estendidas do conjunto de dados para criar métricas e dimensões derivadas para fins de análise específicos.

A construção do conjunto de dados é como um processo de fabricação. Você seleciona os dados (as matérias-primas) a serem usados para criar o conjunto de dados e define as transformações de dados (as etapas do processo) que manipulam as informações disponíveis nos dados para criar dimensões estendidas (os produtos fabricados).

<!--
c_log_proc.xml
-->

Os registros são filtrados e os campos de dados que devem ser passados para a fase de transformação são identificados. No final da fase de processamento do log, os dados são agrupados pela ID de rastreamento (ou seja, todas as entradas de log com a mesma ID de rastreamento são agrupadas juntas) e solicitados no tempo. Durante a fase de processamento de log, não é possível acessar os dados processados para uso na análise.

## Especificação de Fontes de Log {#section-75279dd6a7304d469735562796741d0f}

As fontes de log são arquivos que contêm os dados a serem usados para criar um conjunto de dados. Os dados disponíveis nas fontes de log são chamados de dados de evento porque cada registro de dados representa um registro de transação ou uma única instância de um evento. Além disso, cada registro ou entrada de registro contém um valor chamado de ID de rastreamento.

>[!NOTE]
>
>Ao selecionar fontes de log, verifique se cada entrada de log contém uma ID de rastreamento para a entidade que deve representar o nível mais alto no qual seus dados devem ser agrupados. Por exemplo, se você estiver trabalhando com dados coletados do tráfego do site, é provável que você escolha o visitante para ser essa entidade. Cada visitante tem uma ID de rastreamento exclusiva, e todos os dados sobre um visitante do site específico podem ser agrupados. Para obter ajuda, entre em contato com a Adobe.

Os dados de eventos de fontes de log são coletados em tempo real por fontes de dados arquivadas [!DNL Sensors] ou extraídos por meio do Insight Server. Os dados de eventos coletados pelos Sensores de HTTP e servidores de aplicativos são transmitidos para os Servidores Insight, que convertem os dados em arquivos de log ( [!DNL .vsl]) altamente compactados. Os dados de evento que residem em um arquivo simples, um arquivo XML ou uma fonte de dados ODBC são lidos pelo Insight Server, que fornece decodificadores que você define para extrair um conjunto comum de campos de log desses diferentes formatos.

## Definindo transformações {#section-55a8cdb47379484081e53087f074778d}

Uma transformação é um conjunto de instruções que você pode definir para extrair ou manipular informações nos dados do evento. Cada transformação definida é aplicada a cada registro de dados de evento (entrada de registro) para atualizar campos de log existentes ou produzir novos campos. Os resultados das transformações são usados juntamente com as condições de entrada do log para avaliar quais entradas de log são filtradas do conjunto de dados durante o processamento do log.

Nem todos os tipos de transformações podem ser usados durante a fase de processamento de log do processo de construção do conjunto de dados.

## Filtrar registros {#section-6172ca0fb0eb4177925151bb49fdbc02}

O conjunto de dados contém vários parâmetros usados para filtrar o fluxo de dados para fora das transformações. A filtragem é usada para especificar quais entradas de log são usadas em etapas de processamento subsequentes. Por exemplo, os filtros podem ser definidos por, intervalo de tempo, status da resposta do servidor ou endereço IP e informações agente-usuário. O [!DNL Log Entry Condition] é um teste de filtragem personalizável. O teste procura determinadas condições nos campos de cada entrada de log para determinar se essa entrada deve continuar no processo de construção do conjunto de dados. Se uma entrada de log não atender à condição, ela será removida do processo de construção.

## Identificação de campos para transformação {#section-eef98ca723e54547b887aefdf0514c47}

Se um campo de dados for passado da fase de processamento de log para a fase de transformação para processamento adicional, você deverá identificá-lo durante o processamento de log. Esse requisito se aplica independentemente de o campo estar disponível nas fontes de log ou criado a partir das transformações de dados aplicadas aos dados durante o processamento de log.

<!--
c_transformation.xml
-->

Durante a fase de transformação da construção do conjunto de dados, o processamento ocorre nos dados agrupados e pedidos que são gerados pelo processamento de log. Transformações de dados adicionais são executadas e dimensões de dados estendidas são criadas para uso em suas análises. Durante a fase de transformação, você pode acessar uma amostra estatística dos dados que ficam maiores à medida que a fase de transformação se aproxima da conclusão.

## Definindo transformações {#section-001b3fd4c1dd4dd38a5536872bc9de68}

É possível definir transformações a serem usadas durante a fase de transformação do processo de construção do conjunto de dados para facilitar a criação das dimensões estendidas. Cada transformação é aplicada a cada registro de dados de evento (entrada de registro) passado do processamento de log.

## Filtrar registros {#section-3fed0a00ca344a719b5e8db363f64f06}

O aplicativo [!DNL Log Entry Condition] pode ser aplicado durante a transformação para procurar condições específicas nos campos de cada entrada de log proveniente do processamento de log. Se uma entrada de log não atender à condição, ela será removida do processo de construção.

## Definindo Dimensões Estendidas {#section-25efafd0bfc84c86b9717d453a88c91b}

Dimensões estendidas são os produtos finais do processo de construção do conjunto de dados. Eles representam relações entre os campos de log nos dados. Use-os para criar visualizações, criar métricas estendidas ou executar análises para entender as operações e problemas específicos de sua empresa.
