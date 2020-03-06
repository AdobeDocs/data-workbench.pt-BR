---
description: Etapas para instalar os componentes necessários da Microsoft.
solution: Analytics
title: Instalação dos componentes obrigatórios
topic: Data workbench
uuid: e23fba09-4684-4daf-8426-ea91169b3348
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Instalação dos componentes obrigatórios{#installing-required-components}

Etapas para instalar os componentes necessários da Microsoft.

1. Instale o Microsoft .NET Framework v4.0.

   >[!NOTE]
   >
   >Isso deve ser instalado somente após a instalação e configuração da função Web do IIS.

1. Siga o assistente e escolha os padrões quando solicitado para concluir a instalação.
1. Depois de instalado, verifique se o pool de aplicativos ASP.NET v.4.0 foi adicionado na lista **[!UICONTROL Application Pools]** no IIS.
1. Instale o Banco de Dados do Microsoft SQL Server.

   Use qualquer versão do SQL Server 2008 ou 2008 R2 (o Express é compatível) com as Ferramentas de Gerenciamento (a Adobe recomenda o SQL Server 2008 R2 SP1 - Express Edition). 1. Para uma instalação genérica sem instâncias existentes do SQL Server em execução antecipada, selecione a **[!UICONTROL Default Instance]** opção na **[!UICONTROL Instance Configuration]** tela.
1. Para o restante das opções de configuração, siga o assistente e escolha os padrões quando solicitado a concluir a instalação.
1. Instale o Microsoft Web Deploy v2.0.

   Para a maioria das instalações, a **[!UICONTROL Typical]** instalação está boa. No entanto, se você estiver planejando executar implantações remotas, precisará fazer uma instalação completa (escolha **[!UICONTROL Complete]**).

   Depois que todos os pré-requisitos estiverem instalados corretamente, você estará pronto para preparar os servidores da análise de big data para se comunicar com o painel.
