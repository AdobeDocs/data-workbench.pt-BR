---
description: Gere relatórios processando espaços de trabalho e especificando-os como relatórios.
title: Gerar relatórios
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 9%

---

# Gerar relatórios{#generating-reports}

Gere relatórios processando espaços de trabalho e especificando-os como relatórios.

[!DNL Report] O gera seus relatórios no intervalo definido no  [!DNL Every] parâmetro no  [!DNL Report.cfg] arquivo (como  [!DNL "day],&quot; que processa o relatório diariamente) e com base nas outras configurações  [!DNL Report.cfg] de arquivo.

Ao gerar relatórios, a porcentagem completa é exibida na guia [!DNL Reports] na miniatura desse relatório específico. Se [!DNL Report] encontrar um problema durante a geração do relatório, a mensagem de erro mais recente será exibida na guia [!DNL Reports] na pasta do conjunto de relatórios. Se [!DNL Report] encontrar um erro para um relatório específico, ele continuará a processar os outros relatórios no conjunto.

Você pode gerar os relatórios em um conjunto de relatórios em qualquer um ou em todos os formatos a seguir usando o parâmetro [!DNL Report Types] no arquivo [!DNL Report.cfg]:

* Arquivo do Microsoft Excel ( [!DNL .xls] ou [!DNL .xlsx])
* Arquivo gráfico de rede portátil ( [!DNL .png])
* Miniatura ( [!DNL .jpg])

Juntamente com os tipos de saída especificados, [!DNL Report] cria um arquivo [!DNL .xml] com o mesmo nome do relatório. Este arquivo *`<report name>`*.xml contém a descrição do relatório que é exibida em Data Workbench na guia [!DNL Reports] abaixo da miniatura do relatório. Isso torna a descrição disponível para uso ao distribuir seus relatórios por meio de um portal de relatórios. Para obter informações sobre o [!DNL Report Portal], consulte [Trabalhar com o portal de relatórios](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Se você redefinir uma métrica interna, o sistema se comporta inesperadamente por causa do valor errado. Os relatórios não serão gerados a menos que uma métrica leia 100%. É recomendável não alterar as definições de métricas.
