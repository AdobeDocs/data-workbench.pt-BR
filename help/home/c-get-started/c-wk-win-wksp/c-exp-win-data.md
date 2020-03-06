---
description: É possível exportar os dados em determinadas janelas para um arquivo do Excel (.xls ou .xlsx) ou para um arquivo de valores separados por tabulação (.tsv).
solution: Analytics
title: Exportar dados da janela
topic: Data workbench
uuid: 71a93f35-1096-41ae-8808-e5b94813a52c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exportar dados da janela{#export-window-data}

É possível exportar os dados em determinadas janelas para um arquivo do Excel (.xls ou .xlsx) ou para um arquivo de valores separados por tabulação (.tsv).

Os dados não são exportados de gráficos, navegadores de caminho, mapas de processo, gráficos de dispersão e globais.

## Exportar dados da janela para o Microsoft Excel {#section-b660adf7f4f64a2b9be7287c591b67b0}

Para exportar dados de janela individuais para o Microsoft Excel, os seguintes requisitos devem ser atendidos:

* O Microsoft Excel deve ser instalado no mesmo computador que o Análise de big data.
* A conta de usuário na qual o processo da Análise de big data está em execução deve ter permissão para acessar o Microsoft Excel.
* Ao exportar dados como arquivos do Excel, você está abrindo uma nova instância do Excel.
* Embora a Análise de big data ofereça suporte para mais de 256 colunas e 65.536 linhas de dados, as versões do Microsoft Excel anteriores à versão 8.0 não oferecem suporte.

Se esses requisitos forem atendidos, o Análise de big data inicia automaticamente o Microsoft Excel e exporta os dados para uma nova pasta de trabalho do Excel quando você seleciona a opção de **[!UICONTROL Export To Excel]** menu.

**Para exportar dados da janela para um arquivo .xls ou .xlsx**

Clique com o botão direito do mouse na borda superior da janela e clique em **[!UICONTROL Export]** > **[!UICONTROL Export to Excel]**.

![](assets/mnu_window_TitleBar_Export.png)

O Excel abre uma nova pasta de trabalho contendo os dados exportados. A menos que você tenha fornecido um título Personalizado (conforme descrito na seção a seguir), essa pasta de trabalho será nomeada usando o [!DNL Export title] (Tabela de dias no exemplo acima).

## Aplicar títulos personalizados {#section-2a6559df812a470685e43923b7b9024e}

Se você fornecer um título personalizado para uma janela (usando o [!DNL Custom title] campo no [!DNL Export] menu), a planilha para a qual o Análise de big data exporta os dados será nomeada usando esse título personalizado em vez do título no [!DNL Export title] campo (Tabela de dias no exemplo acima).

**Para aplicar um título personalizado a uma visualização**

1. Clique com o botão direito do mouse na borda superior da janela e clique no **[!UICONTROL Custom title]** campo.
1. you

![](assets/mnu_window_TitleBar_Export.png)

Quando você exporta a visualização para o Excel, a planilha que contém os dados para essa janela é nomeada usando o título especificado em vez do título no [!DNL Export title] campo.

## Exportar dados de janela para um arquivo TSV {#section-93c6b24f7338430aaf5a63b99b9489e8}

**Para exportar uma janela para um arquivo .tsv**

Clique com o botão direito do mouse na borda superior da janela e clique em **[!UICONTROL Export]** > **[!UICONTROL Export TSV]**.

1. A caixa [!DNL Save Window] de diálogo é exibida.
1. Navegue até o diretório em que deseja salvar o arquivo. Altere o nome do arquivo, se necessário, e clique em **[!UICONTROL Save]**.

