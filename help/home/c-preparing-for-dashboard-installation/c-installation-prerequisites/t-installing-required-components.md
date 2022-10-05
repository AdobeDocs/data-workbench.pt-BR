---
description: Etapas para instalar os componentes Microsoft necessários.
title: Instalar componentes obrigatórios
uuid: e23fba09-4684-4daf-8426-ea91169b3348
exl-id: d39cb14e-7cce-4088-8301-8ff566c0bde4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 3%

---

# Instalar componentes obrigatórios{#installing-required-components}

{{eol}}

Etapas para instalar os componentes Microsoft necessários.

1. Instale o Microsoft .NET Framework v4.0.

   >[!NOTE]
   >
   >Isso deve ser instalado somente após instalar e configurar a Função Web do IIS.

1. Siga o assistente e escolha padrões, onde solicitado, para concluir a instalação.
1. Depois de instalado, verifique se o pool de aplicativos ASP.NET v.4.0 foi adicionado dentro do **[!UICONTROL Application Pools]** listar no IIS.
1. Instale o Banco de Dados do Microsoft SQL Server.

   Use qualquer versão do SQL Server 2008 ou 2008 R2 (o Express é compatível) com as Ferramentas de Gerenciamento (o Adobe recomenda o SQL Server 2008 R2 SP1 - Express Edition). 1. Para uma instalação genérica sem instâncias existentes do SQL Server em execução antecipada, selecione o **[!UICONTROL Default Instance]** na **[!UICONTROL Instance Configuration]** tela.
1. Para o restante das opções de configuração, siga o assistente e escolha padrões quando solicitado a concluir a instalação.
1. Instale o Microsoft Web Deploy v2.0.

   Para a maioria das instalações, a variável **[!UICONTROL Typical]** a instalação está boa. No entanto, se você estiver planejando executar implantações remotas, será necessário fazer uma instalação completa (escolha **[!UICONTROL Complete]**).

   Depois que todos os pré-requisitos forem instalados corretamente, você estará pronto para preparar os servidores do Data Workbench para se comunicar com o painel.
