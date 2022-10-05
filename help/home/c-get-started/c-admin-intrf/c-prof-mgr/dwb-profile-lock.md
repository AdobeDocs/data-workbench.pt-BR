---
description: O arquivo Internal.cfg aplicado no Gerenciador de perfil impede que os usuários alterem seus perfis personalizados para os gerentes de Perfil, Dimension, Relatórios, Espaços de trabalho, Métricas e Filtros.
title: Bloquear perfis na estação de trabalho
uuid: 6b65d7c1-dade-4c6e-9d59-09693e62f3f5
exl-id: 2604ceea-0e55-4ae7-a286-e5257e974a64
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 5%

---

# Bloquear perfis na estação de trabalho{#locking-profiles-in-the-workstation}

{{eol}}

O arquivo Internal.cfg aplicado no Gerenciador de perfil impede que os usuários alterem seus perfis personalizados para os gerentes de Perfil, Dimension, Relatórios, Espaços de trabalho, Métricas e Filtros.

Você pode impedir que os arquivos de perfil sejam modificados e substituídos ao usar os gerentes salvando o **[!DNL Internal.cfg]** para seu perfil personalizado no Gerenciador de perfis. Esse arquivo de configuração impede que os usuários sobrescrevam vários arquivos ao trabalhar nos gerentes (acessados do **Administrador** > **Perfil** ).

**Bloquear perfis no Gerenciador de perfis**

1. No espaço de trabalho, clique com o botão direito do mouse **Administrador** > **Gerenciador de perfis**.

1. No **Gerenciador de perfis**, clique com o botão direito do mouse **[!DNL Context > Internal.cfg]** e **Tornar local**.

1. Clique com o botão direito do mouse na marca de seleção **Usuário** e salvar em uma `<custom profile>`.

![](assets/dwb_lock_profiles.png)

**Observação**: Somente as alterações nos arquivos de perfil pelos gerentes são impedidas ao salvar a variável **[!DNL Internal.cfg]** para um perfil personalizado no Gerenciador de perfis. Ainda é possível salvar espaços de trabalho no servidor a partir da bancada usando a **Salvar no servidor** comando.
