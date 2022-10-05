---
description: Os parâmetros de vetor contêm vários valores para uma única variável.
title: Parâmetros de vetor
uuid: 2ca83502-acc4-4b94-b0e4-a48a596e7623
exl-id: c6140bdf-dcd9-4fa9-a6e0-34cbc45414d0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 4%

---

# Parâmetros de vetor{#vector-parameters}

{{eol}}

Os parâmetros de vetor contêm vários valores para uma única variável.

Você pode fazer referência a parâmetros de vetor somente como o único item de um vetor. Este exemplo mostra uma [!DNL Transformation Dataset Include] arquivo que define um parâmetro de vetor. O parâmetro de vetor, &quot;Domínios internos&quot;, consiste em três valores.

![](assets/cfg_WebParameters_InternalDomains.png)

Observe que o parâmetro de vetor é o único item listado para a variável [!DNL Matches] no [!DNL String Match] condição.

![](assets/cfg_Parameters_InternalDomains_Ref.png)

Para obter mais informações sobre domínios internos, consulte [Configurações para dados da Web](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519). Para obter informações sobre o [!DNL String Match] condição, consulte [Condições](../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md).
