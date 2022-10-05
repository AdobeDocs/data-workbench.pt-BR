---
description: É possível exportar os dados em determinadas janelas para um arquivo Excel (.xls ou .xlsx) ou para um arquivo de valores separados por tabulação (.tsv).
title: Exportar dados da janela
uuid: 71a93f35-1096-41ae-8808-e5b94813a52c
exl-id: ab931453-d366-4d3a-990e-7a368328da2d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 2%

---

# Exportar dados da janela{#export-window-data}

{{eol}}

É possível exportar os dados em determinadas janelas para um arquivo Excel (.xls ou .xlsx) ou para um arquivo de valores separados por tabulação (.tsv).

Os dados não são exportados de gráficos, navegadores de caminhos, mapas de processos, gráficos de dispersão e globos.

## Exportar dados da janela para o Microsoft Excel {#section-b660adf7f4f64a2b9be7287c591b67b0}

Para exportar dados de janela individuais para o Microsoft Excel, os seguintes requisitos devem ser atendidos:

* O Microsoft Excel deve ser instalado na mesma máquina que o Data Workbench.
* A conta de usuário na qual o processo de Data Workbench está em execução deve ter permissão para acessar o Microsoft Excel.
* Ao exportar dados como arquivos do Excel, você está abrindo uma nova instância do Excel.
* Embora o Data Workbench seja compatível com mais de 256 colunas e 65.536 linhas de dados, as versões do Microsoft Excel anteriores ao 8.0 não são compatíveis.

Se esses requisitos forem atendidos, o Data Workbench inicia automaticamente o Microsoft Excel e exporta os dados para uma nova pasta de trabalho do Excel quando você seleciona a variável **[!UICONTROL Export To Excel]** opção de menu.

**Para exportar dados da janela para um arquivo .xls ou .xlsx**

Clique com o botão direito do mouse na borda superior da janela e clique em **[!UICONTROL Export]** > **[!UICONTROL Export to Excel]**.

![](assets/mnu_window_TitleBar_Export.png)

O Excel abre uma nova pasta de trabalho contendo os dados exportados. A menos que você tenha fornecido um título Personalizado (conforme descrito na seção a seguir), essa pasta de trabalho será nomeada usando o [!DNL Export title] (Tabela de dias no exemplo acima).

## Aplicar títulos personalizados {#section-2a6559df812a470685e43923b7b9024e}

Se você fornecer um título personalizado para uma janela (usando o [!DNL Custom title] no campo [!DNL Export] ) a planilha para a qual o Data Workbench exporta os dados é nomeada usando este título personalizado em vez do título na [!DNL Export title] (Tabela de dias no exemplo acima).

**Para aplicar um título personalizado a uma visualização**

1. Clique com o botão direito do mouse na borda superior da janela e clique em no **[!UICONTROL Custom title]** campo.
1. you

![](assets/mnu_window_TitleBar_Export.png)

Quando você exporta a visualização para o Excel, a planilha que contém os dados desta janela é nomeada usando o título que você especificou em vez do título na [!DNL Export title] campo.

## Exportar dados da janela para um arquivo TSV {#section-93c6b24f7338430aaf5a63b99b9489e8}

**Para exportar uma janela para um arquivo .tsv**

Clique com o botão direito do mouse na borda superior da janela e clique em **[!UICONTROL Export]** > **[!UICONTROL Export TSV]**.

1. A caixa de diálogo [!DNL Save Window] é exibida.
1. Navegue até o diretório em que deseja salvar o arquivo. Altere o nome do arquivo, se necessário, e clique em **[!UICONTROL Save]**.
