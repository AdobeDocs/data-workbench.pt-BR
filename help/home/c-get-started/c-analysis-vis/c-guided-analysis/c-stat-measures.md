---
description: Para ajudar com as estatísticas, a Análise de big data fornece três medidas estatísticas na visualização da análise guiada.
solution: Analytics
title: Medidas estatísticas
topic: Data workbench
uuid: a8782cd2-d657-4c04-9c5d-8e0af2a3b76e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Medidas estatísticas{#statistical-measures}

Para ajudar com as estatísticas, a Análise de big data fornece três medidas estatísticas na visualização da análise guiada.

>[!NOTE]
>
>Embora a matemática possa ajudá-lo a fazer julgamentos sobre as correlações em seus dados, o contexto que envolve os dados também deve ser considerado.

* **Chi Sq p** é um teste de significância estatística que controla a aparência da marca de seleção na visualização. Matematicamente, é uma probabilidade de rejeitarmos a hipótese nula, que diz que as diferenças observadas entre os dois grupos podem ser explicadas por variação aleatória. Praticamente, se o valor de p Qui Sq for inferior a quase 100%, podemos ignorar a correlação independentemente da sua intensidade medida (conforme descrito nas seguintes seções estatísticas U e V).
* **A estatística** U é uma medida da força da correlação estatística. Matematicamente, ele provém de um ramo da matemática chamado teoria da informação e está intimamente relacionado ao conceito de informação mútua entre as distribuições dos dois grupos. Em alternativa, pode considerar-se que é a compressibilidade de um grupo, dado um esquema de codificação ótimo para o outro grupo. Praticamente, essa medida tem um bom desempenho no caso comum de uma dimensão com muitos elementos que contêm poucos visitantes. A medida varia de 0 (fraco) a 1 (forte).
* **A estatística** V é também uma medida da força da correlação estatística. Matematicamente, está relacionado à estatística V de Cramer, que difere apenas por uma etapa de normalização destinada a melhorar a simetria da medida em relação à inversão de seleção. Praticamente, esta medida funciona razoavelmente bem com muitos tipos de dimensões e está relacionada com uma medida estatística de uso comum. A medida varia de 0 (fraco) a 1 (forte).

>[!NOTE]
>
>As estatísticas U e V foram selecionadas para complementarem uma à outra — cada uma ajustada para detectar tipos de correlações às quais a outra pode não responder com a mesma intensidade.

Usando essa visualização como guia, você pode adicionar outras visualizações à sua área de trabalho para fornecer mais informações sobre seus dados com base na seleção.

O [!DNL Site] exemplo a seguir contém um gráfico de barras que mostra as sessões para dias em janeiro, fevereiro, março e abril. Observe que um dia em janeiro é selecionado.

![](assets/vis_GuidedAnalysis_withVis.png)

A visualização da análise guiada no canto inferior esquerdo da área de trabalho indica que a dimensão Número da sessão fornece informações úteis sobre o dia selecionado.

Examinando o gráfico de barras Número da Sessão no canto inferior direito da área de trabalho, você pode ver que os dados para o Número da Sessão 2 são muito menores que o benchmark. Assim, podemos concluir que, como uma porcentagem, menos segundos de sessões ocorreram no dia selecionado do que é normal. Para exibir um gráfico de barras para qualquer uma das dimensões listadas na visualização da análise guiada, basta selecionar a dimensão clicando na dimensão com o mouse.
