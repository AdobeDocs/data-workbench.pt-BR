---
description: Os cálculos estatísticos para Pontuação de propensão são definidos.
solution: Analytics
title: Calculando Pontuação de Propensão
topic: Data workbench
uuid: 67270864-0468-4cc9-b48b-0e880f813555
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Calculando Pontuação de Propensão{#calculating-propensity-scoring}

Os cálculos estatísticos para Pontuação de propensão são definidos.

Conceitualmente, a pontuação calculada para cada visitante é uma probabilidade estimada de que o evento especificado (definido pelo filtro de destino) possa ocorrer, resultando em um intervalo de valores de pontuação de 0 a 100%. O procedimento de pontuação usa amostras existentes como dados de treinamento para encontrar a relação entre a probabilidade do evento e as variáveis independentes de interesse selecionadas.

Matematicamente, essas relações são refletidas em cada valor quantitativo associado a cada variável independente. Esses valores são chamados de coeficientes de modelo. ScoreDim usa atualmente o algoritmo Iterativamente Reweight Least Squares (IRLS) para estimar os coeficientes do modelo. O IRLS percorre as amostras várias vezes até que a diferença de coeficientes entre a passagem atual e a passagem anterior seja menor que 1,0e-6, ponto em que é chamado de **convergência**. No entanto, dependendo dos dados, o IRLS pode não conseguir alcançar a convergência.

Nesse caso, a iteração de treinamento do modelo terminará quando

* a diferença de coeficiente fica maior em vez de menor,
* 1.000 passagens foram atingidas, ou
* um erro matemático impede a repetição.

Se o IRLS não convergir, um algoritmo de backup denominado Stochastic Gradient Decent (SGD) será usado. A SGD também passará por amostras de treinamento várias vezes. Mas, ao contrário do IRLS, os coeficientes do modelo SGD são controlados para que a diferença entre a iteração diminua sempre de forma exponencial. Da mesma forma, a SGD terminará quando a diferença de coeficiente cair abaixo de 1.0e-6 ou 100.000 passagens tiverem sido atingidas. A falha do IRLS e o envolvimento do SGD serão registrados no registro de rastreio.

Para ambos os algoritmos, nem todas as amostras entram no treinamento do modelo. Atualmente, 80% são usados para treinar o modelo. Depois que o modelo for treinado, as restantes 20% de amostras serão usadas para avaliar a intensidade do modelo em termos de Precisão, Recall e Precisão que é calculada a partir da matriz de confusão. Quanto mais próximo de 100%, melhor o modelo de pontuação.
