---
description: O arquivo de configuração de Controle de Acesso, Access Control.cfg, define os grupos de controle de acesso pelos quais o Insight Server concede permissões a arquivos com base nos atributos (OU, CN, e assim por diante) do certificado da conexão de entrada.
solution: Insight
title: Configurando o controle de acesso
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurando o controle de acesso{#configuring-access-control}

O arquivo de configuração de Controle de Acesso, Access Control.cfg, define os grupos de controle de acesso pelos quais o Insight Server concede permissões a arquivos com base nos atributos (OU, CN, e assim por diante) do certificado da conexão de entrada.

**Frequência recomendada:** Conforme necessário

[!DNL Insight Server] fornece grupos de controle de acesso configuráveis para gerenciar a segurança das conexões com [!DNL Insight Server]. Os grupos de controle de acesso identificam os usuários com permissão para realizar funções administrativas por meio [!DNL Insight].

Se precisar fornecer acesso a novos usuários ou máquinas, como ao adicionar uma máquina a um [!DNL Insight Server] cluster, basta editar o arquivo de configuração Controle de acesso.
