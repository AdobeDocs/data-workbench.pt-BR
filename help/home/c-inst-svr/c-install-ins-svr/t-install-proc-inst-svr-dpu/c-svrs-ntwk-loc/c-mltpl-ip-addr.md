---
description: Se os clientes puderem acessar um servidor Insight por meio de várias redes (por exemplo, através da intranet corporativa e pela Internet), o arquivo de endereço deve definir um local de rede separado para cada um dos endereços IP do servidor.
title: Vários endereços IP para um servidor Insight
uuid: 6ed00b47-8ba3-4127-a5db-7e684e573d9c
exl-id: 71654a60-af82-45f2-826b-29ecc7127b0b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 7%

---

# Vários endereços IP para um servidor Insight{#multiple-ip-addresses-for-an-insight-server}

Se os clientes puderem acessar um servidor Insight por meio de várias redes (por exemplo, através da intranet corporativa e pela Internet), o arquivo de endereço deve definir um local de rede separado para cada um dos endereços IP do servidor.

Por exemplo, se o servidor [!DNL VS01.myCompany.com] tiver um endereço IP de 10.2.1.70 em uma rede interna e um endereço IP de 65.196.125.167 na Internet, o arquivo de endereço incluiria um local de rede para cada um dos endereços, conforme ilustrado no exemplo abaixo:

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
1 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 65.196.125.167
      Name = string: VS01.myCompany.com
  Name = string: Internet
  Parent = string:
```

Quando os usuários se conectam a um [!DNL Insight Server], eles usam o parâmetro NetworkLocation (na interface do usuário do cliente) para especificar o local de rede pelo qual desejam que o nome comum do servidor seja resolvido. Por exemplo, considerando um arquivo de endereço com os dois NetworkLocations mostrados acima, um usuário definiria o parâmetro NetworkLocation como &quot;MyCorporate Intranet&quot; para se conectar a [!DNL Insight Server] por meio da rede interna e à &quot;Internet&quot; para se conectar ao servidor por meio da Internet.
