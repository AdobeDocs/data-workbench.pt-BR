---
description: Após a geração dos relatórios, o Relatório distribui os relatórios no conjunto com base nas configurações em seu arquivo Report.cfg.
solution: Analytics
title: Distribuição de relatórios
topic: Data workbench
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Distribuição de relatórios{#distributing-reports}

Após a geração dos relatórios, o Relatório distribui os relatórios no conjunto com base nas configurações em seu arquivo Report.cfg.

[!DNL Report] permite que você distribua os relatórios em um conjunto usando os seguintes métodos:

* **Email:** Para distribuir relatórios como arquivos, [!DNL .png] arquivos ou miniaturas do Excel por email (em linha ou como anexos), especifique os parâmetros de Relatório de email no [!DNL Report.cfg] arquivo do conjunto de relatórios. Todos os relatórios nesse conjunto são enviados por email em uma mensagem para os destinatários especificados.

* **Diretório compartilhado:** Para distribuir relatórios como arquivos, [!DNL .png] arquivos ou miniaturas do Excel em um diretório compartilhado, especifique o diretório no parâmetro Raiz de saída no [!DNL Report.cfg] arquivo do conjunto de relatórios.

* **Portal de relatórios:** Um portal de relatórios permite que você visualize relatórios por meio do navegador da Web. O da Adobe [!DNL Report Portal] exibe relatórios gerados como Excel ou [!DNL .png] arquivos, mas não os gerados como miniaturas ( [!DNL .jpg]). Para distribuir relatórios para um portal, especifique a raiz do documento do servidor da Web usado para o portal no parâmetro Raiz de saída no [!DNL Report.cfg] arquivo do conjunto de relatórios. Para obter mais informações sobre como instalar e usar [!DNL Report Portal], consulte [Trabalhar com o portal](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)de relatórios.

>[!NOTE]
>
>Para ler a saída atualmente suportada por [!DNL Report], você deve ter um aplicativo capaz de exibir os relatórios no(s) formato(s) desejado(s). Por exemplo, para exibir [!DNL .xlsx] arquivos, é necessário ter o Microsoft Excel 2007 ou posterior.

Você também pode usar uma combinação dessas opções de geração e distribuição. Por exemplo, se você definir o [!DNL Report Types] parâmetro para gerar um conjunto de relatórios como Excel e [!DNL .png] arquivos e, em seguida, definir os parâmetros [!DNL Mail Report]e [!DNL Output Root] , todos os relatórios nesse conjunto serão distribuídos para o diretório de saída especificado (talvez para exibição em um portal) e enviados por email para os destinatários.

Para obter etapas para configurar seus conjuntos de relatórios, consulte [Trabalhar com conjuntos](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5)de relatórios. Para obter mais informações sobre os [!DNL Report.cfg] parâmetros específicos, consulte Parâmetros [Report.cfg](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
