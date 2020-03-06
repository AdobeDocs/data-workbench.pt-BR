---
description: Informações sobre as colunas da camada do ponto de elemento.
solution: Analytics
title: Formato de Arquivo de Pesquisa do Ponto de Elemento
topic: Data workbench
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Formato de Arquivo de Pesquisa do Ponto de Elemento{#element-point-lookup-file-format}

Informações sobre as colunas da camada do ponto de elemento.

O arquivo de pesquisa de camada de ponto de elemento deve conter pelo menos as três colunas a seguir:

* **[!DNL Key]coluna:**Essa coluna deve conter dados de chave comuns, o que permite que o servidor de análise de big data conecte os dados no arquivo de pesquisa aos dados no conjunto de dados. A[!DNL Key]coluna deve ser a primeira coluna no arquivo de pesquisa. Cada linha nesta coluna identifica um elemento da dimensão.

* **[!DNL Longitude]coluna:**Essa coluna deve conter a longitude de cada ponto de dados na[!DNL Key]coluna.

* **[!DNL Latitude]coluna:**Essa coluna deve conter a latitude para cada ponto de dados na[!DNL Key]coluna.

* **[!DNL Name]coluna:**(Opcional). Se você quiser especificar um nome a ser exibido no mapa para cada ponto de dados, é possível incluir uma[!DNL Name]coluna no arquivo de pesquisa.

Cada linha no arquivo de [!DNL Zip Points.txt] pesquisa contém um CEP na primeira coluna, seguido da longitude, latitude e nome da cidade associado.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

