---
description: Um guia rápido para as etapas mínimas necessárias para validar e configurar feeds de dados históricos.
title: Validação de feeds de dados históricos
uuid: 83d2d48b-0966-4f4e-9c9c-60473c4546b2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Validação de feeds de dados históricos{#validating-historical-data-feeds}

Um guia rápido para as etapas mínimas necessárias para validar e configurar feeds de dados históricos.

## Etapas de validação para consistência dos feeds de dados {#section-777b2c627a354627a02feb9461e23038}

1. Faça logon nos *dentes* (https://oasis.omniture.com/drteeth/)
1. Ir para o Administrador do SiteCatalyst -> Definição do Feed de Dados (novo)
1. Ir para o local do servidor (ex. Dallas, Londres...) Dependendo de onde sua organização esteja localizada.
1. Forneça RSID e selecione o tipo de feed Insight e clique em *pesquisa*.

   ![](assets/dwb_impl_historical.png)

1. Identifique o nome real do feed para o seu cliente.
1. Clique em Histórico na seção Ações. ![](assets/dwb_impl_historical1.png)

   Verifique se há erros no campo de status e, se algum feed estiver em estado de erro, selecione o feed e clique em reprocessar. Se o erro ocorreu em várias solicitações, envie um email para *`dataworkbench@adobe.com`* com a ID do feed e os detalhes do Conjunto de relatórios para reprocessar.

1. A pós-validação verifica os logs na pasta bruta do local NAS.

