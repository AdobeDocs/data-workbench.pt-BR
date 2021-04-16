---
description: Ao exibir componentes do conjunto de dados em um mapa de dependência, você tem a opção de ativar a opção de exibição Incluir blocos de arquivo .
title: Blocos de arquivo
uuid: 079dccba-ef19-4895-90bb-6c56f26e8beb
exl-id: 04b0faf1-a16d-4e46-b790-5fe2023f2ba1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 1%

---

# Blocos de arquivo{#file-blocks}

Ao exibir componentes do conjunto de dados em um mapa de dependência, você tem a opção de ativar a opção de exibição Incluir blocos de arquivo .

Quando essa opção é ativada, o mapa exibe um único nó azul para todas as transformações definidas em um arquivo de configuração de conjunto de dados e um único nó verde para todas as dimensões estendidas definidas em um arquivo de configuração de conjunto de dados. Por exemplo, se um arquivo [!DNL log processing dataset include] incluir as definições de três transformações, o mapa exibirá um nó azul representando as três transformações. Da mesma forma, se um arquivo [!DNL transformation dataset include] incluir as definições de duas dimensões estendidas, o mapa exibirá um nó verde representando as duas dimensões estendidas.

## Blocos de transformação {#section-c442730394264a0b850792a32eaaa2da}

Cada nó azul é um bloco de transformação e tem as seguintes opções:

* Para exibir os campos de entrada do bloco de transformação, clique com o botão direito do mouse no nó do bloco e clique em **[!UICONTROL Inputs]**.
* Para exibir os campos de saída do bloco de transformação, clique com o botão direito do mouse no nó do bloco e clique em **[!UICONTROL Outputs]**.
* Para editar qualquer transformação no bloco, clique com o botão direito do mouse no nó do bloco e clique em **[!UICONTROL Edit Configuration]**. A chamada exibida contém todo o arquivo de configuração em que todas as transformações são definidas. Em seguida, é possível editar os parâmetros conforme desejado. Para obter mais informações sobre esses parâmetros, consulte o *Guia de Configuração de Conjunto de Dados*.

* Para ver todas as transformações no bloco , clique com o botão direito do mouse no nó do bloco de transformação e clique em **[!UICONTROL Show Details]**. A chamada exibida contém outro mapa de dependência mostrando nós para todas as transformações no bloco.

## Dimension blocks {#section-0dd581ac6dfc4153bee5300b3cfae2a0}

Cada nó verde é um bloco de dimensão e tem as seguintes opções:

* Para exibir os campos de entrada ou a dimensão pai do bloco de dimensão, clique com o botão direito do mouse no nó do bloco e clique em **[!UICONTROL Inputs]**.
* Para exibir as dimensões de saída do bloco de dimensão, clique com o botão direito do mouse no nó do bloco e clique em **[!UICONTROL Outputs]**.
