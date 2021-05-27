---
description: A etapa final é executar o painel pela primeira vez para permitir que ele seja inicializado.
title: Inicializar o painel
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
exl-id: 47098d73-d8c4-4d14-964f-108a731d3733
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 4%

---

# Inicializar o painel{#initializing-the-dashboard}

A etapa final é executar o painel pela primeira vez para permitir que ele seja inicializado.

1. Abra um navegador da Web e insira o URL do site recém-implantado (por exemplo, http://localhost/dashboard).
1. A conexão pela primeira vez configurará as tabelas do banco de dados; portanto, você pode experimentar um pequeno atraso.
1. As credenciais de logon inicial são:

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. No primeiro logon, acesse **[!UICONTROL User]** > **[!UICONTROL Account Settings]** e selecione **[!UICONTROL Change Password]** para alterar a senha do administrador.

A instalação do painel está concluída. Caso ainda não o tenha feito, use as instruções detalhadas na seção Preparando a Data Workbench deste guia para configurar sua comunicação com os servidores do Data Workbench e gerenciar usuários e grupos.

>[!NOTE]
>
>O erro do painel e os logs de auditoria podem ser encontrados no diretório [!DNL logs] dentro do caminho de instalação.

>[!NOTE]
>
>Se precisar alterar a identidade do pool de aplicativos para uma conta diferente, certifique-se de conceder acesso ao banco de dados e conceder à identidade acesso de leitura/gravação à pasta [!DNL logs] no caminho de instalação.

>[!NOTE]
>
>Se precisar alterar a string de conexão do banco de dados, basta editar o valor usando o **[!UICONTROL IIS Management Console]**.
