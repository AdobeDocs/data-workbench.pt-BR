---
description: Inicializar e atualizar uma definição de esquema do perfil
title: Inicializar e atualizar uma definição de esquema do perfil
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
exl-id: e8190909-4416-4d4a-8901-130d01906773
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 7%

---

# Inicializar e atualizar uma definição de esquema do perfil{#initializing-and-updating-a-profile-s-schema-definition}

{{eol}}

1. Abra o **[!UICONTROL Schema Builder]** para o perfil que você deseja configurar.
1. A **[!UICONTROL Loading]** será exibida enquanto o esquema é recuperado do perfil de Insight. O tempo para carregar o schema depende da complexidade do perfil que está sendo carregado.
1. Ao concluir, você verá um resumo das diferenças entre os **[!UICONTROL Insight Schema]** no painel esquerdo e na **[!UICONTROL Dashboard Schema]** no painel direito. Este resumo aparecerá na parte inferior esquerda da **[!UICONTROL Schema Builder]** janela.

   >[!NOTE]
   >
   >Ao configurar o schema pela primeira vez, cada métrica, dimensão e filtro será listada de forma diferente do schema do painel. Isso ocorre porque os objetos de esquema do painel não existem no momento.

   ![](assets/schema_builder2.png)

1. Clique no botão **[!UICONTROL Synchronize with Schema]** para sincronizar todas as métricas, dimensões e filtros da visualização Esquema do Insight com a visualização Esquema do painel.
1. Quando terminar, você verá uma mensagem indicando que não há diferenças encontradas:

   ![](assets/diff_found.png)

1. Se houver erros com o Esquema do painel, como métricas e dimensões duplicadas, você deve corrigi-los manualmente antes de salvar.

   >[!NOTE]
   >
   >Você pode remover seletivamente qualquer métrica, dimensão ou filtro da variável **[!UICONTROL Dashboard Schema]** que você não deseja que apareça para os usuários finais do painel. Você receberá um aviso de que os itens não estão presentes no Esquema do painel, mas isso não impedirá que você seja salvo.

1. Quando estiver pronto, clique em **[!UICONTROL Save]** para salvar as alterações no esquema do painel.
1. O sistema de painel usará essa definição de esquema para preencher as dimensões, métricas e filtros disponíveis para os usuários finais da interface do painel.
