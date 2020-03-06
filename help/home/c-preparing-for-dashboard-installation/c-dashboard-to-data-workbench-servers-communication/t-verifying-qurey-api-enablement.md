---
description: Cada DPU da qual o painel visualiza dados deve ter uma licença da API de consulta.
solution: Analytics
title: Verificando a Ativação da API de Consulta
topic: Data workbench
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Verificando a Ativação da API de Consulta{#verifying-query-api-enablement}

Cada DPU da qual o painel visualiza dados deve ter uma licença da API de consulta.

Abaixo estão algumas instruções sobre como validar se a API de consulta está instalada e ativada.

1. Localize o certificado do servidor da análise de big data.
1. Abra este certificado em um editor de texto.
1. Verifique se a linha `Product = Query API` existe no certificado.
1. Na **[!UICONTROL Trace]** pasta, abra o arquivo [!DNL InsightServer64.log] em um editor de texto.
1. Nas entradas mais recentes do registro de inicialização, verifique se a linha `Enabling Query API (licensed)` aparece.

* Se a API de consulta não estiver ativada, você verá a entrada `Not enabling Query API (not licensed)`.
* Se você não vir nenhuma entrada de log ou suspeitar que o servidor da análise de big data foi reiniciado desde que a API de consulta foi adicionada, reinicie o servidor da análise de big data e verifique o log.

   Se você não conseguir validar se a API de consulta está ativada, entre em contato com o Adobe ClientCare para obter assistência.
