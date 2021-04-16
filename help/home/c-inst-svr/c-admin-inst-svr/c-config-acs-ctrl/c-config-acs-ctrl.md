---
description: O arquivo de configuração Controle de acesso, Access Control.cfg, define os grupos de controle de acesso pelos quais o Insight Server concede permissões a arquivos com base nos atributos (OU, CN, e assim por diante) do certificado da conexão de entrada.
title: Configurar o controle de acesso
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
exl-id: 2836c907-fc74-4d35-badc-b8f06cd6989f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---

# Configurar o controle de acesso{#configuring-access-control}

O arquivo de configuração Controle de acesso, Access Control.cfg, define os grupos de controle de acesso pelos quais o Insight Server concede permissões a arquivos com base nos atributos (OU, CN, e assim por diante) do certificado da conexão de entrada.

**Frequência recomendada:** conforme necessário

[!DNL Insight Server] O fornece grupos de controle de acesso configuráveis para gerenciar a segurança das conexões com o  [!DNL Insight Server]. Os grupos de controle de acesso identificam usuários que podem executar funções administrativas por meio de [!DNL Insight].

Se precisar fornecer acesso a novos usuários ou máquinas, como ao adicionar uma máquina a um cluster [!DNL Insight Server], basta editar o arquivo de configuração Controle de Acesso.
