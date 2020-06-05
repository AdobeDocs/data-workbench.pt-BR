---
description: O Adobe Data Workbench fornece ferramentas e processos para preparar seus dados para cumprir o Regulamento Geral de Proteção de Dados (RGPD).
solution: Analytics
title: Suporte para análise de big data para RGPD
topic: Data workbench
translation-type: tm+mt
source-git-commit: 279e71f3da3f0ebc29091e88b87666a22a36a8d6
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 2%

---


# Suporte para análise de big data para RGPD

O Adobe Data Workbench fornece ferramentas e processos para preparar seus dados para estar em conformidade com o [!DNL General Data Protection Regulations] (RGPD).

Como todas as soluções do Adobe Analytics, o Análise de big data oferece suporte para o RGPD ao fornecer limpeza, exclusão e rotulagem de variáveis de análise ao processar o feed de dados do Adobe Analytics. Para suportar implementações de RGPD, a Adobe permite que você configure processos para RGPD de acordo com as permissões de sua empresa, conforme estabelecido em seu contrato com a Adobe. Consulte [Adobe Analytics e RGPD para obter mais informações](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html).

O Regulamento RGPD identifica os papéis e obrigações das diferentes partes responsáveis pela ativação do RGPD (ver [RGPD e Your Business](https://www.adobe.com/br/privacy/general-data-protection-regulation.html)).

* Sua organização atua como o controlador **de** dados para determinar o contexto e a retenção de dados pessoais com base em suas necessidades e restrições. Em seguida, a Adobe processa e armazena esses dados em seu nome.
* A Adobe atua como o processador **de** dados para fornecer o software e os serviços necessários para implementar os requisitos de RGPD com base em seu acordo com a Adobe.
* Após a integração do Análise de big data com o serviço do RGPD e de acordo com os padrões do RGPD, os visitantes de um site (as pessoas **** com os dados) podem exercer seu &quot;direito de ser esquecido&quot; pela Adobe, o processador de dados. Para obter o direito de ser esquecido, você, como controlador de dados, pode fazer upload de IDs de visitante desafiadas para a Adobe a partir de uma interface do usuário ou API. Consulte a documentação do Fluxo de trabalho [GDPR do](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html) Adobe Analytics para obter mais informações, incluindo a seção [enviar solicitações](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html) de acesso e exclusão.

>[!NOTE]
>
>Para outras fontes de dados, sua organização será responsável pela limpeza de IDs de visitante desafiadas de outras fontes de registro, como CRM, POS, IVR e outras fontes de dados brutos. Os pacotes de serviços com escopo personalizado estarão disponíveis para fornecer suporte às organizações, _fornecendo um conjunto completo de arquivos de substituição para cada fonte_ de dados que os contêineres de serviço em andamento precisam suportar ou manter.

## Atualização do DWB para implementação do RGPD

A consulta o aconselhará sobre o pacote de serviços apropriado para tornar as implementações existentes compatíveis. Entre em contato com o Gerente de sucesso do cliente (CSM) para obter mais informações.

Se necessário:

* [Atualize para a versão](https://docs.adobe.com/content/help/pt-BR/data-workbench/using/release-notes/release-notes.html) mais recente do Análise de big data. Para obter a maior segurança, novos certificados e recursos de segurança foram adicionados nas versões do DWB 6.7 necessárias para a integração do RGPD.
* Se estiver usando registros de eventos do TSV Analytics herdados, atualize para o feed [de dados do](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2)Avro.
* Se estiver usando um UCP herdado (Unified Customer Process) com Transform para atualizar registros existentes, atualize para o processo atual. O processo atualizado gera diretamente um arquivo de pesquisa mestre para mapear IDs de visitante nas fontes.
* Padronizar o fluxo de dados para acomodar o serviço RGPD.
* Estabeleça um pacote de serviços com escopo personalizado para gerenciar outras fontes de log, como CRM, POS, IVR e outras fontes de dados brutos.
* Confirme o período padrão de retenção de dados de 25 meses ou mais no contrato do Analytics.
