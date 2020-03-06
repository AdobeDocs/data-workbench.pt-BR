---
description: Siga estas etapas para iniciar o processo de integração para o Adobe Data Workbench (DWB), um componente do Adobe Analytics Premium (AAP).
title: Instruções básicas de onboard para serviços gerenciados DWB
uuid: ad44a4eb-00ea-49c7-8401-58976d8fe39e
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# Instruções básicas de onboard para serviços gerenciados DWB{#basic-onboarding-instructions-for-dwb-managed-services}

Siga estas etapas para iniciar o processo de integração para o Adobe Data Workbench (DWB), um componente do Adobe Analytics Premium (AAP).

Essas instruções de integração são para clientes que implementam o Análise de big data com um único conjunto de relatórios usando serviços gerenciados da Adobe sem serviços de consultoria. Se você for um novo cliente AAP que implementa o DWB, a equipe de onboard da Adobe será seu contato inicial. Se você estiver atualizando do Adobe Analytics padrão ou de uma versão anterior do DWB, um Gerente de sucesso do cliente da Adobe o ajudará.

## Informações onboard: O que precisamos de você {#section-bdeb9aa26dc14e45a6c90920832becaa}

A Adobe entrará em contato com você para:

* Identifique um usuário primário para DWB para gerar um certificado especificamente para esse usuário no diretório de rede. O usuário principal também atuará como a pessoa principal para interagir com o Atendimento ao cliente da Adobe.
* Identifique o conjunto de relatórios a ser carregado no DWB.

As equipes do Adobe Digital Marketing usarão suas informações para criar perfis, definir contas e fornecer um arquivo de configuração para o DWB.

**Tarefas de integração da Adobe**

* O Atendimento ao cliente da Adobe cria uma conta licenciada do DWB. O Atendimento ao cliente da Adobe gera um certificado DWB para o usuário principal.
* O Atendimento ao cliente da Adobe define o usuário principal como &quot;usuário suportado&quot;, a pessoa identificada para chamadas suportadas e solução de problemas.
* O Atendimento ao cliente da Adobe carrega o pacote de software para o portal de licença e software da DWB (perfil SoftDocs/Software e Docs) a ser baixado para sua organização.
* A equipe TechOps da Adobe prepara os ambientes de produção e desenvolvimento e seus perfis (por contrato) para o DWB.
* A equipe TechOps da Adobe configura feeds de dados e scripts de gerenciamento de perfis.
* A equipe TechOps da Adobe cria e envia o arquivo de configuração DWB (Insight.cfg) para a equipe de Onboard da Adobe responsável pelas tarefas de integração associadas à sua organização.

Depois de personalizar seus feeds de dados e gerar credenciais, certificados e uma configuração de perfil, o Atendimento ao cliente da Adobe enviará seu arquivo de configuração e suas credenciais para a próxima etapa.

## Acesse seus arquivos de instalação personalizados {#section-26962bf57fef435dbd1c5486d4b6f688}

Você receberá esses arquivos de configuração do Atendimento ao cliente da Adobe para instalar a estação de trabalho DWB no computador cliente.

* Seu arquivo de configuração DWB personalizado (Insight.cfg)

   Esse arquivo de configuração no computador cliente incluirá conexões com os servidores DWB gerenciados.

* Credenciais de logon para o Portal de Licenciamento para baixar o Assistente de Instalação do DWB e o certificado necessário (arquivo .pem) com o nome do usuário principal.

**Download de arquivos de configuração adicionais**

1. Navegue até: license.visualsciences.com para baixar seu certificado de licença e o executável do Assistente de configuração DWB.
1. Digite sua organização (nome da conta), o nome do usuário principal e a senha recebida do Atendimento ao cliente da Adobe e clique em logon.

   >[!NOTE]
   >
   >Seu navegador pode solicitar que você apresente um certificado digital neste momento. Se isso acontecer, clique em Cancelar para descartar a caixa de diálogo.

1. Localize o certificado emitido para sua instância do Adobe Data Workbench (`<PrimaryUser>`.pem) na seção Downloads e baixe.
1. Localize o Standard Client Installer na seção Downloads para baixar o Assistente de configuração do DWB (arquivo InsightSetup-x.xx.exe).
1. Depois de receber e baixar arquivos do Atendimento ao cliente da Adobe, execute o Assistente de instalação do DWB para instalar o software da estação de trabalho no computador cliente.

>[!NOTE]
O Assistente de configuração do DWB o guiará pela instalação da estação de trabalho do cliente DWB e ajudará a localizar os arquivos Insight.cfg e `<PrimaryUser>`.pem nas pastas necessárias. O arquivo Insight.cfg reside no arquivo Insight.exe na estação de trabalho do cliente instalada. O arquivo `<PrimaryUser>`.pem reside na pasta Certificados com o arquivo trust_ca_cert.pem. Todos os arquivos de certificado e configuração devem estar presentes para que o DWB funcione.

Para obter informações adicionais, consulte o Assistente [de instalação do](https://docs.adobe.com/content/help/en/data-workbench/using/install/workstation-setup/install-setup.html)DWB.

## Conexão com seus servidores DWB {#section-8e79c4e07c2a4342a5bb8af6ee7be3c9}

Seus servidores gerenciados são identificados no arquivo Insight.cfg que você recebe do Atendimento ao cliente da Adobe e reside na sua estação de trabalho cliente. A TechOps da Adobe configurará seus servidores e o Atendimento ao cliente da Adobe adicionará referências a esses servidores e perfis gerenciados ao arquivo Insight.cfg antes de enviá-lo para você. (A documentação Configurar conexões com o servidor na etapa 12 do Assistente de configuração do DWB será concluída.)

>[!NOTE]
Na área de trabalho Configuração da estação de trabalho na estação de trabalho do cliente DWB, você poderá ver seus servidores e perfis conectados.

**Adobe Managed Services**

・ A TechOps da Adobe gerencia a infraestrutura, incluindo rede, data center, servidores e armazenamento. O monitoramento da infraestrutura e a resposta a alertas ocorrem 24 horas por dia, 7 dias por semana, para alertas que exigem ação TechOps. Para outros alertas, o TechOps notificará o Atendimento ao cliente da Adobe para coordenar com você.

・ A TechOps da Adobe executará atualizações de manutenção e firmware para seus servidores gerenciados. Para manutenção que gera tempo de inatividade, você receberá notificações da janela de manutenção do Atendimento ao cliente com pelo menos duas semanas de antecedência. A TechOps da Adobe atenderá às necessidades imediatas o mais rápido possível. A notificação dependerá da urgência e será resolvida assim que o agendamento for conhecido.

・ A TechOps da Adobe configura uma tarefa agendada para gerenciar dados automaticamente. Os dados de feed analíticos são movidos para o DWB para processamento e transformação todas as noites, começando às 21:00 horas, hora do conjunto de relatórios.

・ A TechOps da Adobe processará outros Serviços gerenciados da Adobe que incluem backups de dados, contas FTP, arquivamento de dados e transferência de dados, quando necessário.

・ A TechOps da Adobe configurará o cluster de produção principal para conter três meses de dados acumulados a serem redefinidos e reprocessados mensalmente. Atualizações em pesquisas (Geografia, DeviceAtlas, Classificações padrão) também ocorrerão como parte da tarefa de reprocessamento. Por padrão, a tarefa é executada na primeira sexta-feira de cada mês. Se necessário, o agendamento pode ser modificado pelo Atendimento ao cliente.

Para obter informações adicionais, entre em contato com o Atendimento [ao cliente da](https://helpx.adobe.com/support/programs/enterprise-support-terms.html)Adobe.
