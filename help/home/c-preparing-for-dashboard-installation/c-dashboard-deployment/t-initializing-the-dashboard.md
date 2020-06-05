---
description: A etapa final é executar o painel pela primeira vez para permitir que ele seja inicializado.
solution: Analytics
title: Inicializando o Painel
topic: Data workbench
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
translation-type: tm+mt
source-git-commit: 4b39a42285c39e26f097b91309c269c05a9475bd
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 1%

---


# Inicializando o Painel{#initializing-the-dashboard}

A etapa final é executar o painel pela primeira vez para permitir que ele seja inicializado.

1. Abra um navegador da Web e insira o URL para o site recém-implantado (por exemplo, http://localhost/dashboard).
1. A conexão pela primeira vez configurará as tabelas do banco de dados, de modo que você pode experimentar um pequeno atraso.
1. As credenciais de logon inicial são:

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. No primeiro logon, vá para **[!UICONTROL User]** > **[!UICONTROL Account Settings]** e selecione **[!UICONTROL Change Password]** para alterar a senha do administrador.

A instalação do painel está concluída. Caso ainda não o tenha feito, use as instruções detalhadas na seção Preparação da análise de big data deste guia para configurar sua comunicação com os servidores da análise de big data e gerenciar usuários e grupos.

>[!NOTE]
>
>É possível localizar erros de Painel e registros de auditoria no [!DNL logs] diretório dentro do caminho de instalação.

>[!NOTE]
>
>Se precisar alterar a identidade do pool de aplicativos para outra conta, certifique-se de conceder acesso ao banco de dados e conceder acesso de leitura/gravação à identidade para a [!DNL logs] pasta no caminho de instalação.

>[!NOTE]
>
>Se você precisar alterar a string de conexão do banco de dados, basta editar o valor usando o **[!UICONTROL IIS Management Console]**.
