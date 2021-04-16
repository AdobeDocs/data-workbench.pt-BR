---
description: Em um experimento, você pode definir qualquer número de grupos de teste além do grupo de controle.
solution: Analytics,Analytics
title: Como funcionam os experimentos controlados?
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
exl-id: 1d3af6a2-078e-4eb8-848e-685f531a60c5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---

# Como funcionam os experimentos controlados?{#how-do-controlled-experiments-work}

Em um experimento, você pode definir qualquer número de grupos de teste além do grupo de controle.

Quando um experimento está em execução, todos os visitantes do seu site se tornam parte do experimento, seja como parte de um grupo de teste ou do grupo de controle, assim que acessam qualquer página envolvida no experimento. Os visitantes são alocados aos grupos de experimento aleatoriamente, em proporções definidas durante a configuração do experimento.

Experimentos controlados são implementados usando o software [!DNL Sensor] instalado em cada um dos servidores de conteúdo em seu cluster da Web. À medida que os servidores de conteúdo recebem solicitações, [!DNL Sensor] seleciona aleatoriamente visitantes para seus grupos de teste e redireciona suas solicitações de página para o conteúdo experimental. Quando [!DNL Sensor] seleciona um visitante para visualizar o conteúdo de teste, a barra de endereços continua a listar o URI solicitado originalmente, mas o visitante é roteado para o URI de teste. Como esse processo ocorre internamente no aplicativo do servidor, os usuários não estão cientes de quando estão sendo testados, o que é uma consideração importante para a experimentação imparcial.

[!DNL Sensor] O transmite os URIs de teste, não o URI original exibido ao usuário, para os arquivos de log para uso na análise.

Os resultados dos experimentos podem ser analisados facilmente usando [!DNL Insight] para determinar se a hipótese experimental que você estava testando está correta.

>[!NOTE]
>
>A Adobe recomenda que os experimentos controlados sejam coordenados e executados com a entrada dos indivíduos em sua organização responsáveis pela configuração e manutenção dos conjuntos de dados de análise.
