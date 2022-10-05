---
description: Um guia rápido para as etapas mínimas necessárias para validar e configurar feeds de dados históricos.
title: Validação de feeds de dados históricos
uuid: 83d2d48b-0966-4f4e-9c9c-60473c4546b2
exl-id: 5a5e2cca-2fab-48a0-b58d-a8c46114b9a0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 5%

---

# Validação de feeds de dados históricos{#validating-historical-data-feeds}

{{eol}}

Um guia rápido para as etapas mínimas necessárias para validar e configurar feeds de dados históricos.

## Etapas de validação para garantir a consistência dos feeds de dados {#section-777b2c627a354627a02feb9461e23038}

1. Faça logon em *dente* (https://oasis.omniture.com/drteeth/)
1. Vá para SiteCatalyst Admin -> Definição do feed de dados (novo)
1. Ir para a localização do servidor (Ex. Dallas, Londres...) Dependendo de onde sua organização está localizada.
1. Forneça RSID e selecione o tipo de feed Insight e clique em *pesquisa*.

   ![](assets/dwb_impl_historical.png)

1. Identifique o nome real do feed para o cliente.
1. Clique em Histórico na seção Ações . ![](assets/dwb_impl_historical1.png)

   Verifique se há erros no campo de status e, caso algum feed esteja em estado de erro, selecione o feed e clique em reprocessar. Se o erro ocorreu para várias solicitações, envie um email para *`dataworkbench@adobe.com`* com a ID do feed e os detalhes do Conjunto de relatórios para reprocessar.

1. A pós-validação verifica os logs na pasta bruta do local NAS.
