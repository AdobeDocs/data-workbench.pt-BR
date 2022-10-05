---
description: Cinco grupos de controle de acesso pré-criados estão disponíveis, mas você pode criar e gerenciar grupos adicionais, conforme necessário.
title: Compreender grupos de controle de acesso
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
exl-id: 35353b0a-7f08-4215-8a2c-ee1e26d9f5db
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 8%

---

# Compreender grupos de controle de acesso{#understanding-access-control-groups}

{{eol}}

Cinco grupos de controle de acesso pré-criados estão disponíveis, mas você pode criar e gerenciar grupos adicionais, conforme necessário.

Você pode definir os membros de cada grupo de controle de acesso, bem como os diretórios aos quais cada grupo tem acesso de Leitura ou Leitura/Gravação.

Os grupos predefinidos são definidos da seguinte forma:

| Grupo | Descrição |
|---|---|
| Administradores | Permite o acesso a todos os diretórios e arquivos. O endereço IP padrão é 127.0.0.1 (host local). |
| Sensores | Permite acesso somente aos arquivos usados por [!DNL Sensor] transmitir dados. |
| Usuários | Permite acesso somente leitura aos elementos necessários para um [!DNL Insight] para executar tarefas básicas de análise. |
| Usuários avançados | Permite acesso somente leitura aos elementos necessários para um [!DNL Insight] usuário para executar tarefas básicas de análise, além de acesso de leitura e gravação ao [!DNL Profiles] pasta para modificar perfis. |
| Servidores de Cluster | Permite o acesso a [!DNL Insight Servers] que são designados como servidores de cluster. |
| Servidores de relatórios | Permite o acesso a [!DNL Report] máquinas que se conectam ao [!DNL Insight Server]. |

Os membros de um grupo de controle de acesso são definidos usando seus endereços IP ou informações de certificado SSL.

Se um certificado SSL não estiver disponível, um endereço IP pode ser usado para definir um membro do grupo. A instalação típica de [!DNL Insight] inclui um certificado SSL, enquanto o uso de certificados para [!DNL Sensor(s)] é opcional. Para [!DNL Insight Server], os Servidores de Cluster são definidos usando endereços IP em vez de certificados SSL.

Os seguintes códigos podem ser usados para definir membros do grupo:

| Código de tipos de acesso | Definição |
|---|---|
| Op. | Organização |
| NC | Nome comum |
| L | Localidade |
| ST | Estado ou província |
| C | País |
| OU | Unidade organizacional |
| Email | Endereço de email |
