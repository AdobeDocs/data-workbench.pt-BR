---
description: Para ajudar com as estatísticas, o Data Workbench fornece três medidas estatísticas na visualização da análise guiada.
title: Medidas estatísticas
uuid: a8782cd2-d657-4c04-9c5d-8e0af2a3b76e
exl-id: 166ff98b-d531-4b31-897e-0c7fedbd2f4d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 0%

---

# Medidas estatísticas{#statistical-measures}

Para ajudar com as estatísticas, o Data Workbench fornece três medidas estatísticas na visualização da análise guiada.

>[!NOTE]
>
>Embora a matemática possa ajudar você a fazer julgamentos sobre as correlações em seus dados, o contexto em torno dos dados também deve ser levado em consideração.

* **Chi Sq** é um teste de significância estatística que controla a aparência da marca de seleção na visualização. Matematicamente, é uma probabilidade de rejeitarmos a hipótese nula, que afirma que as diferenças observadas entre os dois grupos podem ser explicadas por variação aleatória. Praticamente, se o valor p de Qui Sq for menor que quase 100%, podemos ignorar a correlação independentemente de sua força medida (conforme descrito nas seções de estatística U e V a seguir).
* **A** estatística U é uma medida da força da correlação estatística. Matematicamente, ela vem de um ramo da matemática chamado teoria da informação e está intimamente relacionada ao conceito de informação mútua entre as distribuições dos dois grupos. Em alternativa, pode considerar-se que é a compressibilidade de um grupo, dado um sistema de codificação ideal para o outro grupo. Praticamente, essa medida tem um desempenho muito bom no caso comum de uma dimensão com muitos elementos contendo poucos visitantes. A medida varia de 0 (fraco) a 1 (forte).
* **A** estatística V é também uma medida da força da correlação estatística. Matematicamente, está relacionada à estatística V de Cramer familiar, diferindo apenas por uma etapa de normalização destinada a melhorar a simetria da medida em relação à inversão de seleção. Praticamente, esta medida funciona razoavelmente bem com muitos tipos de dimensões e está relacionada com uma medida estatística de uso corrente. A medida varia de 0 (fraco) a 1 (forte).

>[!NOTE]
>
>As estatísticas U e V foram selecionadas para se complementarem — cada uma ajustada para detectar tipos de correlações às quais a outra pode não responder com tanta intensidade.

Usando essa visualização como guia, você pode adicionar outras visualizações ao seu espaço de trabalho para fornecer mais informações sobre seus dados com base na seleção.

O exemplo [!DNL Site] a seguir contém um gráfico de barras que mostra as sessões para dias em janeiro, fevereiro, março e abril. Observe que um dia em janeiro está selecionado.

![](assets/vis_GuidedAnalysis_withVis.png)

A visualização da análise guiada no canto inferior esquerdo do espaço de trabalho indica que a dimensão Número de sessão fornece informações úteis sobre o dia selecionado.

Ao examinar o gráfico de barras Número de sessão no canto inferior direito do espaço de trabalho, é possível ver que os dados do Número de sessão 2 são muito inferiores ao referencial. Assim, podemos concluir que, como porcentagem, menos segundas sessões ocorreram no dia selecionado do que é normal. Para exibir um gráfico de barras para qualquer uma das dimensões listadas na visualização da análise guiada, basta selecionar a dimensão clicando na dimensão com o mouse.
