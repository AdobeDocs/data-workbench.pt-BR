---
description: Gere relatórios processando espaços de trabalho e especificando-os como relatórios.
title: Gerar relatórios
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 9%

---

# Gerar relatórios{#generating-reports}

{{eol}}

Gere relatórios processando espaços de trabalho e especificando-os como relatórios.

[!DNL Report] gera seus relatórios no intervalo definido na variável [!DNL Every] no [!DNL Report.cfg] (como [!DNL "day],&quot; que processa o relatório diariamente) e com base no outro [!DNL Report.cfg] configurações de arquivo.

Ao gerar relatórios, a porcentagem concluída é exibida na variável [!DNL Reports] na miniatura desse relatório específico. If [!DNL Report] encontra um problema durante a geração do relatório, a mensagem de erro mais recente é exibida no [!DNL Reports] na pasta do conjunto de relatórios. If [!DNL Report] Se encontrar um erro para um relatório específico, ele continua a processar os outros relatórios no conjunto.

Você pode gerar os relatórios em um conjunto de relatórios em qualquer um dos formatos a seguir, ou em todos eles, usando o [!DNL Report Types] no [!DNL Report.cfg] arquivo:

* Arquivo Excel do Microsoft ( [!DNL .xls] ou [!DNL .xlsx])
* Arquivo gráfico de rede portátil ( [!DNL .png])
* Miniatura ( [!DNL .jpg])

Juntamente com os tipos de saída especificados, [!DNL Report] cria um [!DNL .xml] com o mesmo nome do seu relatório. Essa *`<report name>`* O arquivo .xml contém a descrição do relatório que é exibida em Data Workbench no [!DNL Reports] abaixo da miniatura do relatório. Isso torna a descrição disponível para uso ao distribuir seus relatórios por meio de um portal de relatórios. Para obter informações sobre o [!DNL Report Portal], consulte [Trabalhar com o portal de relatórios](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Se você redefinir uma métrica interna, o sistema se comporta inesperadamente por causa do valor errado. Os relatórios não serão gerados a menos que uma métrica leia 100%. É recomendável não alterar as definições de métricas.
