---
description: A Adobe Data Workbench fornece ferramentas e processos para preparar seus dados para estar em conformidade com os Regulamentos Gerais de Proteção de Dados (GDPR).
title: Alinhamento do Data Workbench com o GDPR
exl-id: fdc43567-0c57-4851-9073-e295258a8074
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 4%

---

# Alinhamento do Data Workbench com o GDPR

{{eol}}

A Adobe Data Workbench fornece ferramentas e processos para preparar seus dados para a conformidade com a [!DNL General Data Protection Regulations] (GDPR).

Como todas as soluções da Adobe Analytics, o Data Workbench oferece suporte ao GDPR, fornecendo limpeza, exclusão e rotulagem de variáveis analíticas ao processar o feed de dados da Adobe Analytics. Para oferecer suporte às implementações do GDPR, o Adobe permite configurar processos para o GDPR de acordo com as permissões de sua empresa, conforme estabelecido em seu contrato com o Adobe. Consulte [Adobe Analytics e o GDPR para obter mais informações](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=pt-BR).

O Regulamento GDPR identifica as funções e obrigações das diferentes partes responsáveis pela ativação do GDPR (consulte [GDPR e seu negócio](https://www.adobe.com/br/privacy/general-data-protection-regulation.html)).

* Sua organização atua como a **controlador de dados** para determinar o contexto e a retenção de dados pessoais com base em suas necessidades e restrições. O Adobe processa e armazena esses dados em seu nome.
* O Adobe atua como **processador de dados** para fornecer o software e os serviços para implementar os requisitos do GDPR com base no seu contrato com o Adobe.
* Após a integração do Data Workbench com o serviço GDPR e de acordo com os padrões do GDPR, os visitantes de um site (a variável **titulares de dados**) pode exercer seu &quot;direito de ser esquecido&quot; pelo Adobe, o processador de dados. Para obter o direito de ser esquecido, você, como controlador de dados, pode fazer upload de IDs de visitante desafiadas para o Adobe a partir de uma interface do usuário ou API. Consulte a [Fluxo de trabalho do GDPR do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-workflow.html?lang=en) documentação para obter mais informações, incluindo o [enviar solicitações de acesso e exclusão](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-submit-access-delete.html) seção.

>[!NOTE]
>
>Para outras fontes de dados, sua organização será responsável pela limpeza das IDs de visitante desafiadas de outras fontes de log, como CRM, POS, IVR e outras fontes de dados brutas. Os pacotes de serviços com escopo personalizado estarão disponíveis para fornecer suporte às organizações por _fornecendo um conjunto completo de arquivos de substituição para cada fonte de dados_ que os contêineres de serviço em andamento sejam obrigados a suportar ou manter.

## Atualização do DWB para implementação do GDPR

A consultoria o aconselhará sobre o pacote de serviços apropriado para colocar as implementações existentes em conformidade. Entre em contato com o Gerente de sucesso do cliente (CSM) para obter mais informações.

Se necessário:

* [Atualizar para a versão mais recente](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) de Data Workbench. Para maior segurança, novos certificados e recursos de segurança foram adicionados nas versões do DWB 6.7 necessárias para a integração do GDPR.
* Se estiver usando registros de eventos herdados do TSV Analytics, atualize para o [Feed de dados médio](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2).
* Se estiver usando um UCP herdado (Unified Customer Process) com Transform para atualizar logs existentes, atualize para o processo atual. O processo atualizado gera diretamente um arquivo de pesquisa principal para mapear as IDs de visitante nas fontes.
* Padronizar o fluxo de dados para acomodar o serviço GDPR.
* Estabeleça um pacote de serviços com escopo personalizado para gerenciar outras fontes de log, como CRM, POS, IVR e outras fontes de dados brutas.
* Confirme o período padrão de retenção de dados de 25 meses ou mais no contrato do Analytics.
