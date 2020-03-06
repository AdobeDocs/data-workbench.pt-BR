---
description: Em um experimento, você pode definir qualquer número de grupos de teste além do grupo de controle.
solution: Insight,Analytics
title: Como funcionam os experimentos controlados?
topic: Data workbench
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Como funcionam os experimentos controlados?{#how-do-controlled-experiments-work}

Em um experimento, você pode definir qualquer número de grupos de teste além do grupo de controle.

Quando um experimento é executado, todos os visitantes do seu site se tornam parte do experimento, seja como parte de um grupo de teste ou do grupo de controle, assim que acessam qualquer página envolvida no experimento. Os visitantes são alocados para seus grupos de experimentos aleatoriamente, em proporções definidas durante a configuração do experimento.

Os experimentos controlados são implementados usando o [!DNL Sensor] software instalado em cada um dos servidores de conteúdo no cluster da Web. Conforme os servidores de conteúdo recebem solicitações, [!DNL Sensor] seleciona aleatoriamente os visitantes para seus grupos de teste e redireciona suas solicitações de página para o conteúdo experimental. Quando [!DNL Sensor] seleciona um visitante para exibir o conteúdo de teste, a barra de endereços continua a listar o URI solicitado originalmente, mas o visitante é direcionado para o URI de teste. Como esse processo ocorre internamente no aplicativo do servidor, os usuários não estão cientes de quando estão sendo testados, o que é uma consideração importante para uma experimentação imparcial.

[!DNL Sensor] passa os URIs de teste, não o URI original exibido ao usuário, para os arquivos de log para uso na análise.

Os resultados dos experimentos podem ser analisados facilmente [!DNL Insight] para determinar se a hipótese experimental que você estava testando está correta.

>[!NOTE]
>
>A Adobe recomenda que os experimentos controlados sejam coordenados e executados com informações daqueles indivíduos em sua organização responsáveis pela configuração e manutenção de seus conjuntos de dados de análise.

