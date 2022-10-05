---
description: Informações para gerar relatórios como arquivos Excel.
title: Gerar relatórios como arquivos do Microsoft Excel
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
exl-id: 4e644867-db5e-4ca9-a2bf-1193e031f2bf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 4%

---

# Gerar relatórios como arquivos do Microsoft Excel{#generating-reports-as-microsoft-excel-files}

{{eol}}

Informações para gerar relatórios como arquivos Excel.

Os seguintes requisitos devem ser atendidos:

* O Microsoft Excel deve ser instalado na mesma máquina que [!DNL Report Server].
* A conta de usuário na qual a variável [!DNL Report Server] O processo em execução deve ter permissão para acessar o Microsoft Excel.

   >[!NOTE]
   >
   >
   >
   >
   >    * Ao gerar relatórios como arquivos do Excel, você está abrindo uma nova instância do Excel. Para obter mais informações sobre esse processo, consulte [https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757).
   >    * Embora o Data Workbench seja compatível com mais de 256 colunas e 65.536 linhas de dados, o Microsoft Excel não oferece.


Se esses requisitos forem atendidos, [!DNL Report Server] O inicia automaticamente o Microsoft Excel e os dados de saída de determinadas visualizações, legendas de dimensão e valor e anotações de texto em uma nova pasta de trabalho do Excel com uma visualização por planilha.

>[!NOTE]
>
>Os dados não são exportados de gráficos, navegadores de caminhos, mapas de processos, gráficos de dispersão e globos.

A menos que você tenha especificado um [!DNL Custom Title] para a visualização, o tipo de janela (por exemplo, Tabela de filmes) é usado como o nome da planilha.

Para obter mais informações sobre especificação [!DNL Custom Titles] para visualizar, consulte a [Guia do cliente do Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html?lang=pt-BR).

## Usando um arquivo de modelo {#section-40ab11916f464b1a88214ab969da6751}

Também é possível gerar um relatório como um arquivo Excel usando um Excel de modelo ( [!DNL .xls] ou [!DNL .xlsx]). O uso de um arquivo de modelo pode reduzir o tempo gasto com a formatação dos dados toda vez que o relatório é gerado.

Esse arquivo de modelo deve ser um [!DNL .xls] ou [!DNL .xlsx] arquivo, não um [!DNL .xlt] arquivo.

Você pode optar por definir um modelo para cada relatório individual, um modelo genérico para todos os relatórios ou uma combinação dos dois. Esses dois itens não são mutuamente exclusivos, portanto, é possível definir um modelo genérico e também definir modelos específicos.

Para gerar um relatório usando um modelo genérico usado para todos os relatórios, você deve especificar o nome desse arquivo do Excel no parâmetro Modelo do Excel padrão na [!DNL Report.cfg] para esse arquivo de conjunto de relatórios, coloque o arquivo de modelo na mesma pasta de [!DNL Report.cfg] para esse conjunto de relatórios (*diretório de instalação do data workbench*\*Nome do perfil*\Relatórios\*Nome do conjunto de relatórios*). Para obter informações sobre esse parâmetro, consulte [Parâmetros do Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

Para gerar um relatório usando um modelo específico de relatório, é necessário nomear o arquivo Excel como o espaço de trabalho do relatório ( [!DNL .vw]), em seguida, coloque o arquivo de modelo na mesma pasta do espaço de trabalho do relatório ( [!DNL .vw]).

Quando o relatório é gerado, as planilhas com guias existentes no modelo (cada uma representando uma visualização) são preenchidas novamente com os dados mais recentes do relatório, enquanto qualquer janela nova que não esteja presente no modelo como planilhas com guias é ignorada. Quaisquer outras folhas de guias no arquivo de modelo permanecem inalteradas.

Além disso, se você tiver uma macro definida no arquivo Excel de modelo que gostaria de executar automaticamente quando o relatório for gerado, nomeie a macro como &quot;VSExport&quot;.
