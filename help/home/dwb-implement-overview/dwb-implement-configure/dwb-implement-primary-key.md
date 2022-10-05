---
description: Esta seção explica como criar chaves primárias (ID de rastreamento) para conjuntos de dados do Data Workbench para design e implementação do esquema.
title: Processamento de dados - Criação da chave primária
uuid: 7a12950e-6ac0-47d5-b4a8-0b50c48b04fa
exl-id: 9937038f-d011-4946-8a5b-cc724b611ae5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 2%

---

# Processamento de dados - Criação da chave primária{#data-processing-building-primary-key}

{{eol}}

Esta seção explica como criar chaves primárias (ID de rastreamento) para conjuntos de dados do Data Workbench para design e implementação do esquema.

## Como entender a ID de rastreamento {#section-24683031044a4af49988655ccb9a45fd}

Após ler e decodificar os dados no DWB (usando decodificadores), a primeira etapa é definir a ID de rastreamento e o carimbo de data e hora. A ID de rastreamento é um identificador que identifica exclusivamente um registro do cliente. Pode ser qualquer campo no feed, como ID de email, Número do seguro social, ID de cookie etc. O campo a ser usado como ID de rastreamento é decidido pelo cliente durante a sessão de descoberta. ID de rastreamento e carimbo de data e hora são campos obrigatórios e devem ser definidos para cada registro.

Normalmente, para dados online, ID do cookie (combinação de *x-visid_high* e* x-visid_low*) é usado como o mecanismo padrão para a identificação exclusiva do cliente, no entanto, isso pode ser alterado de acordo com o requisito do cliente. A data e a hora em que a solicitação (ou evento) ocorre é a *x-timestamp*. Todos os registros no DWB são agrupados por *trackingid* e classificadas no carimbo de data e hora. O campo obrigatório [!DNL Definitions.cfg] Arquivo é um arquivo de Inclusão do conjunto de dados de processamento de log que define os campos obrigatórios : *x-trackingid* e *x-timestamp*.

Observação: *x-trackingid *no DWB é um campo integrado e esse nome não deve ser usado para nenhum outro campo.

**Exemplo 1**: Criação *x-trackingid* usar a ID de cookie (quando somente os dados online são usados)

Para criar o *x-trackingid *no DWB usando a ID do cookie, use a função Hash para criar o *x-trackingid* no [!DNL foundation.cfg] (é uma prática recomendada definir a ID de rastreamento em [!DNL foundation.cfg] mas pode ser definido em qualquer outro arquivo de configuração em [!DNL Dataset > log processing] pasta) conforme mostrado:

![](assets/dwb_impl_primary_key1.png)

**Exemplo 2**: Criação *x-trackingid* usar a ID de email (quando dados online e offline estiverem disponíveis)

Supondo que os dados offline e online estejam disponíveis (para este exemplo) e a ID de email esteja disponível em ambas as fontes de dados. Como a ID de email identifica exclusivamente um cliente, ela será usada para criar o *x-trackingid*.

Use a função Hash para criar a variável *trackingId* como mostrado:

![](assets/dwb_impl_primary_key2.png)
