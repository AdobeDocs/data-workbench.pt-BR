---
description: Informações conceituais sobre espaços de trabalho e visualizações.
solution: Analytics
title: Espaços de trabalho e visualizações
topic: Data workbench
uuid: dc7fab6c-d8b4-4ed7-bad6-b3df14b9ebbf
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Espaços de trabalho e visualizações{#workspaces-and-visualizations}

Informações conceituais sobre espaços de trabalho e visualizações.

A figura a seguir mostra um mapa de dependência cujos nós representam os espaços de trabalho, relatórios, opções de menu e camadas de globo definidas no perfil. Essa opção funciona somente se a opção de [!DNL Query Model] exibição estiver ativada.

>[!NOTE]
>
>Se a opção de [!DNL Query Model] exibição não estiver ativada quando você escolher a opção de [!DNL Workspaces and Visualizations] exibição, uma mensagem de erro será exibida.

![](assets/vis_DependencyMap_QueryModelandWorkspaces.png)

* Um nó cinza representa um espaço de trabalho ou um relatório.
* Um nó amarelo-verde representa uma opção de menu.
* Um nó vermelho representa um espaço de trabalho, um relatório, uma opção de menu ou uma camada de globo com uma dependência quebrada ou circular ou outro erro.

>[!NOTE]
>
>Como o mapa de dependência é projetado para acomodar dependências acíclicas, os nós envolvidos em dependências circulares podem não ser exibidos corretamente no mapa. Você pode procurar dependências circulares digitando &quot;dependência circular&quot; na caixa de [!DNL Search] texto. Para obter mais informações sobre o [!DNL Search] recurso, consulte [Pesquisando em um mapa](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

Para obter descrições de outros nós no mapa, consulte Componentes [do modelo de](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f)consulta.
