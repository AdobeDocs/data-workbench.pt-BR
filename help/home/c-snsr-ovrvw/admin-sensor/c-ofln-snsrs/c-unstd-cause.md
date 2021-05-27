---
description: Informações sobre como resolver problemas do servidor da Web, como, por exemplo, se o servidor da Web for tirado do giro ou se o servidor da Web falhar.
title: Compreender as causas
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
exl-id: 008116b0-7ef5-41ee-bd2e-a86d61acd634
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 2%

---

# Compreender as causas{#understanding-the-causes}

Informações sobre como resolver problemas do servidor da Web, como, por exemplo, se o servidor da Web for tirado do giro ou se o servidor da Web falhar.

## Quando um servidor da Web é tirado da rotação {#section-b9f709099cb44b4f9d1acb38ca5330e3}

Quando um servidor da Web é retirado do modo de rotação de um pool de servidores, mas de outra forma está conectado ao transmissor enviando pulsações periódicas, o tempo de início é mantido atualizado e nenhuma intervenção da parte de ninguém é necessária.

## Quando um servidor Web falha {#section-19280cf83ca44bd7b1ee11bfc74494d2}

Quando um servidor da Web está completamente offline devido a uma falha catastrófica ou não está enviando dados ou pulsações, a Data de início no [!DNL data workbench server] para para garantir que representa a última vez que o [!DNL data workbench server] recebeu dados de TODAS as fontes de dados que ele conhece. O próprio sistema continua a processar dados, que ainda estão disponíveis para análise no Data Workbench, mas qualquer item no [!DNL data workbench server] que seja baseado no tempo de início não funciona. Por exemplo, o a partir do tempo aciona o relatório e é usado para criar muitas dimensões derivadas no sistema. Quando o tempo de início for interrompido, o relatório não será acionado e essas dimensões derivadas específicas não estarão disponíveis.

Por exemplo, se a WEB2 ficasse offline em 15 de junho e não enviasse dados por cinco dias, a Data de início seria em algum momento em 15 de junho. A dimensão de Ontem, por exemplo, seria 14 de junho mesmo que a data de hoje seja 20 de junho.
