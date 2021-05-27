---
description: Um visualizador de modelo permite gerar um modelo de regressão logística usando o recurso Pontuação de propensão .
title: Visualizador de modelo
uuid: 7ee8ff29-21c2-4721-804a-c7a5d101b50b
exl-id: e0e4acd4-76a2-436a-993b-2bb7ca91ae1a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 3%

---

# Visualizador de modelo{#model-viewer}

Um visualizador de modelo permite gerar um modelo de regressão logística usando o recurso Pontuação de propensão .

O Visualizador de Modelo exibe os pesos do coeficiente de cada variável de entrada (incluindo o termo constante) e seu intervalo de erros estatísticos. As variáveis de entrada que mostram um alto coeficiente absoluto e uma pequena margem de erro são os indicadores mais significativos no modelo.

**Para abrir um gráfico de Visualizador de Modelo**

1. Selecionar [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Passe o mouse sobre Modelo concluído de uma pontuação salva.

![](assets/propensity_model_viewer.png)

As variáveis de entrada com um coeficiente >= 1 são influências positivas no modelo de propensão. Os coeficientes &lt; 1 são influências negativas no modelo de propensão. O intervalo definido dentro dos parênteses é o erro e indica a consistência da variável de entrada na população bem-sucedida.
