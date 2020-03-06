---
description: No Portal de relatórios, você pode exibir relatórios gerados pelo Servidor de relatórios como arquivos do Excel (.xls ou .xlsx) ou arquivos .png.
solution: Analytics
title: Configuração de arquivos Report.cfg
topic: Data workbench
uuid: b6ce1621-283f-458d-a88d-a062539d243b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuração de arquivos Report.cfg{#configuring-report-cfg-files}

No Portal de relatórios, você pode exibir relatórios gerados pelo Servidor de relatórios como arquivos do Excel (.xls ou .xlsx) ou arquivos .png.

Para exibir um conjunto de relatórios no [!DNL Report Portal], você deve definir os seguintes parâmetros no [!DNL Report.cfg] arquivo para esse conjunto de relatórios:

* No **[!UICONTROL Output Root]** parâmetro, especifique a raiz do documento do servidor da Web usado para o portal.
* No **[!UICONTROL Report Types]** parâmetro, especifique Excel, png e/ou miniatura como os tipos de relatório que você deseja gerar.

Quando [!DNL Report Server] [!DNL Report Portal] gera os relatórios nos formatos especificados, coloca esses arquivos na raiz do documento do servidor da Web, que é onde, durante a instalação, você configura o para acessar os relatórios.

Para obter mais informações sobre os [!DNL Report.cfg] parâmetros específicos, consulte Parâmetros [Report.cfg](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
