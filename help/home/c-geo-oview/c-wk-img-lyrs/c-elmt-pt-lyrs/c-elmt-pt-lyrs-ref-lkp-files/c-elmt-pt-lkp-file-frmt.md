---
description: Informações sobre as colunas da camada do ponto de elemento.
title: Formato de arquivo de pesquisa do ponto de elemento
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
exl-id: da81da9e-0567-4f3a-bc0d-ab6c5e4a23b7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 6%

---

# Formato de arquivo de pesquisa do ponto de elemento{#element-point-lookup-file-format}

Informações sobre as colunas da camada do ponto de elemento.

O arquivo de pesquisa de camada de ponto de elemento deve conter pelo menos as três colunas a seguir:

* **[!DNL Key]coluna:** essa coluna deve conter dados de chave comuns, o que permite que o servidor do Data Workbench conecte os dados no arquivo de pesquisa àqueles no conjunto de dados. A coluna [!DNL Key] deve ser a primeira coluna no arquivo de pesquisa. Cada linha nesta coluna identifica um elemento da dimensão.

* **[!DNL Longitude]coluna:** essa coluna deve conter a longitude de cada ponto de dados na  [!DNL Key] coluna .

* **[!DNL Latitude]coluna:** essa coluna deve conter a latitude para cada ponto de dados na  [!DNL Key] coluna .

* **[!DNL Name]coluna:**  (opcional). Se desejar especificar um nome a ser exibido no mapa para cada ponto de dados, você pode incluir uma coluna [!DNL Name] no arquivo de pesquisa.

Cada linha no arquivo de pesquisa [!DNL Zip Points.txt] contém um CEP na primeira coluna, seguido pela longitude, latitude e nome da cidade associado.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```
