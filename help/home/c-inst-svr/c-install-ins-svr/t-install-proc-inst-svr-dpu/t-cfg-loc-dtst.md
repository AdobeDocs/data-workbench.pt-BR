---
description: Por padrão, o Insight Server grava seu conjunto de dados (temp.db) na mesma unidade dos arquivos de programa do Insight Server.
title: Configurar a localização do conjunto de dados (temp.db)
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
exl-id: 6812883f-ad51-4314-8c80-e95c3fe84664
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---

# Configurar a localização do conjunto de dados (temp.db){#configuring-the-location-of-the-dataset-temp-db}

{{eol}}

Por padrão, o Insight Server grava seu conjunto de dados (temp.db) na mesma unidade dos arquivos de programa do Insight Server.

Por exemplo, se você instalar [!DNL Insight Server] na unidade C, ele grava o conjunto de dados na unidade C.

Se desejar [!DNL Insight Server] para manter o conjunto de dados em uma unidade diferente, ou se a quantidade de dados que você espera coletar exigir o uso de várias unidades, você deve atualizar a variável [!DNL Disk Files.cfg] arquivo para especificar onde deseja [!DNL Insight Server] para gravar o [!DNL temp.db] arquivo.

**Para configurar o local do temp.db**

1. Navegue até o [!DNL Components] no diretório em que você instalou o [!DNL Insight Server].

   Exemplo: [!DNL C:\Adobe\Server\Components]

1. Abra o [!DNL Disk Files.cfg] em um editor de texto, como o Bloco de notas.

   Por padrão, esse arquivo contém uma única entrada na estrutura Arquivos de disco, como mostrado abaixo.

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. Para alterar a localização de [!DNL temp.db], modifique a definição Arquivos de Disco. O exemplo a seguir ilustra como você editaria a configuração para espalhar a variável [!DNL temp.db] arquivo nas unidades C, D e E:

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 3 items
       0 = string: C:\\Temp\\temp.db
       1 = string: D:\\Temp\\temp.db
       2 = string: E:\\Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

   >[!NOTE]
   >
   >Observe o uso de barras invertidas duplas nos nomes de arquivo acima. Em [!DNL Insight Server] arquivos de configuração, o caractere de barra invertida é um caractere de escape. É usado para expressar sequências de controle especiais (por exemplo, \t para um caractere de tabulação) no texto. Para representar um caractere de barra invertida real, você deve digitar a barra invertida duas vezes (por exemplo, \\) para substituir a função de escape. Isso se aplica somente ao editar arquivos de configuração em um editor de texto, como o Bloco de notas.
