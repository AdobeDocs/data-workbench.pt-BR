---
description: O arquivo de endereço instalado no servidor Insight contém quatro locais de rede predefinidos.
title: O arquivo de endereço instalado no servidor Insight
uuid: a58d36d8-e1a3-43e7-91c5-c57351e1be49
exl-id: 12e9bfa2-99ac-4584-b761-38401d1bc3d1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 2%

---

# O arquivo de endereço instalado no servidor Insight{#the-address-file-installed-on-insight-server}

{{eol}}

O arquivo de endereço instalado no servidor Insight contém quatro locais de rede predefinidos.

O procedimento da próxima seção descreve como configurar esse arquivo.

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

* NetworkLocation 0 é um local de rede vazio e sem nome que você edita para associar o nome comum de seu [!DNL Insight Server] para seu endereço IP. Se o servidor tiver vários endereços IP, você criará outros NetworkLocations.
* NetworkLocation 1 é o [!DNL Insight] local da rede. Se você não definir explicitamente o parâmetro NetworkLocation , [!DNL Insight] resolve nomes comuns por meio desse local de rede.

* NetworkLocation 2 é o [!DNL Insight Server] local da rede. When [!DNL Insight Servers] operar em um cluster, eles usam esse local de rede para resolver nomes comuns para comunicação entre servidores.

* NetworkLocation 3 é o [!DNL Report] Local de rede do servidor. Se você não definir explicitamente o parâmetro NetworkLocation , [!DNL Report] resolve nomes comuns por meio desse local de rede.

## Para configurar o arquivo de endereço {#section-10caab9854a244e39b09071946f7bd27}

O procedimento a seguir descreve como configurar o arquivo de endereço para definir um local de rede (ou locais de rede) para seu [!DNL Insight Server].

1. Navegue até o [!DNL Addresses] no diretório em que você instalou o [!DNL Insight Server] (por exemplo, [!DNL C:\Adobe\Server\Addresses)].

1. Localize a variável [!DNL server.address] e renomeie esse arquivo para refletir o nome comum do servidor. Por exemplo, se o nome comum fosse [!DNL server.mycompany.com], você renomearia o arquivo [!DNL server.mycompany.com.address].

1. Abra o arquivo renomeado em um editor de texto, como o Bloco de notas.
1. Edite NetworkLocation 0 para especificar o nome comum e o endereço IP da variável [!DNL Insight Server] conforme mostrado abaixo. Se o servidor tiver vários endereços IP, use NetworkLocation 0 para especificar o endereço IP do servidor na rede local não roteável (por exemplo, a localização na rede interna).

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
   <td colname="col2"> <p>O endereço IP numérico da variável <span class="keyword"> Servidor Insight </span> máquina. </p> <p>Exemplo: 192.168.124.176 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Nome comum </i> </td> 
   <td colname="col2"> <p>O nome comum atribuído ao certificado digital para <span class="keyword"> Servidor Insight </span>. </p> <p>Exemplo: <span class="filepath"> server.mycompany.com </span></p> <p>Observação: Certifique-se de digitar esse nome exatamente como aparece no certificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Nome do local da rede </i> </td> 
   <td colname="col2"> <p>O nome que você deseja atribuir à coleção de nomes e endereços IP comuns que essa NetworkLocation representa. O nome deve ser exclusivo no arquivo de endereço. </p> <p>Exemplo: Intranet corporativa </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Se o seu [!DNL Insight Server] tem endereços IP adicionais, crie um NetworkLocation adicional para cada endereço. (Uma maneira fácil de fazer isso é fazer uma cópia da NetworkLocation que você criou acima e atualizar o endereço IP na cópia.)

   Você pode adicionar o novo NetworkLocation ao final do arquivo de endereço ou inseri-lo entre as definições de NetworkLocation existentes. (A posição de uma NetworkLocation no ficheiro de endereço não é significativa; no entanto, o [!DNL Insight], [!DNL Insight Server]e [!DNL Report] As localizações de rede do servidor normalmente são colocadas no final do arquivo.)

   Depois de ter adicionado os NetworkLocations necessários, faça o seguinte para renumerar os itens no arquivo:

   1. Atualize a contagem de itens da estrutura Localizações para corresponder ao número total de definições de NetworkLocation no arquivo. Por exemplo, se seu arquivo contém quatro definições de NetworkLocation , a linha Localizações seria a seguinte:

      ```
      Locations = vector: 4 items
      ```

   1. Atualize os números de item NetworkLocation para que NetworkLocations sejam numerados consecutivamente (começando em 0).
   Para um exemplo de um arquivo de endereço que define um [!DNL Insight Server] com dois endereços IP, consulte o exemplo nesta seção.

1. No [!DNL Insight] e [!DNL Report] Locais de rede do servidor, edite o parâmetro Pai como mostrado abaixo para especificar o nome do NetworkLocation que [!DNL Insight] e [!DNL Report] use como seus locais de rede padrão. (Para obter um exemplo da aparência do parâmetro Pai quando configurado, consulte o exemplo nesta seção.)

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

   Se o seu [!DNL Insight Server] tem um único endereço IP e, portanto, tem apenas uma NetworkLocation, aponta o parâmetro Pai para essa NetworkLocation. Se o seu [!DNL Insight Server] tem vários endereços IP, aponte o parâmetro Pai para a NetworkLocation que define o endereço para o qual seu [!DNL Insight] e [!DNL Report] Os clientes se conectam com mais frequência.

1. No [!DNL Insight Server] local da rede, edite o parâmetro Pai como mostrado abaixo para apontar para o NetworkLocation que o servidor usa para resolver nomes comuns de outros [!DNL Insight Servers] quando ele opera em um cluster. (Embora essa localização de rede não seja usada, a menos que um [!DNL Insight Server] opera em um cluster, é uma boa prática, mesmo em uma única configuração de servidor, apontar o parâmetro Pai para um local de rede que identifica o endereço IP interno do servidor.)

   ```
   2 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight Server 
     Parent = string: ServerDefaultNetworkLocation
   ```

O exemplo a seguir mostra um arquivo de endereço concluído. Esse arquivo define cinco locais de rede.

* Os itens de NetworkLocation 0 e 1 definem os locais de rede chamados &quot;MyCorporateIntranet&quot; e &quot;Internet&quot;. Esses locais de rede definem dois endereços IP diferentes para um servidor chamado [!DNL VS01.myCompany.com].
* O item 2 NetworkLocation é o [!DNL Insight] local da rede. Esse é o local de rede padrão usado por [!DNL Insight]. Neste exemplo, a variável [!DNL Insight] o local da rede herda suas AddressDefinition do NetworkLocation &quot;Internet&quot;.

* O item 3 NetworkLocation é o [!DNL Insight Server] local da rede. Esse é o local de rede padrão [!DNL Insight Server] O usa quando se comunica com outros servidores em um cluster. Neste exemplo, a variável [!DNL Insight Server] O local da rede herda suas AddressDefinition do NetworkLocation &quot;MyCorporate Intranet&quot;.

* O item 4 de NetworkLocation é o [!DNL Report] Local de rede do servidor. Esse é o local de rede padrão usado por [!DNL Report]. Neste exemplo, a variável [!DNL Report] O local de rede do servidor herda AddressDefinition do NetworkLocation &quot;Internet&quot;.

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
