---
description: As métricas podem ser editadas usando o Editor de métricas e salvas no diretório Métricas de um perfil.
solution: Analytics
title: Sintaxe para expressões de métricas
topic: Data workbench
uuid: 801e265d-d7e4-4f0f-9698-d0b50dd00995
translation-type: tm+mt
source-git-commit: a276b16565634fea9b693206c8a55b528fada977
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 1%

---


# Sintaxe para expressões de métricas{#syntax-for-metric-expressions}

As métricas podem ser editadas usando o Editor de métricas e salvas no diretório Métricas de um perfil.

Para obter mais informações, consulte [Criação e edição de métricas](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40)derivadas. Expressões de métricas também podem ser usadas em planilhas. Para obter mais informações, consulte [Planilhas](../../../home/c-get-started/c-analysis-vis/c-wksts/c-wksts.md#concept-45b50aafc4d84709841f14aee8022581). A sintaxe a seguir é usada para definir expressões de métricas.

Notas:

1. As palavras sublinhadas devem ser digitadas literalmente no texto da expressão.
1. O formulário `{TEXT}?` representa o texto opcional.
1. O formulário `{TEXT}*` representa um texto que pode ocorrer zero ou mais vezes.
1. O formulário `{A | B | C |...}` representa o texto que consiste exatamente em uma das opções fornecidas, como A ou B ou C....
1. O formulário `[A,B)` representa um intervalo de números, de A até, mas não incluindo, B.

<table id="table_A6CA9C9F396448209398AA2A369E63FA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identificador </p> </td> 
   <td colname="col2"> <p>Um identificador faz referência a uma métrica nomeada. Para obter as regras que regem identificadores legais, consulte <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> Sintaxe para identificadores </a>. </p> <p>Exemplo: Receita = Total_Price </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(Métrica) </p> </td> 
   <td colname="col2"> <p>O resultado de (Métrica) é o mesmo que o resultado de Métrica. Os parênteses especificam a ordem das operações em uma expressão. </p> <p>Exemplo: Média = (A + B) / 2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A + B </p> </td> 
   <td colname="col2"> <p>Soma dos resultados da Métrica A e B. </p> <p>Exemplo: Valor = Receita + Custo_Economia </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A - B </p> </td> 
   <td colname="col2"> <p>Diferença dos resultados da Métrica A e B. </p> <p>Exemplo: Lucro = Receita - Custo </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A * B </p> </td> 
   <td colname="col2"> <p>Produto dos resultados das Métricas A e B. </p> <p>Exemplo: Dólares = Centavos * 0,01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A/B </p> </td> 
   <td colname="col2"> <p>Proporção dos resultados da Métrica A e da Métrica B. </p> <p>Exemplo: Receita_por_Sessão = Receita / Sessões </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A ^ B </p> </td> 
   <td colname="col2"> <p>Resultado da métrica A elevado à potência do resultado da métrica B. </p> <p>Exemplo: Área = Largura^2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>confidence(metric) </p> </td> 
   <td colname="col2"> <p>Uma estimativa do desvio padrão da métrica. Isto é calculado usando uma técnica de amostragem conhecida como jaquetagem. </p> <p>Essa métrica consome muita memória e não deve ser usada em tabelas grandes. </p> <p>Para usar essa sintaxe, você deve ter uma dimensão de canivete (chamada "canivete") com as propriedades apropriadas. Para obter mais informações, entre em contato com os Serviços de consultoria da Adobe. </p> <p>Exemplo: confidence(Average_Score) </p> <p> <p>Observação:  Os tipos de métricas de confiança, incluindo a confiança (métrica) e a confiança (métrica, Jacknife), são especialmente úteis ao usar a funcionalidade de experimentação controlada do Adobe. Se uma métrica saltasse de 12% para 16% durante um experimento controlado, você poderia usar uma chamada de confiança para calcular as probabilidades de que o salto fosse devido à variação aleatória. Isso pode ajudá-lo a evitar tirar conclusões erradas de evidências limitadas, e, inversamente, dar garantias de que uma mudança questionável é realmente real. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>confidence(metric, Jackfaca) </p> </td> 
   <td colname="col2"> <p>Uma estimativa do desvio padrão da métrica. Isto é calculado usando uma técnica de amostragem conhecida como jaquetagem. Essa sintaxe permite que você determine a confiança de uma métrica usando uma dimensão de canivete chamada algo diferente de "canivete". </p> <p>Essa métrica consome muita memória e não deve ser usada em tabelas grandes. </p> <p>Para usar essa sintaxe, você deve ter uma dimensão de canivete (chamada de algo diferente de "canivete") com as propriedades apropriadas. Para obter mais informações, entre em contato com os Serviços de consultoria da Adobe. </p> <p>Exemplo: confidence(Average_Score,SubSamples) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eval(CellReference) </p> </td> 
   <td colname="col2"> <p>Trata o conteúdo da célula que você está referenciando como uma expressão de métrica. Essa sintaxe pode ser usada somente em uma visualização de planilha. </p> <p>Exemplo: eval(B1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>log (B, X) </p> </td> 
   <td colname="col2"> <p>O logaritmo matemático funciona: A métrica X é o parâmetro e a métrica B é a base. </p> <p>Exemplo: dB = 20*log(Amplitude,10) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Métrica[Filtro] </p> </td> 
   <td colname="col2"> <p>"Métrica onde Filtro": Uma nova métrica filtrada pelo filtro fornecido. </p> <p>Exemplo: Jan_Sessions = Sessões[ Mês="Jan" ] </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Métrica por Dimension </p> </td> 
   <td colname="col2"> <p>Uma métrica avaliada no "nível" da dimensão. O resultado de (M por X)[F] (o resultado da métrica "M por X" avaliada com o Filtro "F") é o resultado de M[F por X] (o resultado da Métrica "M" avaliada com o Filtro "F por X"). </p> <p>Exemplo: AB_Visitantes = </p> <p>(Visitantes por sessão)[Página="A" e Página="B"] = </p> <p>Visitantes[(Page="A" e Page="B") por Sessão] = </p> <p>O número de Visitantes que visitaram as páginas A e B na mesma sessão. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>número </p> </td> 
   <td colname="col2"> <p>Uma métrica com um valor fixo. </p> <p>Exemplo: Pi = 3,1415 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total (Métrica) </p> </td> 
   <td colname="col2"> <p>Ignora qualquer dimensão sobre a qual a métrica é avaliada. A métrica tem o mesmo valor para cada elemento dessa dimensão. </p> <p>Exemplo: Pct_of_Visitantes = Visitantes / total(Visitantes) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>all(Métrica) </p> </td> 
   <td colname="col2"> <p>Ignora filtros que se aplicam à métrica. A métrica não é afetada pelas seleções e outros filtros. </p> <p>Exemplo: Benchmark_Sessions = all( Sessões ) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(all(Metric)) </p> </td> 
   <td colname="col2"> <p>Ignora todos os filtros e dimensões. Ele tem o mesmo valor em um determinado perfil, independentemente dos filtros ou dimensões aplicados. </p> <p>Exemplo: Dataset_Visitantes = total(todos(Visitantes)) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(One,Countable_Dimension) </p> </td> 
   <td colname="col2"> <p>Uma métrica que fornece a contagem de uma dimensão contável, como Visitante ou Sessão. </p> <p>Exemplo: Visitantes = sum(Um,Visitante) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(Numeric_ Dimension, Countable_ Dimension) </p> </td> 
   <td colname="col2"> <p>Uma métrica que fornece a soma de uma dimensão numérica sobre uma dimensão contável. Os valores ordinais (em oposição aos valores formatados) dos elementos da dimensão numérica são usados, portanto um fator de escala geralmente precisa ser aplicado ao resultado. </p> <p>Exemplo: Valor = sum(Session_Value, Session)*0.01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>min(A, B) </p> </td> 
   <td colname="col2"> <p>Os resultados menores da métrica A e B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>max(A, B) </p> </td> 
   <td colname="col2"> <p>O maior dos resultados das métricas A e B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>format(A, B) </p> </td> 
   <td colname="col2"> <p>Uma métrica idêntica à métrica A, exceto que usa a função de formatação da métrica B. </p> </td> 
  </tr> 
 </tbody> 
</table>

