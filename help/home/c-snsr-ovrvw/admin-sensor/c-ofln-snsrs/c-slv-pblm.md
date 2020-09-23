---
description: Quando um servidor da Web fica offline devido a uma falha, a solução é simples e requer um usuário Data Workbench com os privilégios apropriados para abrir o arquivo Log Processing Mode.cfg e adicionar a ID do Sensor (em nosso exemplo, WEB2) à seção "Fontes offline".
solution: Analytics
title: Resolver o problema
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---


# Resolver o problema{#solving-the-problem}

Quando um servidor da Web fica offline devido a uma falha, a solução é simples e requer um usuário Data Workbench com os privilégios apropriados para abrir o arquivo Log Processing Mode.cfg e adicionar a ID do Sensor (em nosso exemplo, WEB2) à seção &quot;Fontes offline&quot;.

Esta seção do arquivo diz ao [!DNL data workbench server] que ele não deve mais esperar dados dessa fonte, pois eles estão, na verdade, offline.

>[!NOTE]
>
>Essa alteração não precisa ser realizada por um consultor Adobe. Qualquer pessoa que tenha privilégios adequados para abrir o [!DNL Log Processing Mode.cfg] arquivo pode fazer essa alteração.

Se a WEB2 começar a enviar dados novamente, a [!DNL data workbench server] colocará a fonte novamente online e ajustará a Hora de início para refletir a última vez que recebeu dados de todas as fontes que ela conhece. Em outras palavras, novos dados entrando no sistema têm precedência sobre o que está escrito no [!DNL Log Processing Mode.cfg file].

Se a WEB2 voltar a ficar offline, a Hora de início será interrompida novamente e será necessário editar o [!DNL Log Processing Mode.cfg] arquivo novamente, mesmo que já tenha a WEB2 listada como uma fonte offline. Este é um artefato do design do produto de acordo com a definição de A partir do tempo: a última vez que o sistema tiver dados para todas as fontes conhecidas.

Quando você adiciona mais servidores da Web (WEB4, WEB5, WEB6) e eles começam a enviar dados para o [!DNL data workbench server], você não precisa fazer nada para que o [!DNL data workbench server] reconheça as novas fontes. O sistema apenas se apercebe de que deve esperar dados dessas novas fontes, conforme descrito acima.
