---
description: Informações sobre como resolver problemas do servidor da Web, como, por exemplo, se o servidor da Web estiver fora de rotação ou se o servidor da Web falhar.
solution: Insight
title: Compreensão das causas
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Compreensão das causas{#understanding-the-causes}

Informações sobre como resolver problemas do servidor da Web, como, por exemplo, se o servidor da Web estiver fora de rotação ou se o servidor da Web falhar.

## Quando um servidor Web é tirado da rotação {#section-b9f709099cb44b4f9d1acb38ca5330e3}

Quando um servidor da Web é tirado da rotação de um pool de servidores, mas está conectado ao transmissor enviando pulsações periódicas, o tempo de início é mantido atualizado e nenhuma intervenção de qualquer pessoa é necessária.

## Quando um Servidor Web falha {#section-19280cf83ca44bd7b1ee11bfc74494d2}

Quando um servidor da Web está completamente offline devido a alguma falha catastrófica, ou não está enviando dados ou pulsações, o tempo de início da página [!DNL data workbench server] para garantir que representa a última vez que os dados [!DNL data workbench server] recebidos de TODAS as fontes de dados são conhecidos. O próprio sistema continua processando dados, que ainda estão disponíveis para análise na Análise de big data, mas qualquer coisa na [!DNL data workbench server] qual se baseia a data de início não funciona. Por exemplo, a Hora de início aciona os relatórios e é usada para criar muitas dimensões derivadas no sistema. Quando o tempo de início for interrompido, o relatório não será acionado e essas dimensões derivadas específicas não estarão disponíveis.

Por exemplo, se a WEB2 ficasse offline em 15 de junho e não enviasse dados por cinco dias, a data de início seria em 15 de junho. A dimensão de Ontem, por exemplo, seria 14 de junho, mesmo que a data de hoje seja 20 de junho.
