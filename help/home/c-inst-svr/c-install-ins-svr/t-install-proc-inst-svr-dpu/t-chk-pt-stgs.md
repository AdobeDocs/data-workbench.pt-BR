---
description: Por padrão, o Insight Server escuta nas portas 80 (para HTTP) e 443 (para HTTPS).
solution: Insight
title: Verificando as configurações de porta
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Verificando as configurações de porta{#checking-the-port-settings}

Por padrão, o Insight Server escuta nas portas 80 (para HTTP) e 443 (para HTTPS).

Se essas portas já estiverem alocadas por outro processo no computador em que você instalou [!DNL Insight Server], use o procedimento a seguir para alterar atribuições de [!DNL Insight Server’s] porta.

**Alteração das atribuições de porta**

1. Navegue até a [!DNL Components] pasta no diretório em que você instalou [!DNL Insight Server].

   Exemplo: [!DNL C:\Adobe\Server\Components]

1. Abra o [!DNL Communications.cfg] arquivo em um editor de texto, como o Bloco de notas.
1. Localize as entradas Porta e Porta SSL, como mostrado abaixo:

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

1. Se essas não forem as portas que você deseja usar, altere as atribuições da porta e salve e feche o arquivo. [!DNL Insight Server]
