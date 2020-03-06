---
description: Use a estação de trabalho para gerenciar os usuários da análise de big data.
title: Autoprovisionamento de usuários
uuid: e3c10bc4-2fa0-4368-9952-e38a4794aee9
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Autoprovisionamento de usuários{#self-provisioning-of-users}

Use a estação de trabalho para gerenciar os usuários da análise de big data.

Você pode usar a estação de trabalho para se conectar ao servidor da análise de big data configurando o certificado necessário da Adobe. Este certificado auxilia na comunicação SSL e na autorização para usar os recursos e recursos licenciados. Na autenticação baseada em certificados, você precisa adquirir e configurar vários certificados para usar a estação de trabalho em várias máquinas. Além disso, o provisionamento e os direitos do usuário são gerenciados pela Adobe e você deve entrar em contato com a Adobe para obter novos certificados ou revogação de certificados.

A partir do DWB 6.7, a estação de trabalho oferece suporte à autenticação de usuário por meio do nome de usuário e senha.

Embora a autenticação/autorização baseada em certificados ainda funcione para a sua configuração, é altamente recomendável migrar para a autenticação baseada em credenciais mais recente. Na abordagem mais recente, os usuários da estação de trabalho se autenticam por meio do Adobe Identity Management System (IMS). Antes de poderem usar a estação de trabalho, eles precisam receber acesso aos recursos por meio do Console de [administração](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) pelo administrador da organização.

O novo modelo de autenticação e provisionamento de usuário ajuda a:

* Autoprovisionamento de usuários e grupos por meio do Admin Console. Não é necessário entrar em contato com a Adobe para adicionar, remover ou modificar direitos de licença para usuários.
* Acessar a estação de trabalho de vários computadores sem perder o estado de configuração fazendo logon usando credenciais. O cache local é excluído ao sair, o perfil atual é fechado e o perfil de Configuração fica ativo.

## Introdução

Antes de começar, entre em contato com a Adobe para adicionar sua organização ao Admin Console. Dependendo dos serviços que você comprou, a Adobe fornecerá a organização para você. Por exemplo, as organizações podem ter acesso ao serviço de Atribuição ou às compilações Beta, ou a ambos. Depois que uma organização é configurada, o administrador da organização pode adicionar usuários e grupos. Consulte [Gerenciar usuários e produtos](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) da Experience Cloud na Experience Cloud para obter mais informações. O administrador da organização também pode configurar restrições de uso para usuários diferentes dependendo de suas funções. Por exemplo, os usuários que não fazem pré-lançamento não precisam acessar as compilações Beta.

Cada usuário provisionado adicionado a essa organização por meio do Admin Console terá acesso para usar o Análise de big data. Os subserviços só podem ser habilitados ou desabilitados para cada usuário, dependendo do acesso ao produto. Quando um usuário é atualizado de certificado para IMS, todos os dados locais serão copiados para o novo diretório de usuário IMS.

>[!NOTE]
>
>Uma sessão dura 6 horas no servidor e 23 horas no cliente, a menos que o token de acesso seja atualizado. Quando o token for atualizado, você poderá usar o Client sem fazer logon novamente.

Pelo menos uma Configuração de nível de produto precisa ser criada no Admin Console pelo administrador antes de dar acesso a qualquer usuário.

O sinalizador booleano **Use IMS** pode ser adicionado ao fallback [!DNL Insight.cfg] para o modo de certificado. Para obter informações sobre como configurar o Controle de Acesso para usuários de IMS, consulte [Atualização do Arquivo](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/install-servers/insight-server-dpu/c-updt-accss-ctrl-file.html)de Controle de Acesso.

## Resolução de conflitos

Quando um usuário está conectado a várias máquinas com a mesma conta IMS no mesmo perfil e está no modo offline em uma das máquinas, um formulário `.conflict` pode ser exibido e uma janela pop-up o informa. Isso ocorre quando há diferença no conteúdo com qualquer arquivo (espaços de trabalho, dimensões, filtros etc.) sincronizado em ambos os computadores em [!DNL User\Profile\] no servidor e no cliente. Um backup será criado no `.conflict` arquivo e nenhum dado será perdido. Um sinalizador booleano no [!DNL Insight.cfg] oferece a capacidade de desativar essa pop-up de conflito.

Sinalizador: Notificações de conflito

Isso se aplica a espaços de trabalho, métricas, dimensões etc. em Pasta do usuário.
