---
description: Métricas, dimensões e filtros fornecem uma estrutura na qual os cálculos são feitos sobre os dados processados em um conjunto de dados da análise de big data.
solution: Analytics
title: Métricas, dimensões e filtros do Análise de big data
topic: Data workbench
uuid: 3c0300a0-ae19-4817-aab8-7294e0eabdd9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Métricas, dimensões e filtros do Análise de big data{#data-workbench-metrics-dimensions-and-filters}

Métricas, dimensões e filtros fornecem uma estrutura na qual os cálculos são feitos sobre os dados processados em um conjunto de dados da análise de big data.

Os resultados dos cálculos definidos usando essa estrutura são mostrados em espaços de trabalho, painéis, relatórios ou outras saídas. Resumindo, qualquer número que você visualize em ou de um aplicativo é o resultado de uma consulta de um conjunto de dados que envolve uma métrica, uma dimensão e um filtro.

No nível mais básico, uma métrica descreve o que está sendo calculado a partir e sobre o conjunto de dados, uma dimensão divide os dados no conjunto de dados em categorias e um filtro descreve uma parte ou um subconjunto selecionado dos dados no conjunto de dados.

Quando o Servidor do Análise de big data processa dados para criar um conjunto de dados, as dimensões dos dados são criadas e atualizadas continuamente à medida que novos dados são lidos e processados pelo servidor. Métricas e filtros são calculados a partir dessas dimensões de dados.

>[!CAUTION]
>
>Se você redefinir uma métrica interna, o sistema se comportará inesperadamente devido ao valor errado. Seus relatórios não serão gerados a menos que uma métrica leia 100%. É recomendável que você não altere as definições de métricas.

## Um exemplo {#section-ecc465d1a5e34d559c1983e96fa409ec}

Imaginem um conjunto de dados que contém informação sobre todas as pessoas no mundo. Este conjunto de dados contém, no mínimo, todas as pessoas no mundo e suas idades. Uma métrica útil para calcular a partir desse conjunto de dados seria a Idade Média. A avaliação dessa métrica resultaria em um número: a idade média da população mundial.

Adicionar uma dimensão ao conjunto de dados torna essas informações mais úteis e gerenciáveis. Se o conjunto de dados também contiver o país de residência de cada pessoa, a definição de uma dimensão de País forneceria uma maneira de segmentar as pessoas em grupos para cada país no mundo. A avaliação da métrica Idade Média na dimensão País resultaria em uma lista de números, um para cada país, cada um representando a idade média das pessoas nesse país.

A aplicação de um filtro (ou filtro de seleção) em uma fórmula de métrica pode fornecer informações mais detalhadas ou permitir a definição de uma nova métrica com base nas métricas e dimensões existentes. A avaliação da métrica Idade Média com um filtro de &quot;onde país é igual à Suécia&quot; resulta em um número: a idade média das pessoas na Suécia. Uma métrica baseada nesse filtro pode ser a Idade Média Sueca.

Por exemplo:

```
Swedish_Average_Age=Average_Age[country = ‘Sweden’]
```

## Relação entre métricas, dimensões e filtros {#section-28622596124140b280e6b993b174ef84}

Em geral, avaliar uma métrica em uma dimensão resulta na avaliação dessa métrica para cada elemento de dimensão (ou elemento). No exemplo acima, a dimensão País tem um elemento para cada país do mundo. A avaliação da Idade Média em relação ao País resultaria na idade média de cada um dos elementos (países), incluindo o elemento Suécia.

É importante observar que, ao avaliar uma métrica sobre uma dimensão, você receberá o mesmo resultado numérico para um elemento de dimensão específico, independentemente de avaliar essa métrica para a dimensão inteira ou definir um filtro correspondente a esse elemento de dimensão específico. Usando o exemplo anterior, ao procurar a idade média das pessoas na Suécia, qualquer um dos métodos a seguir produziria resultados idênticos:

* Avalie a métrica Idade média na dimensão País e, em seguida, verifique o número do elemento de dimensão Suécia.
* Avalie a métrica Idade Média com um filtro de &quot;pessoas na Suécia&quot; (expresso como [!DNL Average_[AgeCountry=&#39;Suécia&#39;]]).

Os filtros são expressões sintáticas que fazem referência a uma ou mais dimensões e elementos de dimensão. Como você viu no exemplo acima, usar a expressão [!DNL [dimension=element]] é uma maneira fácil de especificar um filtro.

É igualmente fácil aplicar esse filtro para definir uma nova métrica usando uma expressão como [!DNL New_Metric=[MetricFilter]]. Esse filtro pode ser usado para definir uma nova métrica com base em um elemento de dimensão específico. Para usar o exemplo acima, [!DNL Average_[AgeCountry=&#39;Sweden&#39;]] especifica uma métrica para a idade média das pessoas na Suécia. Se atribuíssemos um nome a essa métrica, como sueco_average_Age, poderíamos usá-la em outros cálculos como uma métrica. Por exemplo, avaliar [!DNL Swedish_Average_Age/Average_Age] resultaria em um único número: a relação entre a idade média das pessoas na Suécia e a das pessoas no resto do mundo.

Se o conjunto de dados com informações sobre todas as pessoas no mundo também incluir uma dimensão Cor dos olhos, a expressão [!DNL Sweden_Average_[AgeEye_Color=&#39;green&#39;]] resultará na idade média dos suecos com olhos verdes. Você também pode obter esse mesmo resultado sem usar uma definição de métrica intermediária aplicando um filtro diferente: [!DNL Average_[AgeCountry=&#39;Sweden&#39; E Eye_Color=&#39;green&#39;]]. Nesse caso, o [!DNL AND] operador especifica uma expressão de filtro usando duas outras expressões de filtro básicas.
