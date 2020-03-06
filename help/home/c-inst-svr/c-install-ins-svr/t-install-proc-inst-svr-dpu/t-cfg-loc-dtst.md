---
description: Por padrão, o Insight Server grava seu conjunto de dados (temp.db) na mesma unidade dos arquivos de programa do Insight Server.
solution: Insight
title: Configuração da localização do conjunto de dados (temp.db)
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuração da localização do conjunto de dados (temp.db){#configuring-the-location-of-the-dataset-temp-db}

Por padrão, o Insight Server grava seu conjunto de dados (temp.db) na mesma unidade dos arquivos de programa do Insight Server.

Por exemplo, se você instalar [!DNL Insight Server] na unidade C, ele grava o conjunto de dados na unidade C.

Se você quiser manter [!DNL Insight Server] o conjunto de dados em uma unidade diferente, ou se a quantidade de dados que espera coletar exigir o uso de várias unidades, atualize o [!DNL Disk Files.cfg] arquivo para especificar onde deseja [!DNL Insight Server] gravar o [!DNL temp.db] arquivo.

**Para configurar o local de temp.db**

1. Navegue até a [!DNL Components] pasta no diretório em que você instalou [!DNL Insight Server].

   Exemplo: [!DNL C:\Adobe\Server\Components]

1. Abra o [!DNL Disk Files.cfg] arquivo em um editor de texto, como o Bloco de notas.

   Por padrão, esse arquivo contém uma única entrada na estrutura Arquivos de Disco, como mostrado abaixo.

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. Para alterar o local de [!DNL temp.db], modifique a definição de Arquivos de Disco. O exemplo a seguir ilustra como você editaria a configuração para espalhar o [!DNL temp.db] arquivo pelas unidades C, D e E:

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
   >Observe o uso de barras invertidas duplas nos nomes de arquivos acima. Nos arquivos [!DNL Insight Server] de configuração, o caractere de barra invertida é um caractere de escape. É usado para expressar sequências de controle especiais (por exemplo, \t para um caractere de tabulação) no texto. Para representar um caractere de barra invertida real, você deve digitar a barra invertida duas vezes (por exemplo, \\) para substituir a função de escape. Isso se aplica somente ao editar arquivos de configuração em um editor de texto, como o Bloco de notas.

