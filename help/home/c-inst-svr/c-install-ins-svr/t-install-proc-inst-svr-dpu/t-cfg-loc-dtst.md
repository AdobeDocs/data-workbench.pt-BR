---
description: Por padrão, o Insight Server grava seu conjunto de dados (temp.db) na mesma unidade dos arquivos de programa do Insight Server.
title: Configurar a localização do conjunto de dados (temp.db)
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
exl-id: 6812883f-ad51-4314-8c80-e95c3fe84664
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---

# Configurar a localização do conjunto de dados (temp.db){#configuring-the-location-of-the-dataset-temp-db}

Por padrão, o Insight Server grava seu conjunto de dados (temp.db) na mesma unidade dos arquivos de programa do Insight Server.

Por exemplo, se você instalar [!DNL Insight Server] na unidade C, ele gravará o conjunto de dados na unidade C.

Se quiser que [!DNL Insight Server] mantenha o conjunto de dados em uma unidade diferente ou se a quantidade de dados que espera coletar exigir o uso de várias unidades, atualize o arquivo [!DNL Disk Files.cfg] para especificar onde deseja que [!DNL Insight Server] grave o arquivo [!DNL temp.db].

**Para configurar o local do temp.db**

1. Navegue até a pasta [!DNL Components] no diretório em que você instalou [!DNL Insight Server].

   Exemplo: [!DNL C:\Adobe\Server\Components]

1. Abra o arquivo [!DNL Disk Files.cfg] em um editor de texto, como o Bloco de notas.

   Por padrão, esse arquivo contém uma única entrada na estrutura Arquivos de disco, como mostrado abaixo.

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. Para alterar o local de [!DNL temp.db], modifique a definição Arquivos de Disco. O exemplo a seguir ilustra como você editaria a configuração para espalhar o arquivo [!DNL temp.db] entre as unidades C, D e E:

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
   >Observe o uso de barras invertidas duplas nos nomes de arquivo acima. Nos arquivos de configuração [!DNL Insight Server], o caractere de barra invertida é um caractere de escape. É usado para expressar sequências de controle especiais (por exemplo, \t para um caractere de tabulação) no texto. Para representar um caractere de barra invertida real, você deve digitar a barra invertida duas vezes (por exemplo, \\) para substituir a função de escape. Isso se aplica somente ao editar arquivos de configuração em um editor de texto, como o Bloco de notas.
