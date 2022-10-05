---
description: Por padrão, o Insight Server escuta nas portas 80 (para HTTP) e 443 (para HTTPS).
title: Verificar as configurações de porta
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
exl-id: 924860e3-5afa-4c0f-bb7a-d38d5c1355b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 7%

---

# Verificar as configurações de porta{#checking-the-port-settings}

{{eol}}

Por padrão, o Insight Server escuta nas portas 80 (para HTTP) e 443 (para HTTPS).

Se essas portas já estiverem alocadas por outro processo na máquina em que você instalou [!DNL Insight Server], use o procedimento a seguir para alterar [!DNL Insight Server’s] atribuições de porta.

**Para alterar as atribuições de porta**

1. Navegue até o [!DNL Components] no diretório em que você instalou o [!DNL Insight Server].

   Exemplo: [!DNL C:\Adobe\Server\Components]

1. Abra o [!DNL Communications.cfg] em um editor de texto, como o Bloco de notas.
1. Localize as entradas Porta e Porta SSL, conforme mostrado abaixo:

   ```
   component = CommServer: 
     Access Control File = Path: Access Control\\Access Control.cfg
     Access Log Directory = string: P:\\Audit\\
     IP Interface = string: 
     Port = int: 80
     SSL Port = int: 443
     Servers = vector: 17 items
       0 = InitServer: 
         Client Type = string: Sensor
         URI = string: /SensorInit.vsp
     . . .
   ```

1. Se essas não forem as portas desejadas [!DNL Insight Server] para usar, altere as atribuições de porta e, em seguida, salve e feche o arquivo.
