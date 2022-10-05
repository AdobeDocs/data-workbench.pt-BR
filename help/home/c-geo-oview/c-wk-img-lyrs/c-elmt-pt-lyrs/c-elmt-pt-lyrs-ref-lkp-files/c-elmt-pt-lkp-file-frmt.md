---
description: Informações sobre as colunas da camada do ponto de elemento.
title: Formato de arquivo de pesquisa do ponto de elemento
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
exl-id: da81da9e-0567-4f3a-bc0d-ab6c5e4a23b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 6%

---

# Formato de arquivo de pesquisa do ponto de elemento{#element-point-lookup-file-format}

{{eol}}

Informações sobre as colunas da camada do ponto de elemento.

O arquivo de pesquisa de camada de ponto de elemento deve conter pelo menos as três colunas a seguir:

* **[!DNL Key]coluna:** Essa coluna deve conter dados de chave comuns, o que permite que o servidor do Data Workbench conecte os dados no arquivo de pesquisa àqueles no conjunto de dados. O [!DNL Key] deve ser a primeira coluna no arquivo de pesquisa. Cada linha nesta coluna identifica um elemento da dimensão.

* **[!DNL Longitude]coluna:** Essa coluna deve conter a longitude de cada ponto de dados na variável [!DNL Key] coluna.

* **[!DNL Latitude]coluna:** Essa coluna deve conter a latitude para cada ponto de dados no [!DNL Key] coluna.

* **[!DNL Name]coluna:** (Opcional). Se desejar especificar um nome a ser exibido no mapa para cada ponto de dados, você pode incluir um [!DNL Name] no arquivo de pesquisa.

Cada linha no [!DNL Zip Points.txt] O arquivo de pesquisa contém um CEP na primeira coluna, seguido da longitude, latitude e nome da cidade associado.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```
