---
description: Cada DPU da qual o painel deve visualizar dados deve ter uma licença da API de consulta.
title: Verificar a ativação da API de Query
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
exl-id: 3dde2958-0f99-45f8-b65b-207a92362292
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# Verificar a ativação da API de Query{#verifying-query-api-enablement}

{{eol}}

Cada DPU da qual o painel deve visualizar dados deve ter uma licença da API de consulta.

Abaixo estão algumas instruções sobre como validar se a API do Query está instalada e ativada.

1. Encontre o certificado do servidor do Data Workbench.
1. Abra este certificado em um editor de texto.
1. Certifique-se de que a linha `Product = Query API` existe no certificado.
1. No **[!UICONTROL Trace]** , abra o [!DNL InsightServer64.log] em um editor de texto.
1. Nas entradas mais recentes do log de inicialização, verifique se a linha `Enabling Query API (licensed)` é exibido.

* Se a API de consulta não estiver ativada, você verá a entrada `Not enabling Query API (not licensed)`.
* Se você não vir entradas de log ou suspeitar que o servidor do Data Workbench foi reiniciado desde que a API de Query foi adicionada, reinicie o servidor do Data Workbench novamente e verifique o log.

   Se você não conseguir validar se a API do Query está ativada, entre em contato com o Adobe ClientCare para obter assistência.
