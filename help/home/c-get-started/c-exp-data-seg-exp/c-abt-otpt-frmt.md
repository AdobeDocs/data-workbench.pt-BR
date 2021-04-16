---
description: Diretrizes para especificar o formato de saída.
title: Formato de saída
uuid: 12086f14-bad1-4d27-82fb-533e877d0a04
exl-id: e695eaf4-ebe5-4dd1-8191-8045021d6411
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 1%

---

# Formato de saída{#output-format}

Diretrizes para especificar o formato de saída.

* Cada métrica ou nome de dimensão deve começar e terminar com um sinal de porcentagem (%).

   * %XYZ% especifica o elemento da dimensão XYZ correspondente ao elemento de Nível. Um erro é gerado se a dimensão XYZ não for um para um ou um para muitos com Nível.
   * %=XYZ% especifica o valor da fórmula de métrica ou métrica XYZ para o elemento especificado de Nível.

* Nomes de Dimension que sejam duas palavras ou mais não exigem sublinhados.
* Nomes de métricas que sejam duas palavras ou mais exigem sublinhados.

>[!NOTE]
>
>Se você pressionar a tecla Ctrl e clicar com o botão direito do mouse no campo [!DNL Output Format], um [!DNL Insert menu] é exibido. Esse menu contém uma lista de caracteres especiais (por exemplo, Guia) que geralmente são usados como delimitadores.

Se quiser exportar dados de duração da sessão para o seu segmento, crie uma nova métrica com base na métrica Duração da sessão . A nova métrica, que é para ser usada somente com o campo [!DNL Output Format] de exportação de segmento, permite que o Microsoft Excel interprete corretamente as sessões que duram menos de uma hora. Para criar uma nova métrica de duração da sessão, abra o arquivo [!DNL Session Duration.metric] (a partir de [!DNL Profile Manager]) e insira um sinal de número (#) na string de hora: [!DNL ftime = string: %#H:%M:%S]

O sinal de número faz com que um &quot;0&quot; à esquerda seja anexado a durações de sessão inferiores a 1 hora. Como resultado, o Excel interpreta 0:53:21 como 53 minutos e 21 segundos. Salve a nova métrica com um nome diferente e faça upload dela no perfil apropriado para que outras pessoas possam usá-la clicando com o botão direito do mouse na marca de seleção do arquivo na coluna [!DNL User] e clicando em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***.
