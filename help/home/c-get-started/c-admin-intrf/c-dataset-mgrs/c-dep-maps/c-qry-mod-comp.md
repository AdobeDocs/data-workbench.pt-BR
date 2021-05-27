---
description: Informações conceituais sobre componentes do modelo de consulta.
title: Componentes do modelo de query
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
exl-id: 1f5d0a3a-6647-4762-ab20-9d80e467d48f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 3%

---

# Componentes do modelo de query{#query-model-components}

Informações conceituais sobre componentes do modelo de consulta.

A figura a seguir mostra um mapa de dependência cujos nós representam as métricas, dimensões derivadas e filtros de um modelo de consulta definidos nas pastas Dimension, Métricas e Filtros do perfil, bem como as dimensões estendidas definidas no conjunto de dados que estão relacionadas a eles de alguma forma.

![](assets/vis_DependencyMap_QueryModel.png)

* Um nó amarelo-verde representa um filtro.
* Um nó violeta representa uma métrica.
* Um nó azul-verde representa uma dimensão derivada.
* Um nó verde representa uma dimensão estendida (definida no conjunto de dados).
* Um nó vermelho representa uma métrica, uma dimensão derivada ou um filtro com uma dependência quebrada ou circular ou outro erro.

>[!NOTE]
>
>Como o mapa de dependência é projetado para acomodar dependências acíclicas, os nós envolvidos em dependências circulares podem não ser exibidos corretamente no mapa. Você pode procurar dependências circulares digitando &quot;dependência circular&quot; na caixa de texto [!DNL Search]. Para obter mais informações sobre o recurso [!DNL Search], consulte [Pesquisando em um mapa](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).
