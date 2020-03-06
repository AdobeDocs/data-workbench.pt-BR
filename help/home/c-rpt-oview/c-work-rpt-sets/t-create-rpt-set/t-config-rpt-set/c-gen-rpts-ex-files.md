---
description: Informações para gerar relatórios como arquivos do Excel.
solution: Analytics
title: Gerando Relatórios como Arquivos do Microsoft Excel
topic: Data workbench
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Gerando Relatórios como Arquivos do Microsoft Excel{#generating-reports-as-microsoft-excel-files}

Informações para gerar relatórios como arquivos do Excel.

Devem ser cumpridos os seguintes requisitos:

* O Microsoft Excel deve ser instalado no mesmo computador [!DNL Report Server].
* A conta de usuário na qual o [!DNL Report Server] processo está sendo executado deve ter permissão para acessar o Microsoft Excel.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Ao gerar relatórios como arquivos do Excel, você está abrindo uma nova instância do Excel. Para obter mais informações sobre esse processo, consulte [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).
   >    * Embora a análise de big data suporte mais de 256 colunas e 65.536 linhas de dados, o Microsoft Excel não oferece suporte.


Se esses requisitos forem atendidos, o Microsoft Excel será iniciado [!DNL Report Server] automaticamente e os dados de saída de determinadas visualizações, legendas de dimensão e valor e anotações de texto em uma nova pasta de trabalho do Excel com uma visualização por planilha.

>[!NOTE]
>
>Os dados não são exportados de gráficos, navegadores de caminho, mapas de processo, gráficos de dispersão e globais.

A menos que você tenha especificado um valor [!DNL Custom Title] para a visualização, o tipo de janela (por exemplo, Tabela de filme) será usado como o nome da planilha.

Para obter mais informações sobre como especificar [!DNL Custom Titles] para visualizações, consulte o Guia [do cliente da Análise de](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html)big data.

## Usando um Arquivo de Modelo {#section-40ab11916f464b1a88214ab969da6751}

Você também pode gerar um relatório como um arquivo Excel usando um arquivo Excel de modelo ( [!DNL .xls] ou [!DNL .xlsx]). O uso de um arquivo de modelo pode reduzir o tempo que você gasta formatando seus dados toda vez que o relatório é gerado.

Este arquivo de modelo deve ser um arquivo [!DNL .xls] ou [!DNL .xlsx] , não um [!DNL .xlt] arquivo.

Você pode optar por definir um modelo para cada relatório individual, um modelo genérico para todos os relatórios ou uma combinação de ambos. Esses dois itens não são mutuamente exclusivos, portanto, você pode definir um modelo genérico e, em seguida, definir modelos específicos também.

Para gerar um relatório usando um modelo genérico que você usa para todos os relatórios, você deve especificar o nome desse arquivo Excel no parâmetro Modelo padrão do Excel no arquivo [!DNL Report.cfg] para esse conjunto de relatórios e, em seguida, colocar o arquivo de modelo na mesma pasta do conjunto de relatórios [!DNL Report.cfg] (diretório ** de instalação da análise de big data\*ProfileName*\Reports\*ReportSetName*). Para obter informações sobre esse parâmetro, consulte Parâmetros [](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)Report.cfg.

Para gerar um relatório usando um modelo que seja específico de um relatório, é necessário nomear o arquivo do Excel como o arquivo da área de trabalho do relatório ( [!DNL .vw]) e, em seguida, colocar o arquivo de modelo na mesma pasta que o arquivo da área de trabalho do relatório ( [!DNL .vw]).

Quando o relatório é gerado, as planilhas com guias existentes no modelo (cada uma representando uma visualização) são preenchidas novamente com os dados mais recentes do relatório, enquanto quaisquer janelas novas que não estejam presentes no modelo como planilhas com guias são ignoradas. Quaisquer outras folhas com guias no arquivo de modelo permanecerão inalteradas.

Além disso, se você tiver uma macro definida no arquivo Excel de modelo que você gostaria de executar automaticamente quando o relatório for gerado, nomeie a macro &quot;Exportar&quot;.
