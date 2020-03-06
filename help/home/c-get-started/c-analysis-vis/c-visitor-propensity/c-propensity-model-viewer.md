---
description: Um visualizador de modelo permite gerar um modelo de regressão logística usando o recurso Pontuação de propensão.
solution: Analytics
title: Visualizador de modelos
topic: Data workbench
uuid: 7ee8ff29-21c2-4721-804a-c7a5d101b50b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Model Viewer{#model-viewer}

Um visualizador de modelo permite gerar um modelo de regressão logística usando o recurso Pontuação de propensão.

O Visualizador de modelo exibe as pesos do coeficiente de cada variável de entrada (incluindo o termo constante) e seu intervalo de erros estatísticos. As variáveis de entrada que mostram um alto coeficiente absoluto e uma pequena margem de erro são os indicadores mais significativos do modelo.

**Para abrir um gráfico do Visualizador de modelos**

1. Selecionar [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Passe o cursor do mouse sobre Modelo concluído de uma pontuação salva.

![](assets/propensity_model_viewer.png)

As variáveis de entrada com um coeficiente >= 1 são influências positivas no modelo de propensão. Os coeficientes que são &lt; 1 são influências negativas no modelo de propensão. O intervalo definido dentro dos parênteses é o erro e indica a consistência da variável de entrada na população bem-sucedida.
