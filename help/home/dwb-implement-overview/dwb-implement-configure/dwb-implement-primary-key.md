---
description: Esta seção explica como criar chaves primárias (ID de rastreamento) para conjuntos de dados do Análise de big data para o design e implementação do esquema.
title: Processamento de dados - Criação da chave primária
uuid: 7a12950e-6ac0-47d5-b4a8-0b50c48b04fa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Processamento de dados - Criação da chave primária{#data-processing-building-primary-key}

Esta seção explica como criar chaves primárias (ID de rastreamento) para conjuntos de dados do Análise de big data para o design e implementação do esquema.

## Compreensão da ID de rastreamento {#section-24683031044a4af49988655ccb9a45fd}

Após ler e decodificar os dados no DWB (usando decodificadores), a primeira etapa é definir a ID de rastreamento e o carimbo de data e hora. A ID de rastreamento é um identificador que identifica exclusivamente um registro do Cliente. Pode ser qualquer campo no feed, como ID de e-mail, Número de Segurança Social, ID de cookie etc. O campo a ser usado como ID de rastreamento é decidido pelo cliente durante a sessão de descoberta. A ID de rastreamento e o carimbo de data e hora são campos obrigatórios e devem ser definidos para cada registro.

Normalmente, para os Dados online, a ID do cookie (combinação de *x-visid_high* e* x-visid_low*) é usada como o mecanismo padrão para a identificação única do cliente, no entanto, isso pode ser alterado de acordo com o requisito do cliente. A data e a hora em que a solicitação (ou evento) ocorre é o carimbo de data e hora *x*. Todos os registros no DWB são agrupados por *trackingid* e classificados no carimbo de data e hora. O arquivo de campo obrigatório é um arquivo de Inclusão de Conjunto de Dados de Processamento de Log que define os campos obrigatórios: [!DNL Definitions.cfg] *x-trackingid* e *x-timestamp*.

Observação: *x-trackingid *no DWB é um campo incorporado e esse nome não deve ser usado para nenhum outro campo.

**Exemplo 1**: Criar *x-trackingid* usando a ID de cookie (quando somente os dados online são usados)

Para criar o *x-trackingid *no DWB usando a ID de cookie, use a função Hash para criar o *x-trackingid* no [!DNL foundation.cfg] arquivo (é uma prática recomendada definir a ID de rastreamento no [!DNL foundation.cfg] qual, no entanto, ela pode ser definida em qualquer outro arquivo de configuração na [!DNL Dataset > log processing] pasta), como mostrado:

![](assets/dwb_impl_primary_key1.png)

**Exemplo 2**: Criar *x-trackingid* usando a ID de email (quando os dados online e offline estiverem disponíveis)

Supondo que os dados offline e online estejam disponíveis (por exemplo) e a ID de email esteja disponível em ambas as fontes de dados. Como a ID de email identifica exclusivamente um cliente, ela será usada para criar o *x-trackingid*.

Use a função Hash para criar o *trackingId* como mostrado:

![](assets/dwb_impl_primary_key2.png)

