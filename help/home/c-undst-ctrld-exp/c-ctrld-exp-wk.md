---
description: Em um experimento, você pode definir qualquer número de grupos de teste além do grupo de controle.
solution: Analytics,Analytics
title: Como funcionam os experimentos controlados?
topic: Data workbench
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---


# Como funcionam os experimentos controlados?{#how-do-controlled-experiments-work}

Em um experimento, você pode definir qualquer número de grupos de teste além do grupo de controle.

Quando um experimento é executado, todos os visitantes do seu site se tornam parte do experimento, seja como parte de um grupo de teste ou do grupo de controle, assim que acessam qualquer página envolvida no experimento. Os visitantes são alocados para seus grupos de experimentos aleatoriamente, em proporções definidas durante a configuração do experimento.

Os experimentos controlados são implementados usando o [!DNL Sensor] software instalado em cada um dos servidores de conteúdo no cluster da Web. Conforme os servidores de conteúdo recebem solicitações, [!DNL Sensor] seleciona aleatoriamente visitantes para seus grupos de teste e redireciona suas solicitações de página para o conteúdo experimental. Quando [!DNL Sensor] seleciona uma visitante para visualização do conteúdo de teste, a barra de endereços continua a lista do URI solicitado originalmente, mas o visitante é roteado para o URI de teste. Como esse processo ocorre internamente no aplicativo do servidor, os usuários não estão cientes de quando estão sendo testados, o que é uma consideração importante para uma experimentação imparcial.

[!DNL Sensor] passa os URIs de teste, não o URI original exibido ao usuário, para os arquivos de registro para uso na análise.

Os resultados dos experimentos podem ser analisados facilmente [!DNL Insight] para determinar se a hipótese experimental que você estava testando está correta.

>[!NOTE]
>
>A Adobe recomenda que os experimentos controlados sejam coordenados e executados com a participação dos indivíduos na sua organização responsáveis pela configuração e manutenção dos seus conjuntos de dados de análise.

