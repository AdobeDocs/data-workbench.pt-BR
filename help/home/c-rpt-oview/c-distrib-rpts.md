---
description: Após a geração dos relatórios, o relatório distribui os relatórios no conjunto com base nas configurações em seu arquivo Report.cfg .
title: Distribuir relatórios
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
exl-id: ead1d8ef-7319-4307-9155-0101a9c1959d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# Distribuir relatórios{#distributing-reports}

Após a geração dos relatórios, o relatório distribui os relatórios no conjunto com base nas configurações em seu arquivo Report.cfg .

[!DNL Report] O permite distribuir os relatórios em um conjunto usando os seguintes métodos:

* **Email:** Para distribuir relatórios como arquivos,  [!DNL .png] arquivos ou miniaturas do Excel por email (em linha ou como anexos), especifique os parâmetros de Relatório de email no  [!DNL Report.cfg] arquivo do conjunto de relatórios. Todos os relatórios nesse conjunto são enviados por email em uma mensagem para os recipients especificados.

* **Diretório compartilhado:** para distribuir relatórios como arquivos,  [!DNL .png] arquivos ou miniaturas do Excel para um diretório compartilhado, especifique o diretório no parâmetro Raiz de saída no  [!DNL Report.cfg] arquivo do conjunto de relatórios.

* **Portal de relatórios:** um portal de relatórios permite exibir relatórios por meio do navegador da Web. O [!DNL Report Portal] do Adobe exibe relatórios gerados como arquivos Excel ou [!DNL .png], mas não aqueles gerados como miniaturas ( [!DNL .jpg]). Para distribuir relatórios em um portal, especifique a raiz do documento do servidor da Web usado para o portal no parâmetro Raiz de saída no arquivo [!DNL Report.cfg] do conjunto de relatórios. Para obter mais informações sobre como instalar e usar [!DNL Report Portal], consulte [Trabalhar com o portal de relatórios](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Para ler a saída atualmente suportada por [!DNL Report], você deve ter um aplicativo capaz de exibir os relatórios no(s) formato(s) desejado(s). Por exemplo, para visualizar arquivos [!DNL .xlsx], você deve ter o Microsoft Excel 2007 ou posterior.

Também é possível usar uma combinação dessas opções de geração e distribuição. Por exemplo, se você definir o parâmetro [!DNL Report Types] para gerar um conjunto de relatórios como arquivos Excel e [!DNL .png] e, em seguida, definir os parâmetros [!DNL Mail Report]e [!DNL Output Root], todos os relatórios nesse conjunto serão distribuídos para o diretório de saída especificado (talvez para ser exibido em um portal) e enviados por email para os recipients.

Para obter etapas para configurar seus conjuntos de relatórios, consulte [Trabalhar com conjuntos de relatórios](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5). Para obter mais informações sobre os parâmetros específicos [!DNL Report.cfg], consulte [Parâmetros Report.cfg](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
