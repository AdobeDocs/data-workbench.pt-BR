---
description: Antes de configurar o experimento, você deve criar o conteúdo alternativo que deseja usar no experimento.
solution: Analytics
title: Criar o conteúdo de teste
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
exl-id: fd46c6af-37e8-452a-880d-147b7d0cfe21
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 4%

---

# Criar o conteúdo de teste{#creating-the-test-content}

Antes de configurar o experimento, você deve criar o conteúdo alternativo que deseja usar no experimento.

O grupo de controle é enviado para o URI original, enquanto o grupo de teste é enviado para o URI novo e alternativo.

Para evitar confusão, não reutilize nomes de arquivo de grupo de teste. Por exemplo, se você executar um experimento usando um arquivo de grupo de teste chamado [!DNL test2.asp], não use [!DNL test2.asp] como o nome do arquivo de teste em seu próximo experimento.

Para a hipótese de que mover o link gráfico &quot;Solicitar uma demonstração&quot; em sua página inicial afeta a Conversão do visitante, criamos a página inicial alternativa contendo o link gráfico &quot;Solicitar uma demonstração&quot; na nova posição. A seção a seguir descreve como você especifica o URI do grupo de controle [!DNL index.asp] ser substituído pelo URI do grupo de teste [!DNL index2.asp] para um determinado percentual de visitantes.
