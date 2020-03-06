---
description: É possível visualizar dados de vários perfis em um painel.
solution: Analytics
title: Seleções entre perfis
topic: Data workbench
uuid: e9377bcf-8de9-4952-a81a-863216f25fb7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Seleções entre perfis{#cross-profile-selections}

É possível visualizar dados de vários perfis em um painel.

Em alguns casos, as seleções de uma visualização também podem ser aplicadas a visualizações de outro perfil. Por exemplo, se você criar visualizações a partir de um perfil **[!UICONTROL Call Center]** **[!UICONTROL Website Traffic]** e um perfil em um painel, poderá selecionar um mês de destino para que os dados em todas as visualizações sejam segmentados simultaneamente nesse mês, apesar de serem conjuntos de dados totalmente diferentes.

Quando as visualizações de vários perfis existem em um painel, você pode fazer uma seleção em uma visualização se a dimensão dessa visualização também existir em todos os outros perfis representados na tela. No entanto, as seleções serão desativadas se uma dimensão não for encontrada globalmente em todas as outras visualizações na tela, e os usuários verão uma **[!UICONTROL Selections Disabled]** mensagem.

![](assets/selection_disabled.png)

>[!NOTE]
>
>Embora as dimensões possam compartilhar o mesmo nome em vários perfis, elas podem não ter o mesmo significado. É importante investigar cada dimensão para determinar se é apropriado usá-la para fazer seleções em vários perfis.

