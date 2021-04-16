---
description: Você pode exportar um espaço de trabalho como um arquivo de imagem .png ou exportar os dados de determinadas janelas para um arquivo Excel (.xls ou .xlsx).
title: Exportar um espaço de trabalho
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
exl-id: 87416ddf-2ac0-4f95-ae8e-71051061c757
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 1%

---

# Exportar um espaço de trabalho{#export-a-workspace}

Você pode exportar um espaço de trabalho como um arquivo de imagem .png ou exportar os dados de determinadas janelas para um arquivo Excel (.xls ou .xlsx).

## Exportar espaços de trabalho como um arquivo PNG {#section-f9fbe0f0a1c341e2b063cce106cac35e}

Você pode salvar um instantâneo de um espaço de trabalho no formato Portable Network Graphic (arquivos `.png`). As seguintes opções de cor estão disponíveis ao salvar espaços de trabalho como arquivos `.png`:

* **O** fundo preto copia o espaço de trabalho como exibido.
* **O** fundo branco copia os elementos do espaço de trabalho em cores e os exibe em um plano de fundo branco.
* **O plano de fundo branco (B&amp;W)**  copia os elementos do espaço de trabalho em escala de cinza e os exibe em um plano de fundo branco.

**Para exportar um espaço de trabalho como um arquivo .png**

No menu da barra de título de um espaço de trabalho, clique em **[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > *&lt;**[!UICONTROL color option]**>*.

A caixa de diálogo [!UICONTROL Save Image As] é exibida.

Navegue até o diretório em que deseja salvar o arquivo, altere o nome do arquivo, se necessário, e clique em **[!UICONTROL Save]**.

## Exportar dados do espaço de trabalho para o Microsoft Excel {#section-fe214e3dbc364d2eba3834d62d295acb}

Ao exportar um espaço de trabalho para o Excel, o Data Workbench exporta dados de determinadas visualizações, legendas de dimensão e valor e anotações de texto para uma nova pasta de trabalho do Excel com uma visualização por planilha.

Para exportar espaços de trabalho e janelas individuais para o Microsoft Excel, os seguintes requisitos devem ser atendidos:

* O Microsoft Excel deve ser instalado na mesma máquina que o Data Workbench.
* A conta de usuário na qual o processo de Data Workbench está em execução deve ter permissão para acessar o Microsoft Excel.

>[!NOTE]
>
>* Ao exportar dados como arquivos do Excel, você está abrindo uma nova instância do Excel. Para obter mais informações sobre esse processo, consulte [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).
>* Embora o Data Workbench seja compatível com mais de 256 colunas e 65.536 linhas de dados, as versões do Microsoft Excel anteriores ao 8.0 não são compatíveis.
>



Se esses requisitos forem atendidos, o Data Workbench inicia automaticamente o Microsoft Excel e exporta os dados para uma nova pasta de trabalho do Excel. Os dados não são exportados das seguintes visualizações: gráficos, navegadores de caminhos, mapas de processos, gráficos de dispersão e globos.

## Aplicar títulos personalizados {#section-a332e157554546cb8e88922a8d7a4fa2}

A menos que você tenha especificado um título Personalizado para a janela no menu [!UICONTROL Export], o [!UICONTROL Export title] listado (por exemplo, Tabela de Cidade) é usado como o nome da planilha.

1. Clique com o botão direito do mouse na borda superior da janela e clique no campo **[!UICONTROL Custom title]**.
1. Digite o título que deseja aplicar à janela.

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>Se você inserir um hífen (-) no campo [!UICONTROL Custom title], essa visualização não será exportada com o espaço de trabalho.

Quando você exporta o espaço de trabalho para o Excel, a planilha que contém os dados desta janela é nomeada usando o título especificado em vez do título no campo [!UICONTROL Export title].

## Exportar um espaço de trabalho ou barra lateral para o Excel {#section-360438b66d5f4734826ab463b4a01a75}

**Para exportar dados do espaço de trabalho para um novo  [!DNL .xls] ou  [!DNL .xlsx] arquivo**

1. Na barra de título do espaço de trabalho, clique em **[!UICONTROL Export]** > **[!UICONTROL Export]**.
1. Especifique se deseja exportar o espaço de trabalho, a barra lateral ou ambos.

## Exportar para um arquivo Excel de modelo {#section-814772929ca64cf6b92b89d3fdd02302}

Você pode exportar dados em seu espaço de trabalho para um arquivo Excel de modelo (`.xls` ou `.xlsx`). Usar um arquivo de modelo pode reduzir o tempo gasto com a formatação dos dados toda vez que o espaço de trabalho for exportado.

>[!NOTE]
>
>Esse arquivo de modelo deve ser um arquivo `.xls` ou `.xlsx`, não um arquivo `.xlt`.

Quando os dados são exportados, as planilhas com guias existentes no modelo (cada uma representando uma visualização) são preenchidas novamente com os dados mais recentes do espaço de trabalho, enquanto qualquer nova janela que não esteja presente no modelo como planilhas com guias é ignorada. Quaisquer outras folhas de guias no arquivo de modelo permanecem inalteradas.

Além disso, se você tiver uma macro definida no arquivo Excel de modelo que gostaria de executar automaticamente quando o relatório for gerado, nomeie a macro como &quot;VSExport&quot;.

Digamos que você queira usar os dados de campanha exportados de uma visualização de tabela em um gráfico de pizza em outra planilha com guias em um arquivo Excel e deseja atualizar essas informações toda semana. Você pode usar um modelo para não precisar recriar suas referências da planilha com guias da tabela na planilha com guias do gráfico de pizza sempre que quiser atualizar os dados. Os dados da tabela são atualizados após a exportação, o que atualiza automaticamente o gráfico de pizza.

**Para exportar dados do espaço de trabalho para um modelo  [!DNL .xls] ou  [!DNL .xlsx] arquivo**

1. Clique com o botão direito do mouse na barra de título do espaço de trabalho e clique em **[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]**.
1. Especifique se deseja exportar um espaço de trabalho, uma barra lateral ou ambos.

   A caixa de diálogo [!UICONTROL Select a template worksheet] é aberta.

1. Conclua uma das seguintes etapas, conforme necessário:

   * Se estiver usando um arquivo de modelo `.xls`:

      1. Procure e selecione o arquivo de modelo `.xls` .
      1. Clique em **[!UICONTROL Open]**.
   * Se estiver usando um arquivo de modelo `.xlsx`:

      1. Navegue até o local do arquivo de modelo. O nome do arquivo `.xlsx` não é exibido.
      1. No campo [!UICONTROL File name], digite `.xlsx` e clique em **[!UICONTROL Open]**. Todos os nomes de arquivo `.xlsx` são exibidos na lista de arquivos.

      1. Selecione o arquivo de modelo `.xlsx` .
      1. Clique em **[!UICONTROL Open]**.
