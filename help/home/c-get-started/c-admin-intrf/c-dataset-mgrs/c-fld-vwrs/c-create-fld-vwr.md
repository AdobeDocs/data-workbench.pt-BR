---
description: Abra um visualizador de campo como uma chamada em um mapa de dependência ou como uma visualização independente no menu Admin .
title: Criar um visualizador de campo
uuid: df48e728-96f9-4432-82c8-f8047840ffb9
exl-id: a2563dbb-1d1f-4ed8-b73b-6ac7a2687405
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 2%

---

# Criar um visualizador de campo{#create-a-field-viewer}

Abra um visualizador de campo como uma chamada em um mapa de dependência ou como uma visualização independente no menu Admin .

## Criar um visualizador de campo a partir de um mapa de dependências {#section-040cb83c902b49c48b841d35abc127e5}

Ao abrir um visualizador de campo a partir de um mapa de dependência (como mostrado em [Abrindo visualizadores de campo](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27)), o visualizador é preenchido automaticamente com base na fonte de log, transformação ou dimensão em que você clicou com o botão direito do mouse. Para uma fonte de log ou uma transformação, os campos no visualizador são entradas ou saídas da fonte de log ou transformação. Para uma dimensão, os campos são entradas da dimensão. Você pode adicionar e remover campos, conforme desejado.

## Criar um visualizador de campo como uma visualização independente {#section-11d10e46631d4fdca45d7534336e1e80}

Ao abrir um visualizador de campo como uma visualização independente, você pode criar um [!DNL Log Processing Field Viewer] ou um [!DNL Transformation Field Viewer]. O visualizador fica em branco e você deve adicionar os campos desejados ao visualizador. Para um [!DNL Log Processing Field Viewer], você pode adicionar campos do arquivo [!DNL Log Processing.cfg] ou qualquer arquivo [!DNL Log Processing dataset include]. Para um [!DNL Transformation Field Viewer], você pode adicionar campos do arquivo [!DNL Transformation.cfg] ou qualquer arquivo [!DNL Transformation dataset include].

Para obter mais informações sobre configuração e incluir arquivos, consulte o *Guia de Configuração de Conjunto de Dados*.

## Adicionar e remover um campo {#section-9c0d4f5735a044a8b21dc7a99c63a59a}

**Para adicionar um campo a um visualizador de campo**

* Clique com o botão direito do mouse no visualizador de campo e clique em **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]*** > *&lt;**[!UICONTROL instance]***.

   -ou-

* Clique com o botão direito do mouse em uma coluna existente no visualizador de campos e clique em **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]*** > *&lt;**[!UICONTROL instance]***.

O nome do campo refere-se ao nome do campo e a instância refere-se a onde na configuração do conjunto de dados o campo é usado, como um estágio de processamento de conjunto de dados ou uma transformação. Alguns campos são usados em vários locais na configuração do conjunto de dados (por exemplo, um campo pode ser modificado por várias transformações), portanto, você deve selecionar qual instância do campo será adicionada ao visualizador de campo.

Na lista de campos disponíveis, um X é exibido à esquerda de qualquer campo já exibido no visualizador.

**Remoção de um campo de um visualizador de campo**

* Clique com o botão direito do mouse na coluna do campo que deseja remover e clique em **[!UICONTROL Remove Field]**.
