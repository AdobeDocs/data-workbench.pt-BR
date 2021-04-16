---
description: Antes de configurar o experimento, você deve criar o conteúdo alternativo que deseja usar no experimento.
solution: Analytics,Analytics
title: Criar o conteúdo de teste
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
exl-id: fd46c6af-37e8-452a-880d-147b7d0cfe21
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 4%

---

# Criar o conteúdo de teste{#creating-the-test-content}

Antes de configurar o experimento, você deve criar o conteúdo alternativo que deseja usar no experimento.

O grupo de controle é enviado para o URI original, enquanto o grupo de teste é enviado para o URI novo e alternativo.

Para evitar confusão, não reutilize nomes de arquivo de grupo de teste. Por exemplo, se você executar um experimento usando um arquivo de grupo de teste chamado [!DNL test2.asp], não use [!DNL test2.asp] como o nome do arquivo de teste no próximo experimento.

Para a hipótese de que mover o link gráfico &quot;Solicitar uma demonstração&quot; em sua página inicial afeta a Conversão do visitante, criamos a página inicial alternativa contendo o link gráfico &quot;Solicitar uma demonstração&quot; na nova posição. A seção a seguir descreve como você especifica que o URI do grupo de controle [!DNL index.asp] seja substituído pelo URI do grupo de teste [!DNL index2.asp] para uma porcentagem específica de visitantes.
