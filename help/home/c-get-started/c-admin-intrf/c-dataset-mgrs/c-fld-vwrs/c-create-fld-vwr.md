---
description: Você pode abrir um visualizador de campo como um texto explicativo a partir de um mapa de dependência ou como uma visualização independente no menu Admin.
solution: Analytics
title: Criar um visualizador de campo
topic: Data workbench
uuid: df48e728-96f9-4432-82c8-f8047840ffb9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Criar um visualizador de campo{#create-a-field-viewer}

Você pode abrir um visualizador de campo como um texto explicativo a partir de um mapa de dependência ou como uma visualização independente no menu Admin.

## Criar um visualizador de campos a partir de um mapa de dependência {#section-040cb83c902b49c48b841d35abc127e5}

Quando você abre um visualizador de campo a partir de um mapa de dependência (como mostrado em [Abrindo visualizadores](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27)de campo), o visualizador é preenchido automaticamente com base na fonte de log, na transformação ou na dimensão em que você clicou com o botão direito do mouse. Para uma fonte de log ou uma transformação, os campos no visualizador são entradas ou saídas da fonte de log ou da transformação. Para uma dimensão, os campos são entradas da dimensão. Você pode adicionar e remover campos conforme desejado.

## Criar visualizadores de campo como uma visualização independente {#section-11d10e46631d4fdca45d7534336e1e80}

Ao abrir um visualizador de campo como uma visualização independente, você pode criar um [!DNL Log Processing Field Viewer] ou um [!DNL Transformation Field Viewer]. O visualizador está em branco e você deve adicionar os campos desejados ao visualizador. Para um [!DNL Log Processing Field Viewer], você pode adicionar campos do [!DNL Log Processing.cfg] arquivo ou de qualquer [!DNL Log Processing dataset include] arquivo. Para um [!DNL Transformation Field Viewer], você pode adicionar campos do [!DNL Transformation.cfg] arquivo ou de qualquer [!DNL Transformation dataset include] arquivo.

Para obter mais informações sobre configuração e inclusão de arquivos, consulte o Guia *de Configuração de* Conjunto de Dados.

## Adicionar e remover um campo {#section-9c0d4f5735a044a8b21dc7a99c63a59a}

**Para adicionar um campo a um visualizador de campo**

* Clique com o botão direito do mouse no visualizador de campos e clique em **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

   -ou-

* Clique com o botão direito do mouse em uma coluna existente no visualizador de campos e clique em **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

O nome do campo refere-se ao nome do campo e a instância refere-se a onde na configuração do conjunto de dados o campo é usado, como um estágio de processamento do conjunto de dados ou uma transformação. Alguns campos são usados em vários locais na configuração do conjunto de dados (por exemplo, um campo pode ser modificado por várias transformações), portanto, você deve selecionar qual instância do campo adicionar ao visualizador de campo.

Na lista de campos disponíveis, um X é exibido à esquerda de qualquer campo já exibido no visualizador.

**Para remover um campo de um visualizador de campo**

* Clique com o botão direito do mouse na coluna do campo que deseja remover e clique em **[!UICONTROL Remove Field]**.

