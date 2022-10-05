---
description: Informações conceituais sobre espaços de trabalho e visualizações.
title: Espaços de trabalho e visualizações
uuid: dc7fab6c-d8b4-4ed7-bad6-b3df14b9ebbf
exl-id: a70748dd-8190-4d1b-9ee1-1011b73a1a86
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 3%

---

# Espaços de trabalho e visualizações{#workspaces-and-visualizations}

{{eol}}

Informações conceituais sobre espaços de trabalho e visualizações.

A figura a seguir mostra um mapa de dependência cujos nós representam os espaços de trabalho, relatórios, opções de menu e camadas de globo definidas no perfil. Essa opção funciona somente se a variável [!DNL Query Model] a opção de exibição está ativada.

>[!NOTE]
>
>Se a variável [!DNL Query Model] a opção de exibição não é ativada ao escolher a variável [!DNL Workspaces and Visualizations] opção de exibição, uma mensagem de erro é exibida.

![](assets/vis_DependencyMap_QueryModelandWorkspaces.png)

* Um nó cinza representa um espaço de trabalho ou um relatório.
* Um nó amarelo-verde representa uma opção de menu.
* Um nó vermelho representa um espaço de trabalho, relatório, opção de menu ou camada de globo com uma dependência quebrada ou circular ou outro erro.

>[!NOTE]
>
>Como o mapa de dependência é projetado para acomodar dependências acíclicas, os nós envolvidos em dependências circulares podem não ser exibidos corretamente no mapa. Você pode procurar dependências circulares digitando &quot;dependência circular&quot; no [!DNL Search] caixa de texto. Para obter mais informações sobre o [!DNL Search] recurso, consulte [Pesquisar em um mapa](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

Para obter descrições de outros nós no mapa, consulte [Componentes do modelo de consulta](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f).
