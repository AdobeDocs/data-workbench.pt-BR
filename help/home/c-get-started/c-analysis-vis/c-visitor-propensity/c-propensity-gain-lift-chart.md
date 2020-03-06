---
description: Os gráficos de incentivo e ganho oferecem visualizações para avaliar o desempenho potencial de um modelo pontuado para avaliar o desempenho em relação a partes definidas do público-alvo.
solution: Analytics
title: Gráficos de Ganho de propensão e Incentivo
topic: Data workbench
uuid: 4f08277e-deea-48d3-ab15-214c43ad6664
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Gráficos de Ganho de propensão e Incentivo{#propensity-gain-and-lift-charts}

Os gráficos de incentivo e ganho oferecem visualizações para avaliar o desempenho potencial de um modelo pontuado para avaliar o desempenho em relação a partes definidas do público-alvo.

Gráficos de ganho e incentivo são visualizações criadas para avaliar o desempenho potencial do modelo pontuado. Esses gráficos avaliam o desempenho em cada porção da população.

**Para abrir um gráfico de incentivo ou ganho**

1. Selecionar [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Passe o cursor do mouse sobre **[!UICONTROL Model Complete]** uma pontuação salva.

![](assets/propensity_lift_gain_1.png)

**Sobre os gráficos de incentivo e ganho**

Os Gráficos de Incentivo e Ganho são ferramentas visuais úteis para medir o valor de um modelo preditivo. Ambos os gráficos consistem em uma curva de elevação (verde) e uma linha de base (rosa). Para o Gráfico **de** Ganhos, a distância entre a curva de elevação e a linha de base representa o quanto você pode melhorar o desempenho nas respostas (ou o &quot; ganho&quot;) ao usar o modo preditivo. O ganho é realizado priorizando e direcionando os clientes potenciais (clientes/visitantes) com maior probabilidade de conversão, em vez de marketing para clientes/visitantes aleatório. Dessa forma, você pode quantificar o valor esperado de usar o modelo preditivo para escolher quais perspectivas entrar em contato.

Semelhante ao Gráfico de Ganhos, o Gráfico **de** Incentivos mostra a probabilidade de você receber respostas positivas maior do que se você contatasse as perspectivas aleatoriamente. Você deseja que a distância entre a curva de elevação e a linha de base seja o maior possível, representando maiores ganhos esperados com o uso do modelo preditivo para entrar em contato com os clientes. Matematicamente, os gráficos de ganho e incentivo são definidos da seguinte forma:

* **Ganho** = (Resposta Esperada usando Modelo Preditivo para Contatar Perspectivas) / (Resposta Esperada de Perspectivas de Contatos Aleatórios)
* **Elevação** = (Resposta esperada entre um Tamanho de Grupo Específico de Perspectivas identificado usando o Modelo Preditivo) / (Resposta esperada entre o mesmo Tamanho de Grupo Específico de Perspectivas identificado Aleatoriamente)

**Exemplo de Gráficos de Aumento e Ganho**

Por exemplo, considere o exemplo de um varejista que deseja lançar uma campanha de remarketing por email para vender calças de yoga. Historicamente, o analista espera uma taxa média de resposta de 20% com base em campanhas anteriores de remarketing por email semelhantes a essa. Embora o analista tenha quase 5 milhões de clientes em seu banco de dados de email, a empresa quer comercializar somente para os clientes que provavelmente responderão ao email e à compra. Dessa forma, a empresa maximizará o ROI da campanha e, ao mesmo tempo, garantirá que eles não enviem e-mails desnecessariamente para clientes desinteressados. Dada uma taxa de resposta esperada de 20%, o comerciante e analista esperam que aproximadamente 1 milhão de clientes respondam e comprem. Em vez de adivinhar aleatoriamente quais desses clientes estarão entre as 20% de respostas, o analista quer ser esperto sobre como prever qual entre as 1 milhão de perspectivas (entre as bases de dados de 5 milhões de clientes) tem maior probabilidade de responder.

Usando o recurso de Pontuação de público-alvo da Adobe, o analista define o sucesso como um cliente potencial clica em um email e compra calças de yoga (a variável dependente). Depois de selecionar as variáveis independentes (com base na experiência e no conhecimento obtido com a análise de correlações de dados e agrupamento de público-alvo entre outras análises), cada cliente potencial é pontuado na probabilidade de responder positivamente à campanha de remarketing por email (clicando no email e comprando yoga calça). O analista abre os gráficos Ganho e Levantamento resultantes com base no modelo preditivo.

O eixo y mostra a porcentagem das respostas positivas cumulativas esperadas. No nosso exemplo, esperamos um total de 1 milhão de respostas positivas. Um valor de 20% no eixo y corresponde a 20% dos 1 milhão de respostas positivas esperadas, ou 200 mil respostas positivas. O eixo x mostra a porcentagem de clientes em potencial contactados. Em nosso exemplo, o eixo x representa uma fração dos 5 milhões de clientes no banco de dados de email. A linha de base (cor-de-rosa) é a taxa de resposta geral - se você entrar em contato com X% dos clientes potenciais, então você receberá X% do total de respostas positivas. Usando o modelo preditivo, a curva de incentivo (verde) mostra a porcentagem de respostas positivas obtidas (eixo y) ao contatar uma porcentagem específica de perspectivas (eixo x).

O gráfico Lift representa o aumento esperado como resultado do uso do modelo preditivo para determinar o milhão de clientes potenciais com maior probabilidade de comprar calças yoga depois de receber e clicar no email. Para entrar em contato com 20 por cento das perspectivas selecionadas aleatoriamente usando um modelo preditivo, você deve esperar obter 20 por cento dos respondedores. No entanto, usando o modelo preditivo para identificar os 20% mais prováveis de responder, você espera obter 50% dos respondedores. O valor y da curva de elevação em 20% é 50/20 = 2,5. O gráfico de incentivo mostra o quanto você tem mais probabilidade de receber entrevistados do que se você entrar em contato com uma amostra aleatória de prospetos. Por exemplo, ao entrar em contato com apenas 20% das perspectivas com base no modelo preditivo, você atingirá 2,5 vezes mais entrevistados do que não ter usado nenhum modelo preditivo.
