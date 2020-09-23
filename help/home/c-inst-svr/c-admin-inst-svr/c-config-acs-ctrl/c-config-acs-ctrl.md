---
description: O arquivo de configuração do Controle de acesso, Controle de acesso.cfg, define os grupos de controles de acesso pelos quais o Insight Server concede permissões para arquivos com base nos atributos (OU, CN, e assim por diante) do certificado da conexão de entrada.
solution: Analytics
title: Configurar o controle de acesso
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---


# Configurar o controle de acesso{#configuring-access-control}

O arquivo de configuração do Controle de acesso, Controle de acesso.cfg, define os grupos de controles de acesso pelos quais o Insight Server concede permissões para arquivos com base nos atributos (OU, CN, e assim por diante) do certificado da conexão de entrada.

**Frequência recomendada:** Conforme necessário

[!DNL Insight Server] fornece grupos de controles de acesso configuráveis para gerenciar a segurança das conexões com [!DNL Insight Server]. Os grupos de controles de acesso identificam os usuários com permissão para realizar funções administrativas por meio [!DNL Insight].

Se precisar fornecer acesso a novos usuários ou máquinas, como ao adicionar uma máquina a um [!DNL Insight Server] cluster, basta editar o arquivo de configuração do Controle de acesso.
