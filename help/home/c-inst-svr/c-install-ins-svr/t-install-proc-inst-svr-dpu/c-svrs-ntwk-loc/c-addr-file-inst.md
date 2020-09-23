---
description: O arquivo de endereço instalado no Insight Server contém quatro locais de rede predefinidos.
solution: Analytics
title: O arquivo de endereço instalado no servidor Insight
uuid: a58d36d8-e1a3-43e7-91c5-c57351e1be49
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 2%

---


# O arquivo de endereço instalado no servidor Insight{#the-address-file-installed-on-insight-server}

O arquivo de endereço instalado no Insight Server contém quatro locais de rede predefinidos.

O procedimento na próxima seção descreve como configurar este arquivo.

```
Locations = vector: 4 items  
  0 = NetworkLocation:  
    Addresses = vector: 1 items 
      0 = AddressDefinition:  
        Address = string:  
        Name = string:  
    Name = string:  
    Parent = string:  
  1 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight 
    Parent = string:  
  2 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight Server 
    Parent = string: 
  3 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Report Server 
    Parent = string:
```

* NetworkLocation 0 é um local de rede vazio e sem nome que você edita para associar o nome comum do seu [!DNL Insight Server] endereço IP. Se o servidor tiver vários endereços IP, crie NetworkLocations adicionais.
* NetworkLocation 1 é o local da [!DNL Insight] rede. Se você não definir explicitamente o parâmetro NetworkLocation, [!DNL Insight] resolverá nomes comuns por meio desse local de rede.

* NetworkLocation 2 é o local da [!DNL Insight Server] rede. Quando [!DNL Insight Servers] operam em um cluster, eles usam esse local de rede para resolver nomes comuns para a comunicação entre servidores.

* NetworkLocation 3 é o local de rede do [!DNL Report] servidor. Se você não definir explicitamente o parâmetro NetworkLocation, [!DNL Report] resolverá nomes comuns por meio desse local de rede.

## Para configurar o arquivo de endereço {#section-10caab9854a244e39b09071946f7bd27}

O procedimento a seguir descreve como configurar o arquivo de endereço para definir um local de rede (ou locais de rede) para o seu [!DNL Insight Server].

1. Navegue até a [!DNL Addresses] pasta no diretório em que você instalou [!DNL Insight Server] (por exemplo, [!DNL C:\Adobe\Server\Addresses)].

1. Localize o [!DNL server.address] arquivo e renomeie-o para refletir o nome comum do servidor. Por exemplo, se o nome comum fosse [!DNL server.mycompany.com], você renomearia o arquivo [!DNL server.mycompany.com.address].

1. Abra o arquivo renomeado em um editor de texto, como o Bloco de notas.
1. Edite NetworkLocation 0 para especificar o nome comum e o endereço IP do [!DNL Insight Server] formulário, conforme mostrado abaixo. Se o servidor tiver vários endereços IP, use NetworkLocation 0 para especificar o endereço IP do servidor na rede local e não roteável (por exemplo, sua localização na rede interna).

   ```
   Locations = vector: 3 items 
   0 = NetworkLocation: 
     Addresses = vector: 1 items 
       0 = AddressDefinition: 
         Address = string: IPAddress 
         Name = string: CommonName 
     Name = string: NetworkLocationName 
     Parent = string: 
   ```

