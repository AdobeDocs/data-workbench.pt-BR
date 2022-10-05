---
description: Após a geração dos relatórios, o relatório distribui os relatórios no conjunto com base nas configurações em seu arquivo Report.cfg .
title: Distribuir relatórios
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
exl-id: ead1d8ef-7319-4307-9155-0101a9c1959d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# Distribuir relatórios{#distributing-reports}

{{eol}}

Após a geração dos relatórios, o relatório distribui os relatórios no conjunto com base nas configurações em seu arquivo Report.cfg .

[!DNL Report] O permite distribuir os relatórios em um conjunto usando os seguintes métodos:

* **Email:** Para distribuir relatórios como arquivos do Excel, [!DNL .png] arquivos ou miniaturas por email (em linha ou como anexos), especifique os parâmetros do Relatório de email no relatório de [!DNL Report.cfg] arquivo. Todos os relatórios nesse conjunto são enviados por email em uma mensagem para os recipients especificados.

* **Diretório compartilhado:** Para distribuir relatórios como arquivos do Excel, [!DNL .png] arquivos, ou miniaturas em um diretório compartilhado, especifique o diretório no parâmetro Raiz de saída no conjunto de relatórios [!DNL Report.cfg] arquivo.

* **Portal de relatórios:** Um portal de relatórios permite exibir relatórios por meio do navegador da Web. Adobe&#39;s [!DNL Report Portal] exibe relatórios gerados como Excel ou [!DNL .png] arquivos, mas não aqueles gerados como miniaturas ( [!DNL .jpg]). Para distribuir relatórios em um portal, especifique a raiz do documento do servidor da Web usado para o portal no parâmetro Raiz de saída do conjunto de relatórios [!DNL Report.cfg] arquivo. Para obter mais informações sobre como instalar e usar [!DNL Report Portal], consulte [Trabalhar com o portal de relatórios](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Para ler a saída atualmente suportada pelo [!DNL Report], você deve ter um aplicativo capaz de exibir os relatórios no formato desejado. Por exemplo, para exibir [!DNL .xlsx] arquivos, você deve ter o Microsoft Excel 2007 ou posterior.

Também é possível usar uma combinação dessas opções de geração e distribuição. Por exemplo, se você definir a variável [!DNL Report Types] para gerar um conjunto de relatórios como Excel e [!DNL .png] e, em seguida, defina o [!DNL Mail Report]e [!DNL Output Root] , todos os relatórios nesse conjunto são distribuídos para o diretório de saída especificado (talvez para ser exibido em um portal) e enviados por email para os recipients.

Para obter etapas para configurar seus conjuntos de relatórios, consulte [Trabalhar com conjuntos de relatórios](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5). Para obter mais informações sobre [!DNL Report.cfg] parâmetros, consulte [Parâmetros do Report.cfg](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
