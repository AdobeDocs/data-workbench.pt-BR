---
description: Informações conceituais sobre componentes do conjunto de dados.
solution: Analytics
title: Componentes do conjunto de dados
topic: Data workbench
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Componentes do conjunto de dados{#dataset-components}

Informações conceituais sobre componentes do conjunto de dados.

A figura a seguir mostra um mapa de dependência cujos nós representam as fontes de log, campos, transformações e dimensões estendidas de um conjunto de dados.

![](assets/vis_DependencyMap.png)

* Um nó amarelo-verde representa uma ou mais fontes de log ou um filtro (como uma Condição de entrada de log) definido no conjunto de dados.

   * Um nó para uma fonte de log sempre é exibido mais à esquerda no mapa. Se o conjunto de dados tiver uma única fonte de log, o mapa exibirá a Fonte de Log: nome *da origem do* log. Se o conjunto de dados tiver várias fontes de log, o mapa exibirá o *número* de Fontes de Log, onde o número é a contagem de fontes de log. Por exemplo, se você tiver três fontes de log no conjunto de dados, o mapa exibirá 3 Fontes de Log.

   * O mapa exibe um nó Condição de entrada de registro para cada [!DNL log processing dataset include] arquivo, mas apenas um nó Condição de entrada de registro para transformação (se definido no [!DNL Transformation.cfg] arquivo). Se a Condição de entrada do registro estiver vazia, ela não será exibida no mapa.

* Um nó cinza representa um campo listado no parâmetro Campos em um [!DNL Log Processing.cfg] arquivo ou [!DNL Log Processing include] .

* Um nó azul representa uma transformação.
* Um nó verde representa uma dimensão estendida.

>[!NOTE]
>
>Se a pasta Dataset do seu perfil contiver o arquivo, o mapa de dependência [!DNL Insight Transform.cfg]mostrará as fontes de log, as transformações e os exportadores definidos para uso com Transform. Para obter informações sobre Transformação, consulte o Guia *de configuração de* conjuntos de dados.

Quando você ativa a opção de exibição Incluir [!DNL File Blocks] , o mapa exibe um único nó azul para todas as transformações definidas em um arquivo de configuração de conjunto de dados e um único nó verde para todas as dimensões estendidas definidas em um arquivo de configuração de conjunto de dados. Para obter mais informações sobre essa opção de exibição, consulte [Trabalhar com blocos](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc)de arquivos.
