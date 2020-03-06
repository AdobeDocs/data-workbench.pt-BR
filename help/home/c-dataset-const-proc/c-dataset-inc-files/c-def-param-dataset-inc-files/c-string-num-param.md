---
description: Parâmetros de string e numéricos tomam como seus valores sequências de caracteres e números, respectivamente.
solution: Analytics
title: Parâmetros de string e numéricos
topic: Data workbench
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Parâmetros de string e numéricos{#string-and-numeric-parameters}

Parâmetros de string e numéricos tomam como seus valores sequências de caracteres e números, respectivamente.

É possível usá-los alternadamente, mas os parâmetros numéricos devem ser definidos para terem um valor numérico. Você pode fazer referência a parâmetros de sequência de caracteres e numéricos ao definir transformações, condições e dimensões estendidas, e pode fazer referência a mais de um parâmetro na mesma linha.

Não é possível referenciar parâmetros de sequência de caracteres e numéricos em [!DNL Input] ou [!DNL Output] campos, mas é possível usar um parâmetro de sequência de caracteres para definir um campo de entrada constante. Além disso, não é possível fazer referência a parâmetros de sequência de caracteres e numéricos em grupos de decodificadores ou decodificadores.

Este exemplo mostra um [!DNL Log Processing Dataset Include] arquivo que define um parâmetro de string e um parâmetro numérico. Observe que o parâmetro de string, chamado &quot;Pesquisas de Valor&quot;, define um local de arquivo (Pesquisas\Valores) relativo ao diretório de instalação do servidor da análise de big data.

![](assets/cfg_Parameters_StringNumeric.png)

