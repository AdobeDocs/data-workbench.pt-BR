---
description: Os usuários devem ter uma conta válida e fornecer um nome de conta e senha quando acessarem o portal de relatórios.
title: Definir contas adicionais
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
exl-id: 1f267217-a389-431a-ba49-9a9eead0ae83
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%

---

# Definir contas adicionais

Os usuários devem ter uma conta válida e fornecer um nome de conta e senha quando acessarem o portal de relatórios.

Por padrão, a autenticação de usuário é ativada em [!DNL Report Portal].

A lista de contas válidas para [!DNL Report Portal] é mantida no arquivo de banco de dados, [!DNL portal.mdb]. [!DNL Report Portal] é instalado com uma conta com privilégios administrativos:

* Nome da conta: teste
* Senha: usuário

>[!NOTE]
>
>Por motivos de segurança, o Adobe recomenda que você altere a senha dessa conta após instalar [!DNL Report Portal].

Para adicionar contas de usuário a [!DNL Report Portal] ou alterar informações relacionadas a contas existentes, use a guia [!DNL Admin] na interface do usuário [!DNL Report Portal].

Cada vez que você adiciona uma nova conta ou edita uma conta existente, um email de confirmação é enviado conforme especificado no arquivo [!DNL email.asp] na pasta \*PortalName*\PortalASP. Para obter mais informações, consulte [Editar o arquivo Email.asp](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b).

Para obter etapas para adicionar usuários adicionais, consulte [Trabalhar com contas](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d).

>[!NOTE]
>
>Como opção, você pode desativar a autenticação de usuário e permitir acesso anônimo a [!DNL Report Portal]. Para obter etapas para fazer isso, consulte as informações sobre o parâmetro Session(&quot;In&quot;) em [Edit the Session Configuration File](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7).
