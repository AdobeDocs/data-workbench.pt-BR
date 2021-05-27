---
description: Os parâmetros de string e numéricos são considerados como sequências e números de valores, respectivamente.
title: Parâmetros de string e numéricos
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
exl-id: 37d004da-cde7-4b67-b0cb-0acbb6d8ad68
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 5%

---

# Parâmetros de string e numéricos{#string-and-numeric-parameters}

Os parâmetros de string e numéricos são considerados como sequências e números de valores, respectivamente.

Você pode usá-los alternadamente, mas os parâmetros numéricos devem ser definidos para terem um valor numérico. Você pode fazer referência a parâmetros de string e numéricos ao definir transformações, condições e dimensões estendidas e pode fazer referência a mais de um parâmetro na mesma linha.

Não é possível referenciar parâmetros de string e numéricos em campos [!DNL Input] ou [!DNL Output], mas é possível usar um parâmetro de string para definir um campo de entrada constante. Além disso, não é possível referenciar parâmetros de string e numéricos em decodificadores ou grupos de decodificadores.

Este exemplo mostra um arquivo [!DNL Log Processing Dataset Include] que define um parâmetro de string e um parâmetro numérico. Observe que o parâmetro da string, chamado &quot;Pesquisas de valor&quot;, define um local de arquivo (Pesquisas\Valores) relativo ao diretório de instalação do servidor do Data Workbench.

![](assets/cfg_Parameters_StringNumeric.png)
