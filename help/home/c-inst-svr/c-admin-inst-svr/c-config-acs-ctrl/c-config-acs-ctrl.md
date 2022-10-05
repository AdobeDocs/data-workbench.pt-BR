---
description: O arquivo de configuração Controle de acesso, Access Control.cfg, define os grupos de controle de acesso pelos quais o Insight Server concede permissões a arquivos com base nos atributos (OU, CN, e assim por diante) do certificado da conexão de entrada.
title: Configurar o controle de acesso
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
exl-id: 2836c907-fc74-4d35-badc-b8f06cd6989f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---

# Configurar o controle de acesso{#configuring-access-control}

{{eol}}

O arquivo de configuração Controle de acesso, Access Control.cfg, define os grupos de controle de acesso pelos quais o Insight Server concede permissões a arquivos com base nos atributos (OU, CN, e assim por diante) do certificado da conexão de entrada.

**Frequência recomendada:** Conforme necessário

[!DNL Insight Server] fornece grupos de controle de acesso configuráveis para gerenciar a segurança de conexões com o [!DNL Insight Server]. Os grupos de controle de acesso identificam usuários que podem executar funções administrativas por meio de [!DNL Insight].

Se você precisar fornecer acesso a novos usuários ou máquinas, como ao adicionar uma máquina a um [!DNL Insight Server] , basta editar o arquivo de configuração Controle de Acesso .
