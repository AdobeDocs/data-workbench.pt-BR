---
description: Diretrizes para especificar o formato de saída.
solution: Analytics
title: Formato de saída
topic: Data workbench
uuid: 12086f14-bad1-4d27-82fb-533e877d0a04
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Formato de saída{#output-format}

Diretrizes para especificar o formato de saída.

* Cada métrica ou nome de dimensão deve começar e terminar com um sinal de porcentagem (%).

   * %XYZ% especifica o elemento da dimensão XYZ correspondente ao elemento de Nível. Um erro é gerado se a dimensão XYZ não for um para um ou um para muitos com Nível.
   * %=XYZ% especifica o valor da métrica ou da fórmula de métrica XYZ para o elemento especificado de Nível.

* Nomes de dimensões com duas palavras ou mais não exigem sublinhados.
* Nomes de métricas com duas palavras ou mais exigem sublinhados.

>[!NOTE]
>
>Se você mantiver pressionada a tecla Ctrl e clicar com o botão direito do mouse no [!DNL Output Format] campo, um [!DNL Insert menu] será exibido. Esse menu contém uma lista de caracteres especiais (por exemplo, Guia) que são usados com frequência como delimitadores.

Se quiser exportar dados de duração da sessão para o seu segmento, você deve criar uma nova métrica com base na métrica Duração da sessão. A nova métrica, que é usada somente com o [!DNL Output Format] campo de exportação de segmentos, permite que o Microsoft Excel interprete corretamente as sessões que duram menos de uma hora. Para criar uma nova métrica de duração da sessão, abra o [!DNL Session Duration.metric] arquivo (a partir do [!DNL Profile Manager]) e insira um sinal de número (#) na string de hora: [!DNL ftime = string: %#H:%M:%S]

O sinal de número zero faz com que um &quot;0&quot; à esquerda seja anexado a durações de sessão inferiores a 1 hora. Como resultado, o Excel interpreta 0:53:21 como 53 minutos e 21 segundos. Salve a nova métrica com um nome diferente e carregue-a no perfil apropriado para que outras pessoas possam usá-la clicando com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] coluna e clicando em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.
