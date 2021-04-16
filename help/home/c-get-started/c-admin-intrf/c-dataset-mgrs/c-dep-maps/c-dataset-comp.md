---
description: Informações conceituais sobre componentes do conjunto de dados.
title: Componentes do conjunto de dados
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
exl-id: 6be625c5-1a2e-4b0d-9c34-5f3baec4ba81
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 1%

---

# Componentes do conjunto de dados{#dataset-components}

Informações conceituais sobre componentes do conjunto de dados.

A figura a seguir mostra um mapa de dependência cujos nós representam as fontes de log de um conjunto de dados, campos, transformações e dimensões estendidas.

![](assets/vis_DependencyMap.png)

* Um nó amarelo-verde representa uma ou mais fontes de log ou um filtro (como uma Condição de entrada de log) definido no conjunto de dados.

   * Um nó para uma fonte de log sempre é exibido mais à esquerda no mapa. Se o conjunto de dados tiver uma única fonte de log, o mapa exibirá Fonte de Log: *nome da fonte de log*. Se seu conjunto de dados tiver várias fontes de log, o mapa exibirá *número* Fontes de Log, onde número é a contagem de fontes de log. Por exemplo, se você tiver três fontes de log em seu conjunto de dados, seu mapa exibirá três Fontes de Log.

   * O mapa exibe um nó Condição de entrada de log para cada arquivo [!DNL log processing dataset include] , mas somente um nó Condição de entrada de log para transformação (se definido no arquivo [!DNL Transformation.cfg]). Se a Condição de entrada de log estiver vazia, ela não será exibida no mapa.

* Um nó cinza representa um campo listado no parâmetro Fields em um arquivo [!DNL Log Processing.cfg] ou [!DNL Log Processing include].

* Um nó azul representa uma transformação.
* Um nó verde representa uma dimensão estendida.

>[!NOTE]
>
>Se a pasta do Conjunto de dados do seu perfil contiver o arquivo [!DNL Insight Transform.cfg], o mapa de dependência mostrará as fontes de log, transformações e exportadores definidos para uso com Transformar. Para obter informações sobre Transformar, consulte o *Guia de Configuração do Conjunto de Dados*.

Ao ativar a opção de exibição Incluir [!DNL File Blocks] , o mapa exibe um único nó azul para todas as transformações definidas em um arquivo de configuração de conjunto de dados e um único nó verde para todas as dimensões estendidas definidas em um arquivo de configuração de conjunto de dados. Para obter mais informações sobre essa opção de exibição, consulte [Trabalhar com blocos de arquivo](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).
