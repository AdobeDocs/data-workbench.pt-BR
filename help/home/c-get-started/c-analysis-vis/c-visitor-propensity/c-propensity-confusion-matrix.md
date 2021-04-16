---
description: Os cálculos estatísticos da Pontuação de propensão são definidos.
title: Calcular a pontuação de propensão
uuid: 67270864-0468-4cc9-b48b-0e880f813555
exl-id: 679e1363-fd10-4a44-a85a-ef0daefaf303
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 1%

---

# Calcular a pontuação de propensão{#calculating-propensity-scoring}

Os cálculos estatísticos da Pontuação de propensão são definidos.

Conceitualmente, a pontuação calculada para cada visitante é uma probabilidade estimada de que o evento especificado (definido pelo filtro de direcionamento) possa ocorrer, resultando em um intervalo de valor de pontuação de 0 a 100%. O procedimento de pontuação usa amostras existentes como dados de treinamento para encontrar a relação entre a probabilidade do evento e as variáveis de interesse independentes selecionadas.

Matematicamente, essas relações são refletidas em cada valor quantitativo associado a cada variável independente. Esses valores são chamados de coeficientes de modelo. Atualmente, o ScoreDim usa o algoritmo IRLS (Least Squares) com Reponderação Iterativa para estimar os coeficientes do modelo. O IRLS atravessa as amostras várias vezes até que a diferença de coeficientes entre a passagem atual e a passagem anterior seja inferior a 1.0e-6, altura em que é chamado **converged**. No entanto, dependendo dos dados, as IRLS poderão não conseguir alcançar a convergência.

Nesse caso, a iteração de treinamento do modelo terminará quando

* a diferença de coeficiente aumenta em vez de menor,
* 1.000 passagens foram atingidas, ou
* um erro matemático impede a repetição da iteração.

Se o IRLS não convergir, será usado um algoritmo de backup denominado Stochastic Gradient Decent (SGD). A SGD também passará por amostras de treinamento várias vezes. Mas, ao contrário do IRLS, os coeficientes do modelo SGD são controlados de modo que a diferença entre a iteração sempre diminua de forma exponencial. Da mesma forma, a SGD terminará quando a diferença de coeficiente for inferior a 1.0e-6 ou se tiverem sido atingidos 100.000 passagens. A falha do IRLS e da participação da SGD será registrada no registro de rastreio.

Para ambos os algoritmos, nem todas as amostras são treinadas em modelos. Oitenta por cento são usados atualmente para treinar o modelo. Depois que o modelo for treinado, as 20% restantes serão usadas para avaliar a força do modelo em termos de Precisão, Recall e Precisão que é calculada a partir da matriz de confusão. Quanto mais próximo de 100%, melhor será o modelo de pontuação.
