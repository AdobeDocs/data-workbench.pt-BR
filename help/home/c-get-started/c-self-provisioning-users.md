---
description: Use a Workstation para gerenciar os usuários do Data Workbench.
title: Autoprovisionamento de usuários
uuid: e3c10bc4-2fa0-4368-9952-e38a4794aee9
exl-id: fba916bf-66a1-4b69-a1c0-cad5b27bbbba
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 3%

---

# Autoprovisionamento de usuários{#self-provisioning-of-users}

{{eol}}

Use a Workstation para gerenciar os usuários do Data Workbench.

Você pode usar a Workstation para se conectar ao Data Workbench Server, configurando o certificado necessário do Adobe. Este certificado auxilia na comunicação SSL e na autorização para usar os recursos e recursos licenciados. Na autenticação baseada em certificado, é necessário adquirir e configurar vários certificados para usar a estação de trabalho em várias máquinas. Além disso, o provisionamento e os direitos do usuário são gerenciados pelo Adobe e você deve entrar em contato com o Adobe para obter novos certificados ou a revogação de certificados.

A partir do DWB 6.7, a estação de trabalho oferece suporte à autenticação de usuário por meio de nome de usuário e senha.

Embora a autenticação/autorização baseada em certificado ainda funcione para a configuração, é altamente recomendável migrar para a autenticação baseada em credenciais mais recente. Na abordagem mais recente, os usuários da estação de trabalho se autenticam por meio do Adobe Identity Management System (IMS). Antes de usarem a estação de trabalho, eles precisam ter acesso aos recursos por meio do [Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=pt-BR) pelo administrador da organização.

O novo modelo de autenticação e provisionamento de usuário ajuda a:

* Autoprovisionamento de usuários e grupos por meio do Admin Console. Não é necessário entrar em contato com o Adobe para adicionar, remover ou modificar os direitos de licença dos usuários.
* Acessar a estação de trabalho de vários computadores sem perder o estado de configuração fazendo logon usando credenciais. O cache local é excluído ao fazer logoff, o perfil atual é fechado e o perfil Configuração fica ativo.

## Introdução

Antes de começar, entre em contato com o Adobe para adicionar sua organização ao Admin Console. Dependendo dos serviços que você adquiriu, o Adobe fornecerá a organização para você. Por exemplo, as organizações podem ter acesso ao Serviço de atribuição ou às builds Beta, ou ambos. Quando uma organização é configurada, o administrador da organização pode adicionar usuários e grupos. Consulte [Gerenciar usuários e produtos do Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) no Experience Cloud para obter mais informações. O administrador da organização também pode configurar restrições de uso para usuários diferentes dependendo de suas funções. Por exemplo, usuários que não são de pré-lançamento não precisam acessar as builds Beta.

Cada usuário provisionado adicionado a essa organização por meio do Admin Console terá acesso para usar a Data Workbench. Os subserviços só podem ser ativados ou desativados para cada usuário, dependendo do acesso ao produto. Quando um usuário é atualizado do certificado para o IMS, todos os dados locais são copiados para o novo diretório de usuário do IMS.

>[!NOTE]
>
>Uma sessão dura 6 horas no servidor e 23 horas no cliente, a menos que o token de acesso seja atualizado. Quando o token é atualizado, você pode usar o Client sem fazer logon novamente.

Pelo menos uma Configuração no nível do produto precisa ser criada no Admin Console pelo administrador antes de conceder acesso a qualquer usuário.

O sinalizador booleano **Usar IMS** pode ser adicionado a [!DNL Insight.cfg] para fallback no modo de certificado. Para obter informações sobre como configurar o Controle de Acesso para usuários do IMS, consulte [Atualizar o arquivo de controle de acesso](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/install-servers/insight-server-dpu/c-updt-accss-ctrl-file.html).

## Resolução de conflitos

Quando um usuário está conectado a várias máquinas com a mesma conta IMS no mesmo perfil e está no modo offline em uma das máquinas, um `.conflict` pode ser um formulário e uma janela pop-up informará você. Isso ocorre quando há uma diferença no conteúdo com qualquer arquivo (espaços de trabalho, dimensões, filtros etc.) sincronizado em ambos os computadores em [!DNL User\Profile\] no servidor e no cliente . Um backup será criado no `.conflict` e nenhum dado será perdido. Um sinalizador booleano em [!DNL Insight.cfg] O oferece a capacidade de desativar essa pop-up de conflito.

Sinalizador: Notificações de conflito

Isso se aplica a espaços de trabalho, métricas, dimensões etc. na Pasta do usuário.
