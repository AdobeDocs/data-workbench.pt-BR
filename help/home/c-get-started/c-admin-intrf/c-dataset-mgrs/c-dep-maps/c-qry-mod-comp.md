---
description: Informações conceituais sobre componentes do modelo de consulta.
solution: Analytics
title: Componentes do modelo de consulta
topic: Data workbench
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Componentes do modelo de consulta{#query-model-components}

Informações conceituais sobre componentes do modelo de consulta.

A figura a seguir mostra um mapa de dependência cujos nós representam as métricas de um modelo de consulta, as dimensões derivadas e os filtros definidos nas pastas Dimensões, Métricas e Filtros dentro do perfil, bem como as dimensões estendidas definidas no conjunto de dados que se relacionam a eles de alguma forma.

![](assets/vis_DependencyMap_QueryModel.png)

* Um nó amarelo-verde representa um filtro.
* Um nó roxo representa uma métrica.
* Um nó azul-verde representa uma dimensão derivada.
* Um nó verde representa uma dimensão estendida (definida no conjunto de dados).
* Um nó vermelho representa uma métrica, uma dimensão derivada ou um filtro com uma dependência quebrada ou circular ou outro erro.

>[!NOTE]
>
>Como o mapa de dependência é projetado para acomodar dependências acíclicas, os nós envolvidos em dependências circulares podem não ser exibidos corretamente no mapa. Você pode procurar dependências circulares digitando &quot;dependência circular&quot; na caixa de [!DNL Search] texto. Para obter mais informações sobre o [!DNL Search] recurso, consulte [Pesquisando em um mapa](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

