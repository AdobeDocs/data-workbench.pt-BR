---
description: Você pode exportar um espaço de trabalho como um arquivo de imagem .png ou exportar os dados de determinadas janelas para um arquivo Excel (.xls ou .xlsx).
solution: Analytics
title: Exportar um espaço de trabalho
topic: Data workbench
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exportar um espaço de trabalho{#export-a-workspace}

Você pode exportar um espaço de trabalho como um arquivo de imagem .png ou exportar os dados de determinadas janelas para um arquivo Excel (.xls ou .xlsx).

## Exportar espaços de trabalho como um arquivo PNG {#section-f9fbe0f0a1c341e2b063cce106cac35e}

É possível salvar um instantâneo de um espaço de trabalho no formato Portable Network Graphic (`.png` arquivos). As seguintes opções de cores estão disponíveis ao salvar espaços de trabalho como `.png` arquivos:

* **O plano de fundo** preto copia o espaço de trabalho como exibido.
* **O plano de fundo** branco copia os elementos do espaço de trabalho em cores e os exibe em um plano de fundo branco.
* **O plano de fundo branco (P&amp;B)** copia os elementos do espaço de trabalho em tons de cinza e os exibe em um plano de fundo branco.

**Para exportar um espaço de trabalho como um arquivo .png**

No menu da barra de título de um espaço de trabalho, clique em **[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > *&lt;**[!UICONTROL color option]**>*.

A caixa [!UICONTROL Save Image As] de diálogo é exibida.

Navegue até o diretório em que deseja salvar o arquivo, altere o nome do arquivo, se necessário, e clique em **[!UICONTROL Save]**.

## Exportar dados do espaço de trabalho para o Microsoft Excel {#section-fe214e3dbc364d2eba3834d62d295acb}

Ao exportar um espaço de trabalho para o Excel, o Análise de big data exporta dados de determinadas visualizações, legendas de dimensão e valor e anotações em texto para uma nova pasta de trabalho do Excel com uma visualização por planilha.

Para exportar espaços de trabalho e janelas individuais para o Microsoft Excel, os seguintes requisitos devem ser atendidos:

* O Microsoft Excel deve ser instalado no mesmo computador que o Análise de big data.
* A conta de usuário na qual o processo da Análise de big data está em execução deve ter permissão para acessar o Microsoft Excel.

>[!NOTE]
>
>* Ao exportar dados como arquivos do Excel, você está abrindo uma nova instância do Excel. Para obter mais informações sobre esse processo, consulte [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).
>* Embora a Análise de big data ofereça suporte para mais de 256 colunas e 65.536 linhas de dados, as versões do Microsoft Excel anteriores à versão 8.0 não oferecem suporte.
>



Se esses requisitos forem atendidos, o Análise de big data inicia automaticamente o Microsoft Excel e exporta os dados para uma nova pasta de trabalho do Excel. Os dados não são exportados das seguintes visualizações: gráficos, navegadores de caminho, mapas de processo, gráficos de dispersão e globes.

## Aplicar títulos personalizados {#section-a332e157554546cb8e88922a8d7a4fa2}

A menos que você tenha especificado um título Personalizado para a janela no [!UICONTROL Export] menu, a tabela [!UICONTROL Export title] listada (por exemplo, Tabela da cidade) será usada como o nome da planilha.

1. Clique com o botão direito do mouse na borda superior da janela e clique no **[!UICONTROL Custom title]** campo.
1. Digite o título que deseja aplicar à janela.

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>Se você inserir um hífen (-) no [!UICONTROL Custom title] campo, essa visualização não será exportada com o espaço de trabalho.

Quando você exporta o espaço de trabalho para o Excel, a planilha que contém os dados para essa janela é nomeada usando o título especificado em vez do título no [!UICONTROL Export title] campo.

## Exportar um espaço de trabalho ou barra lateral para o Excel {#section-360438b66d5f4734826ab463b4a01a75}

**Para exportar dados do espaço de trabalho para um novo[!DNL .xls]ou[!DNL .xlsx]arquivo**

1. Na barra de título do espaço de trabalho, clique em **[!UICONTROL Export]** > **[!UICONTROL Export]**.
1. Especifique se deseja exportar o espaço de trabalho, a barra lateral ou ambos.

## Exportar para um arquivo Excel de modelo {#section-814772929ca64cf6b92b89d3fdd02302}

Você pode exportar dados em seu espaço de trabalho para um arquivo Excel de modelo (`.xls` ou `.xlsx`). O uso de um arquivo de modelo pode reduzir a quantidade de tempo que você gasta formatando seus dados toda vez que o espaço de trabalho é exportado.

>[!NOTE]
>
>Este arquivo de modelo deve ser um arquivo `.xls` ou `.xlsx` , não um `.xlt` arquivo.

Quando os dados são exportados, as planilhas com guias existentes no modelo (cada uma representando uma visualização) são preenchidas novamente com os dados mais recentes do espaço de trabalho, enquanto qualquer nova janela que não esteja presente no modelo como planilhas com guias é ignorada. Quaisquer outras folhas com guias no arquivo de modelo permanecerão inalteradas.

Além disso, se você tiver uma macro definida no arquivo Excel de modelo que você gostaria de executar automaticamente quando o relatório for gerado, nomeie a macro &quot;Exportar&quot;.

Considere que você deseja usar os dados de campanha exportados de uma visualização de tabela em um gráfico de pizza em outra planilha com guias em um arquivo Excel e deseja atualizar essas informações toda semana. Você pode usar um modelo para não precisar recriar suas referências da planilha com guias da tabela para a planilha com guias do gráfico de pizza sempre que desejar atualizar os dados. Os dados da tabela são atualizados após a exportação, o que atualiza automaticamente o gráfico de pizza.

**Para exportar dados do espaço de trabalho para um modelo[!DNL .xls]ou[!DNL .xlsx]arquivo**

1. Clique com o botão direito do mouse na barra de título da área de trabalho e clique em **[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]**.
1. Especifique se deseja exportar um espaço de trabalho, uma barra lateral ou ambos.

   A caixa [!UICONTROL Select a template worksheet] de diálogo é aberta.

1. Conclua uma das seguintes etapas, conforme apropriado:

   * Se você estiver usando um arquivo de `.xls` modelo:

      1. Procure e selecione o `.xls` arquivo de modelo.
      1. Clique em **[!UICONTROL Open]**.
   * Se você estiver usando um arquivo de `.xlsx` modelo:

      1. Navegue até o local do arquivo de modelo. O nome do `.xlsx` arquivo não é exibido.
      1. No [!UICONTROL File name] campo, digite `.xlsx` e clique em **[!UICONTROL Open]**. Todos os nomes de `.xlsx` arquivos são exibidos na lista de arquivos.

      1. Selecione o `.xlsx` arquivo de modelo.
      1. Clique em **[!UICONTROL Open]**.


