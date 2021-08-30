---
description: Siga estas etapas para iniciar o processo de integração do Adobe Data Workbench (DWB), um componente do Adobe Analytics Premium (AAP).
title: Instruções básicas de integração para serviços gerenciados DWB
uuid: ad44a4eb-00ea-49c7-8401-58976d8fe39e
exl-id: 49fb6afe-b417-4554-9238-fd6381c00029
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 2%

---

# Instruções básicas de integração para serviços gerenciados DWB{#basic-onboarding-instructions-for-dwb-managed-services}

Siga estas etapas para iniciar o processo de integração do Adobe Data Workbench (DWB), um componente do Adobe Analytics Premium (AAP).

Essas instruções de integração são para clientes que implementam o Data Workbench com um único conjunto de relatórios usando serviços gerenciados pelo Adobe sem serviços de consultoria. Se você for um novo cliente AAP implementando o DWB, a equipe de integração do Adobe será o contato inicial. Se estiver atualizando do Adobe Analytics Standard ou de uma versão anterior do DWB, um Gerente de sucesso de cliente do Adobe ajudará você.

## Informações de integração: O que precisamos de você {#section-bdeb9aa26dc14e45a6c90920832becaa}

O Adobe entrará em contato para:

* Identifique um Usuário Principal para DWB para gerar um certificado especificamente para esse usuário no diretório de rede. O usuário principal também atuará como a pessoa principal para interagir com o Atendimento ao cliente do Adobe.
* Identifique o conjunto de relatórios a ser carregado no DWB.

As equipes de marketing digital do Adobe receberão suas informações para criar perfis, definir contas e fornecer um arquivo de configuração para DWB.

**Tarefas de integração do Adobe**

* O Atendimento ao cliente do Adobe cria uma conta licenciada do DWB. O Atendimento ao cliente do Adobe gera um certificado DWB para o usuário principal.
* O Atendimento ao cliente do Adobe define o usuário principal como um &quot;usuário suportado&quot;, a pessoa identificada para as chamadas suportadas e a resolução de problemas.
* O Atendimento ao cliente do Adobe carrega o pacote de software para o portal de software e licença DWB (perfil SoftDocs/Software and Docs) a ser baixado para sua organização.
* A equipe TechOps da Adobe prepara os ambientes de produção e desenvolvimento e seus perfis (por contrato) para o DWB.
* A equipe TechOps do Adobe configura feeds de dados e scripts de gerenciamento de perfis.
* A equipe TechOps do Adobe cria e envia o arquivo de configuração do DWB (Insight.cfg) para a equipe de integração do Adobe responsável pelas tarefas de integração associadas à sua organização.

Depois de personalizar seus feeds de dados e gerar credenciais, certificados e uma configuração de perfil, o Atendimento ao cliente do Adobe enviará seu arquivo de configuração e credenciais para a próxima etapa.

## Acessar seus arquivos de instalação personalizados {#section-26962bf57fef435dbd1c5486d4b6f688}

Você receberá esses arquivos de configuração do Atendimento ao cliente do Adobe para instalar a estação de trabalho DWB no computador cliente.

* Seu arquivo de configuração DWB personalizado (Insight.cfg)

   Esse arquivo de configuração no computador cliente incluirá conexões com os servidores DWB gerenciados.

* Credenciais de logon do Portal de Licenciamento para baixar o Assistente de Configuração DWB e o certificado necessário (arquivo .pem) com o nome do usuário principal.

**Baixar arquivos de configuração adicionais**

1. Navegue até: license.visualsciences.com para baixar o certificado de licença e o executável DWB Setup Wizard.
1. Insira sua Organização (Nome da conta), o nome do usuário principal e a Senha recebida do Atendimento ao cliente do Adobe e clique em login.

   >[!NOTE]
   >
   >O navegador pode solicitar que você apresente um certificado digital neste momento. Se isso acontecer, clique em Cancelar para fechar a caixa de diálogo.

1. Localize o certificado emitido para a sua instância de Data Workbench do Adobe (`<PrimaryUser>`.pem) na seção Downloads e baixe.
1. Localize o Instalador padrão do cliente na seção Downloads para baixar o Assistente de configuração do DWB (arquivo InsightSetup-x.xx.exe).
1. Depois de receber e baixar arquivos do Adobe Customer Care, execute o Assistente de configuração DWB para instalar o software da estação de trabalho no computador cliente.

>[!NOTE]
O DWB Setup Wizard o guiará pela instalação da estação de trabalho do cliente DWB e ajudará a localizar os arquivos Insight.cfg e `<PrimaryUser>`.pem que serão colocados nas pastas necessárias. O arquivo Insight.cfg reside no arquivo Insight.exe na estação de trabalho do cliente instalada. O arquivo `<PrimaryUser>`.pem reside na pasta Certificados com o arquivo trust_ca_cert.pem. Todos os arquivos de certificado e configuração devem estar presentes para que o DWB funcione.

Para obter mais informações, consulte o [Assistente de configuração do DWB](https://experienceleague.adobe.com/docs/data-workbench/using/install/workstation-setup/install-setup.html).

## Conexão com seus servidores DWB {#section-8e79c4e07c2a4342a5bb8af6ee7be3c9}

Seus servidores gerenciados são identificados no arquivo Insight.cfg que você recebe do Atendimento ao cliente do Adobe e reside na estação de trabalho do cliente. A TechOps do Adobe irá configurar seus servidores e o Atendimento ao cliente do Adobe adicionará referências a esses servidores gerenciados e perfis ao arquivo Insight.cfg antes de enviá-lo para você. (A etapa 12 da documentação do Assistente de configuração do DWB Configurar conexões com o servidor será concluída.)

>[!NOTE]
Na área de trabalho Configuração da estação de trabalho na estação de trabalho do cliente DWB, você poderá ver seus servidores e perfis conectados.

**Serviços gerenciados da Adobe**

・ O Adobe TechOps gerencia a infraestrutura, incluindo rede, data center, servidores e armazenamento. O monitoramento da infraestrutura e a resposta a alertas ocorrem 24 horas por dia, 7 dias por semana, para alertas que exigem ação TechOps. Para outros alertas, a TechOps notificará o Atendimento ao cliente do Adobe para coordenar com você.

・ A Adobe TechOps executará atualizações de manutenção e firmware para seus servidores gerenciados. Para manutenção que causa tempo de inatividade, você receberá notificações da janela de manutenção do Atendimento ao cliente com pelo menos duas semanas de antecedência. A TechOps do Adobe atenderá às necessidades imediatas o mais rápido possível. A notificação dependerá da urgência e será resolvida assim que o agendamento for conhecido.

・ O Adobe TechOps configura uma tarefa agendada para gerenciar automaticamente os dados. Os dados do feed analítico são movidos para o DWB para processamento e transformação todas as noites, começando às 21:00, hora do conjunto de relatórios.

・ A TechOps do Adobe processará outros serviços gerenciados da Adobe, como backups de dados, contas FTP, arquivamento de dados e transferência de dados, quando necessário.

・ A Adobe TechOps configurará o cluster de produção principal para conter três meses de dados em andamento para serem redefinidos e reprocessados mensalmente. Atualizações em pesquisas (Geografia, DeviceAtlas, Classificações padrão) também ocorrerão como parte da tarefa de reprocessamento. Por padrão, a tarefa é executada na primeira sexta-feira de cada mês. Se necessário, o cronograma pode ser modificado pelo Atendimento ao cliente.

Para obter mais informações, entre em contato com o [Atendimento ao cliente do Adobe](https://helpx.adobe.com/support/programs/enterprise-support-terms.html).
