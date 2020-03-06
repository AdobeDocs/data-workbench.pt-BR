---
description: Se os clientes puderem acessar um Insight Server por meio de várias redes (por exemplo, por meio da intranet corporativa e da Internet), o arquivo de endereço deverá definir um local de rede separado para cada endereço IP do servidor.
solution: Insight
title: Vários endereços IP para um servidor Insight
uuid: 6ed00b47-8ba3-4127-a5db-7e684e573d9c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Vários endereços IP para um servidor Insight{#multiple-ip-addresses-for-an-insight-server}

Se os clientes puderem acessar um Insight Server por meio de várias redes (por exemplo, por meio da intranet corporativa e da Internet), o arquivo de endereço deverá definir um local de rede separado para cada endereço IP do servidor.

Por exemplo, se o servidor [!DNL VS01.myCompany.com] tiver um endereço IP de 10.2.1.70 em uma rede interna e um endereço IP de 65.196.125.167 na Internet, o arquivo de endereço incluirá um local de rede para cada um dos endereços, como ilustrado no exemplo abaixo:

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

Quando os usuários se conectam a um servidor, [!DNL Insight Server]eles usam o parâmetro NetworkLocation (na interface do usuário do cliente) para especificar o local de rede pelo qual desejam que o nome comum do servidor seja resolvido. Por exemplo, considerando um arquivo de endereço com os dois NetworkLocations mostrados acima, um usuário definiria o parâmetro NetworkLocation como &quot;MyCorporate Intranet&quot; para se conectar [!DNL Insight Server] pela rede interna e à &quot;Internet&quot; para se conectar ao servidor pela Internet.
