---
description: O arquivo Internal.cfg aplicado no Gerenciador de perfis impede que os usuários alterem seus perfis personalizados pelos gerentes Perfil, Dimensões, Relatórios, Espaços de trabalho, Métricas e Filtros.
title: Bloquear perfis na estação de trabalho
uuid: 6b65d7c1-dade-4c6e-9d59-09693e62f3f5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Bloquear perfis na estação de trabalho{#locking-profiles-in-the-workstation}

O arquivo Internal.cfg aplicado no Gerenciador de perfis impede que os usuários alterem seus perfis personalizados pelos gerentes Perfil, Dimensões, Relatórios, Espaços de trabalho, Métricas e Filtros.

Você pode impedir que os arquivos de perfil sejam modificados e substituídos ao usar os gerentes, salvando o **[!DNL Internal.cfg]** arquivo no seu perfil personalizado no Gerenciador de perfis. Esse arquivo de configuração impede que os usuários sobrescrevam vários arquivos ao trabalhar nos gerentes (acessado pelo menu **Admin** > **Perfil** ).

**Bloquear perfis no Gerenciador de perfis**

1. Na área de trabalho, clique com o botão direito do mouse em **Admin** > Gerenciador **de perfis**.

1. No Gerenciador **de** perfis, clique com o botão direito do mouse **[!DNL Context > Internal.cfg]** e em **Tornar local**.

1. Clique com o botão direito do mouse na coluna **Usuário** e salve em um `<custom profile>`.

![](assets/dwb_lock_profiles.png)

**Observação**: Somente as alterações feitas nos arquivos de perfil pelos gerentes são impedidas ao salvar **[!DNL Internal.cfg]** em um perfil personalizado no Gerenciador de perfis. Você ainda pode salvar espaços de trabalho no servidor a partir da área de trabalho usando o comando **Salvar no servidor** .
