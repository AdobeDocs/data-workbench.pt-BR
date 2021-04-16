---
description: No Portal de relatórios, você pode exibir relatórios gerados pelo Servidor de relatórios como arquivos Excel (.xls ou .xlsx) ou arquivos .png.
title: Configurar arquivos Report.cfg
uuid: b6ce1621-283f-458d-a88d-a062539d243b
exl-id: 5af5abaa-77bf-447b-b341-8f44e228f37a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 4%

---

# Configurar arquivos Report.cfg{#configuring-report-cfg-files}

No Portal de relatórios, você pode exibir relatórios gerados pelo Servidor de relatórios como arquivos Excel (.xls ou .xlsx) ou arquivos .png.

Para exibir um conjunto de relatórios no [!DNL Report Portal], você deve definir os seguintes parâmetros no arquivo [!DNL Report.cfg] para esse conjunto de relatórios:

* No parâmetro **[!UICONTROL Output Root]** , especifique a raiz do documento do servidor da Web usado para o portal.
* No parâmetro **[!UICONTROL Report Types]** , especifique Excel, png e/ou miniatura como os tipos de relatório que deseja gerar.

Quando [!DNL Report Server] gera os relatórios nos formatos especificados, coloca esses arquivos na raiz do documento do servidor da Web, que é onde, durante a instalação, você configura o [!DNL Report Portal] para acessar os relatórios.

Para obter mais informações sobre os parâmetros específicos [!DNL Report.cfg], consulte [Parâmetros Report.cfg](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