<table id="table_02C2A1630CCD40C4A51B314C3CB683F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para este valor... </th> 
   <th colname="col2" class="entry"> Especificar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>Endereço IP</i> </td> 
   <td colname="col2"> <p>O endereço IP numérico da máquina do <span class="keyword"> Insight Server </span> . </p> <p>Exemplo: 192.168.124.176 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Nome comum </i> </td> 
   <td colname="col2"> <p>O nome comum atribuído ao certificado digital para o <span class="keyword"> Insight Server </span>. </p> <p>Exemplo: <span class="filepath"> server.mycompany.com </span></p> <p>Observação: Digite esse nome exatamente como aparece no certificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Nome do local da rede </i> </td> 
   <td colname="col2"> <p>O nome que você deseja atribuir à coleção de nomes comuns e endereços IP que esta NetworkLocation representa. O nome deve ser exclusivo no arquivo de endereço. </p> <p>Exemplo: Intranet corporativa </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Se [!DNL Insight Server] tiver endereços IP adicionais, crie um NetworkLocation adicional para cada endereço. (Uma maneira fácil de fazer isso é fazer uma cópia da NetworkLocation que você criou acima e atualizar o endereço IP na cópia.)

   Você pode adicionar o novo NetworkLocation ao final do arquivo de endereço ou inseri-lo entre as definições de NetworkLocation existentes. (A posição de uma NetworkLocation no ficheiro de endereço não é significativa; no entanto, os NetworkLocations [!DNL Insight], [!DNL Insight Server]e [!DNL Report] Server normalmente são colocados no final do arquivo.)

   Depois de adicionar os NetworkLocations necessários, faça o seguinte para renumerar os itens no arquivo:

   1. Atualize a contagem de itens da estrutura Locais para corresponder ao número total de definições NetworkLocation no arquivo. Por exemplo, se seu arquivo contiver quatro definições NetworkLocation, a linha Locais terá a seguinte aparência:

      ```
      Locations = vector: 4 items
      ```

   1. Atualize os números de itens NetworkLocation para que NetworkLocations sejam numerados consecutivamente (a partir de 0).
   Para obter um exemplo de um arquivo de endereço que define um [!DNL Insight Server] com dois endereços IP, consulte o exemplo nesta seção.

1. Nas localizações de rede [!DNL Insight] e do [!DNL Report] servidor, edite o parâmetro Pai, conforme mostrado abaixo, para especificar o nome da NetworkLocation que [!DNL Insight] e [!DNL Report] usar como suas localizações de rede padrão. (Para obter um exemplo da aparência do parâmetro Pai quando configurado, consulte o exemplo nesta seção.)

   ```
   1 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight 
     Parent = string: ClientDefaultNetworkLocation 
   
   3 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Report Server 
     Parent = string: ClientDefaultNetworkLocation
   ```

   Se o seu [!DNL Insight Server] tiver um único endereço IP e, portanto, tiver apenas um NetworkLocation, aponte o parâmetro Pai para esse NetworkLocation. Se [!DNL Insight Server] tiver vários endereços IP, aponte o parâmetro Pai para a NetworkLocation que define o endereço ao qual seus clientes [!DNL Insight] e [!DNL Report] clientes se conectam com mais frequência.

1. No local da [!DNL Insight Server] rede, edite o parâmetro Pai, conforme mostrado abaixo, para apontar para NetworkLocation que o servidor usa para resolver nomes comuns de outros [!DNL Insight Servers] quando opera em um cluster. Embora esse local de rede não seja usado a menos que um [!DNL Insight Server] opere em um cluster, é uma boa prática, mesmo em uma única configuração de servidor, apontar o parâmetro Pai para um local de rede que identifique o endereço IP interno do servidor.

   ```
   2 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight Server 
     Parent = string: ServerDefaultNetworkLocation
   ```

O exemplo a seguir mostra um arquivo de endereço concluído. Esse arquivo define cinco locais de rede.

* Os itens de NetworkLocation 0 e 1 definem locais de rede chamados &quot;MyCorporateIntranet&quot; e &quot;Internet&quot;. Esses locais de rede definem dois endereços IP diferentes para um servidor chamado [!DNL VS01.myCompany.com].
* O item NetworkLocation 2 é o local da [!DNL Insight] rede. Esse é o local de rede padrão usado pela [!DNL Insight]. Neste exemplo, o local da [!DNL Insight] rede herda AddressDefinition do NetworkLocation &quot;Internet&quot;.

* O item 3 NetworkLocation é a localização da [!DNL Insight Server] rede. Esse é o local de rede padrão [!DNL Insight Server] usado quando se comunica com outros servidores em um cluster. Neste exemplo, o local da [!DNL Insight Server] rede herda AddressDefinition do NetworkLocation &quot;MyCorporate Intranet&quot;.

* O item NetworkLocation 4 é o local de rede do [!DNL Report] Servidor. Esse é o local de rede padrão usado pela [!DNL Report]. Neste exemplo, o local de rede do [!DNL Report] Servidor herda AddressDefinition do NetworkLocation &quot;Internet&quot;.

   ```
   Locations = vector: 5 items 
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
   
     2 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Insight 
       Parent = string: Internet 
   
     3 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Insight Server 
       Parent = string: MyCorporateIntranet 
   
     4 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Report Server 
       Parent = string: Internet
   ```

