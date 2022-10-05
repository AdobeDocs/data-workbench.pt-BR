---
description: É possível visualizar dados de vários perfis em um painel.
title: Seleções entre perfis
uuid: e9377bcf-8de9-4952-a81a-863216f25fb7
exl-id: a14400bf-64e3-44be-b9ab-d8a9ded406ae
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 2%

---

# Seleções entre perfis{#cross-profile-selections}

{{eol}}

É possível visualizar dados de vários perfis em um painel.

Em alguns casos, as seleções de uma visualização também podem ser aplicadas a visualizações de outro perfil. Por exemplo, se você criar visualizações a partir de um **[!UICONTROL Call Center]**perfil e um **[!UICONTROL Website Traffic]** em um painel, você pode selecionar um mês de destino para que os dados em todas as visualizações sejam segmentados simultaneamente nesse mês, apesar de haver conjuntos de dados totalmente diferentes.

Quando existem visualizações de vários perfis em um painel, você pode fazer uma seleção em uma visualização se a dimensão dessa visualização também existir em todos os outros perfis representados na tela. No entanto, as seleções serão desativadas se uma dimensão não for encontrada globalmente em todas as outras visualizações na tela, e os usuários verão uma **[!UICONTROL Selections Disabled]** mensagem.

![](assets/selection_disabled.png)

>[!NOTE]
>
>Embora as dimensões possam compartilhar o mesmo nome em vários perfis, elas podem não ter o mesmo significado. É importante investigar cada dimensão para determinar se é apropriado usá-la para fazer seleções em vários perfis.
