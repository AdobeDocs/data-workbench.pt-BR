---
description: Os usuários devem ter uma conta válida e fornecer um nome de conta e senha quando acessarem o Portal de relatórios.
solution: Analytics
title: Definir Contas Adicionais
topic: Data workbench
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definir Contas Adicionais{#define-additional-accounts}

Os usuários devem ter uma conta válida e fornecer um nome de conta e senha quando acessarem o Portal de relatórios.

Por padrão, a autenticação do usuário está ativada em [!DNL Report Portal].

A lista de contas válidas para [!DNL Report Portal] é mantida no arquivo de banco de dados, [!DNL portal.mdb]. [!DNL Report Portal] é instalado com uma conta com privilégios administrativos:

* Nome da conta: teste
* Senha: user

>[!NOTE]
>
>Por motivos de segurança, a Adobe recomenda que você altere a senha desta conta depois de instalá-la [!DNL Report Portal].

Para adicionar contas de usuário [!DNL Report Portal] ou alterar informações relacionadas a contas existentes, use a guia [!DNL Admin] na interface do [!DNL Report Portal] usuário.

Cada vez que você adiciona uma nova conta ou edita uma conta existente, um email de confirmação é enviado conforme especificado no [!DNL email.asp] arquivo na pasta \*PortalName*\PortalASP. Para obter mais informações, consulte [Editar o arquivo](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b)Email.asp.

Para obter etapas para adicionar usuários adicionais, consulte [Trabalhar com contas](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d).

>[!NOTE]
>
>Como opção, você pode desativar a autenticação do usuário e permitir o acesso anônimo ao [!DNL Report Portal]. Para obter as etapas para fazer isso, consulte as informações sobre o parâmetro Session(&quot;In&quot;) em [Editar o arquivo](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)de configuração da sessão.

