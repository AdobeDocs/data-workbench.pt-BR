---
description: Um visualizador de campo é uma tabela que contém os valores de um ou mais campos de dados.
title: Visualizador de campo
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
exl-id: 53ede4aa-4865-4e67-b3b1-e3e6287f29d7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 1%

---

# Visualizador de campo{#field-viewer}

Um visualizador de campo é uma tabela que contém os valores de um ou mais campos de dados.

Os campos cujos valores são exibidos são entradas ou saídas de fontes de log de um conjunto de dados, transformações ou dimensões estendidas. O nome do campo é mostrado no cabeçalho da coluna e cada linha contém o valor do campo para uma única linha de dados de origem. Como os visualizadores de campo permitem que você veja os valores de um campo, eles são úteis por escrito e no teste de [expressões regulares](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

Você pode abrir um visualizador de campo como uma chamada em um mapa [!DNL Transformation Dependency] ou como uma visualização independente no menu [!DNL Admin]:

* Criar um visualizador de campo a partir de um mapa [!DNL Transformation Dependency]. Quando você abre um visualizador de campo a partir de um mapa [!DNL Transformation Dependency], o visualizador é preenchido automaticamente com base na fonte de log, transformação ou dimensão em que você clicou com o botão direito do mouse. Para uma fonte de log ou uma transformação, os campos no visualizador são entradas ou saídas da fonte de log ou transformação. Para uma dimensão, os campos são entradas da dimensão. Você pode adicionar e remover campos, conforme desejado.

* Criar um visualizador de campo como visualização independente. Ao abrir um visualizador de campo como uma visualização independente, você pode criar um [!DNL Log Processing Field Viewer] ou um [!DNL Transformation Field Viewer]. O visualizador fica em branco e você deve adicionar os campos desejados ao visualizador. Para um [!DNL Log Processing Field Viewer], você pode adicionar campos do arquivo [!DNL Log Processing.cfg] ou qualquer arquivo [!DNL Log Processing Dataset Include]. Para um [!DNL Transformation Field Viewer], você pode adicionar campos do arquivo [!DNL Transformation.cfg] ou qualquer arquivo [!DNL Transformation Dataset Include].

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>Visualizadores de campo não são visualizações de tabela; portanto, elas não têm as propriedades associadas às tabelas.

Para obter informações sobre adicionar e remover campos e filtrar em um visualizador de campo, consulte [Interfaces administrativas](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).
