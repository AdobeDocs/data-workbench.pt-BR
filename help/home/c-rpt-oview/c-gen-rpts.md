---
description: Gere relatórios processando espaços de trabalho e especificando-os como relatórios.
solution: Analytics
title: Geração de relatórios
topic: Data workbench
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Geração de relatórios{#generating-reports}

Gere relatórios processando espaços de trabalho e especificando-os como relatórios.

[!DNL Report] gera seus relatórios no intervalo definido no [!DNL Every] parâmetro no [!DNL Report.cfg] arquivo (como [!DNL "day]&quot;, que processa o relatório diariamente) e com base nas outras configurações de [!DNL Report.cfg] arquivo.

Ao gerar relatórios, a porcentagem concluída é exibida na [!DNL Reports] guia abaixo da miniatura desse relatório específico. Se [!DNL Report] encontrar um problema durante a geração do relatório, a mensagem de erro mais recente será exibida na guia [!DNL Reports] na pasta do conjunto de relatórios. Se [!DNL Report] encontrar um erro para um determinado relatório, ele continuará a processar os outros relatórios no conjunto.

Você pode gerar os relatórios em um conjunto de relatórios em qualquer um dos seguintes formatos ou em todos eles, usando o [!DNL Report Types] parâmetro no [!DNL Report.cfg] arquivo:

* Arquivo do Microsoft Excel ( [!DNL .xls] ou [!DNL .xlsx])
* Arquivo gráfico de rede portátil ( [!DNL .png])
* Miniatura ( [!DNL .jpg])

Juntamente com os tipos de saída especificados, [!DNL Report] cria um [!DNL .xml] arquivo com o mesmo nome do seu relatório. Esse arquivo *`<report name>`*.xml contém a descrição do relatório que é exibido no Análise de big data na [!DNL Reports] guia abaixo da miniatura do relatório. Isso torna a descrição disponível para uso ao distribuir seus relatórios por meio de um portal de relatórios. Para obter informações sobre o [!DNL Report Portal], consulte [Trabalhar com o portal](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)de relatórios.

>[!NOTE]
>
>Se você redefinir uma métrica interna, o sistema se comporta inesperadamente por causa do valor errado. Seus relatórios não serão gerados a menos que uma métrica leia 100%. É recomendável que você não altere as definições de métricas.
