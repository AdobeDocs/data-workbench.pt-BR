---
description: Um visualizador de campo é uma tabela que contém os valores de um ou mais campos de dados.
solution: Analytics
title: Visualizador de campo
topic: Data workbench
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Visualizador de campo{#field-viewer}

Um visualizador de campo é uma tabela que contém os valores de um ou mais campos de dados.

Os campos cujos valores são exibidos são entradas ou saídas de fontes de log de um conjunto de dados, transformações ou dimensões estendidas. O nome do campo é mostrado no cabeçalho da coluna e cada linha contém o valor do campo para uma única linha de dados de origem. Como os visualizadores de campo permitem que você veja os valores de um campo, eles são úteis para escrever e testar expressões [](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c)regulares.

Você pode abrir um visualizador de campo como um texto explicativo de um [!DNL Transformation Dependency] mapa ou como uma visualização independente do [!DNL Admin] menu:

* Criação de um visualizador de campo a partir de um [!DNL Transformation Dependency] mapa. Quando você abre um visualizador de campo a partir de um [!DNL Transformation Dependency] mapa, o visualizador é preenchido automaticamente com base na fonte de log, transformação ou dimensão em que você clicou com o botão direito do mouse. Para uma fonte de log ou uma transformação, os campos no visualizador são entradas ou saídas da fonte de log ou da transformação. Para uma dimensão, os campos são entradas da dimensão. Você pode adicionar e remover campos conforme desejado.

* Criação de um visualizador de campo como visualização independente. Ao abrir um visualizador de campo como uma visualização independente, você pode criar um [!DNL Log Processing Field Viewer] ou um [!DNL Transformation Field Viewer]. O visualizador está em branco e você deve adicionar os campos desejados ao visualizador. Para um [!DNL Log Processing Field Viewer], você pode adicionar campos do [!DNL Log Processing.cfg] arquivo ou de qualquer [!DNL Log Processing Dataset Include] arquivo. Para um [!DNL Transformation Field Viewer], você pode adicionar campos do [!DNL Transformation.cfg] arquivo ou de qualquer [!DNL Transformation Dataset Include] arquivo.

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>Os visualizadores de campo não são visualizações de tabela; portanto, elas não têm as propriedades associadas às tabelas.

Para obter informações sobre como adicionar e remover campos e filtrar em um visualizador de campos, consulte Interfaces [](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74)administrativas.
