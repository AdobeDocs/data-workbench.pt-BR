---
description: As chamadas de retorno são janelas adicionadas a um espaço de trabalho para chamar a atenção para um elemento de dimensão específico ao criar uma nova visualização com uma seleção virtual desse elemento.
title: Adicionar chamadas a um espaço de trabalho
uuid: fb3dd74d-da20-40cb-bc96-e56d25003e48
exl-id: fcdb9231-d44a-4287-b799-6a66f7f79432
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 2%

---

# Adicionar chamadas a um espaço de trabalho{#adding-callouts-to-a-workspace}

As chamadas de retorno são janelas adicionadas a um espaço de trabalho para chamar a atenção para um elemento de dimensão específico ao criar uma nova visualização com uma seleção virtual desse elemento.

O Data Workbench é fornecido com um conjunto padrão de tipos de chamada. Como sua implementação pode ser totalmente personalizada, os tipos de chamada disponíveis que aparecem em sua implementação podem ser diferentes dos documentados neste guia.

Por padrão, o Data Workbench fornece as seguintes chamadas:

* [Anotação](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-7b6742160b3f4aed872a09c8c023f90d)
* [Gráfico de linhas em branco](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [Gráfico de Dispersão em Branco](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [Tabela em branco](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [Legenda de confiança](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-386d1293ddc24a0c9cccb332e20db791)
* [Legenda da métrica](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-daa6d372c22246d9827880a9d6e804d8)

>[!NOTE]
>
>As chamadas de retorno não funcionam como seleções (ou seja, não afetam outras visualizações no espaço de trabalho) a menos que você faça uma seleção na chamada de saída.

Você pode adicionar ou editar definições de chamada configurando os arquivos de chamada armazenados na pasta de instalação *profile name*\Context\Callout folder of the [!DNL Server]. Consulte [Configuração de chamadas de retorno](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-callouts.md#concept-f6e91e172f5e4c009245c9c549beb76a).

## Para adicionar uma chamada de anotação a uma visualização {#section-7b6742160b3f4aed872a09c8c023f90d}

1. Clique com o botão direito do mouse no elemento para o qual deseja criar uma chamada e depois clique em **[!UICONTROL Add Callout]** > **[!UICONTROL Annotation]** > **[!UICONTROL Image]** ou **[!UICONTROL Add Callout]** > **[!UICONTROL Annotation]** > **[!UICONTROL Text]**. Uma janela em branco é exibida com uma conexão visível a esse elemento.

   ![](assets/client-call.png)

   Para adicionar chamadas às visualizações de gráfico, é necessário clicar com o botão direito do mouse na parte inferior da visualização (o eixo base) para abrir um menu.

   ![](assets/visualization_callout_linegraph.png)

1. Dependendo da sua seleção, conclua a etapa apropriada:

   * Para uma anotação de texto, digite ou cole o texto desejado na chamada e, em seguida, formate o texto conforme apropriado. Consulte [Trabalhar com anotações de texto](../../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777).
   * Para uma anotação de imagem, cole a imagem desejada na chamada copiando a imagem e clicando com o botão direito do mouse na chamada. Clique em **[!UICONTROL Paste image]**. Consulte [Trabalhar com anotações de imagem](../../../home/c-get-started/c-analysis-vis/c-annots/c-image-annots.md#concept-02081ed7d91c4fdcb8fc863f2a51c962).

## Para adicionar uma tabela, gráfico de linha ou chamada de gráfico de dispersão em branco a uma visualização {#section-5dcc0504bdb64ed4976f880e2f7b277f}

1. Clique com o botão direito do mouse no elemento para o qual deseja criar uma chamada e clique em **[!UICONTROL Add Callout]** > *&lt;**[!UICONTROL callout type]**>*.

   O exemplo a seguir mostra uma chamada de Tabela em branco.

   ![](assets/vis_callout_blank_bar_graph.png)

1. Para selecionar uma dimensão, clique com o botão direito do mouse **[!UICONTROL None]** e clique em **[!UICONTROL Change Dimension]** > *&lt;**[!UICONTROL dimension name]**>*.

   >[!NOTE]
   >
   >Se você alterar a dimensão em uma visualização que tenha uma chamada , a chamada mudará de estar conectada ao elemento da dimensão original para estar conectada a toda a visualização.

## Para adicionar uma chamada de legenda de confiança a uma visualização {#section-386d1293ddc24a0c9cccb332e20db791}

1. Clique com o botão direito do mouse no elemento para o qual deseja criar a chamada e clique em **[!UICONTROL Add Callout]** > **[!UICONTROL Confidence Legend]**.

   ![](assets/vis_callout_confidenceLegend.png)

1. Se desejar, altere o campo [!DNL Metric or Formula].

Para obter as regras da sintaxe da expressão, consulte [Sintaxe da linguagem de consulta](../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f). Consulte [Legendas de confiança](../../../home/c-get-started/c-analysis-vis/c-legends/c-conf-leg.md#concept-73db81c2c218427786c04068aa778efd).

## Para adicionar uma chamada de legenda de métrica a uma visualização {#section-daa6d372c22246d9827880a9d6e804d8}

1. Clique com o botão direito do mouse no elemento para o qual deseja criar a chamada e clique em **[!UICONTROL Add Callout]** > **[!UICONTROL Metric Legend]**.

   ![](assets/vis_callout_metricLegend.png)

1. Se desejar, adicione ou remova métricas da legenda da métrica.

Consulte [Legendas de métrica](../../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b).
