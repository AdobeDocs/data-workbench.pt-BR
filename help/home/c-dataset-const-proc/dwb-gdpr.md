---
description: A Adobe Data Workbench fornece ferramentas e processos para preparar seus dados para estar em conformidade com os Regulamentos Gerais de Proteção de Dados (GDPR).
title: Alinhamento do Data Workbench com o GDPR
exl-id: fdc43567-0c57-4851-9073-e295258a8074
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 4%

---

# Alinhamento do Data Workbench com o GDPR

A Data Workbench do Adobe fornece ferramentas e processos para preparar seus dados para estar em conformidade com o [!DNL General Data Protection Regulations] (GDPR).

Como todas as soluções da Adobe Analytics, o Data Workbench oferece suporte ao GDPR, fornecendo limpeza, exclusão e rotulagem de variáveis analíticas ao processar o feed de dados da Adobe Analytics. Para oferecer suporte às implementações do GDPR, o Adobe permite configurar processos para o GDPR de acordo com as permissões de sua empresa, conforme estabelecido em seu contrato com o Adobe. Consulte [Adobe Analytics e GDPR para obter informações adicionais](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html).

O Regulamento GDPR identifica as funções e obrigações das diferentes partes responsáveis pela ativação do GDPR (consulte [GDPR e a sua empresa](https://www.adobe.com/br/privacy/general-data-protection-regulation.html)).

* Sua organização atua como o **controlador de dados** para determinar o contexto e a retenção de dados pessoais com base em suas necessidades e restrições. O Adobe processa e armazena esses dados em seu nome.
* O Adobe atua como o **processador de dados** para fornecer o software e os serviços necessários para implementar os requisitos do GDPR com base no seu contrato com o Adobe.
* Após a integração do Data Workbench com o serviço GDPR e de acordo com os padrões do GDPR, os visitantes de um site (o **titulares de dados**) podem exercer seu &quot;direito de ser esquecido&quot; pelo Adobe, o processador de dados. Para obter o direito de ser esquecido, você, como controlador de dados, pode fazer upload de IDs de visitante desafiadas para o Adobe a partir de uma interface do usuário ou API. Consulte a documentação [Fluxo de trabalho do GDPR do Adobe Analytics](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html) para obter mais informações, incluindo a seção [enviar solicitações de acesso e exclusão](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html).

>[!NOTE]
>
>Para outras fontes de dados, sua organização será responsável pela limpeza das IDs de visitante desafiadas de outras fontes de log, como CRM, POS, IVR e outras fontes de dados brutas. Os pacotes de serviços com escopo personalizado estarão disponíveis para fornecer suporte às organizações _fornecendo um conjunto completo de arquivos de substituição para cada fonte de dados_ que os retentores de serviço contínuo são necessários para suportar ou manter.

## Atualização do DWB para implementação do GDPR

A consultoria o aconselhará sobre o pacote de serviços apropriado para colocar as implementações existentes em conformidade. Entre em contato com o Gerente de sucesso do cliente (CSM) para obter mais informações.

Se necessário:

* [Atualize para a ](https://docs.adobe.com/content/help/pt-BR/data-workbench/using/release-notes/release-notes.html) versão mais recente do Data Workbench. Para maior segurança, novos certificados e recursos de segurança foram adicionados nas versões do DWB 6.7 necessárias para a integração do GDPR.
* Se estiver usando registros de eventos herdados do TSV Analytics, atualize para o [Feed de dados Avro](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2).
* Se estiver usando um UCP herdado (Unified Customer Process) com Transform para atualizar logs existentes, atualize para o processo atual. O processo atualizado gera diretamente um arquivo de pesquisa principal para mapear as IDs de visitante nas fontes.
* Padronizar o fluxo de dados para acomodar o serviço GDPR.
* Estabeleça um pacote de serviços com escopo personalizado para gerenciar outras fontes de log, como CRM, POS, IVR e outras fontes de dados brutas.
* Confirme o período padrão de retenção de dados de 25 meses ou mais no contrato do Analytics.
