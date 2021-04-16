---
description: Quando um servidor da Web fica offline por causa de uma falha, a solução é simples e requer um usuário do Data Workbench com privilégios adequados para abrir o arquivo Log Processing Mode.cfg e adicionar a ID do Sensor (em nosso exemplo, WEB2) à seção "Fontes offline".
title: Resolver o problema
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Resolver o problema{#solving-the-problem}

Quando um servidor da Web fica offline por causa de uma falha, a solução é simples e requer um usuário do Data Workbench com privilégios adequados para abrir o arquivo Log Processing Mode.cfg e adicionar a ID do Sensor (em nosso exemplo, WEB2) à seção &quot;Fontes offline&quot;.

Esta seção do arquivo informa ao [!DNL data workbench server] que ele não deve mais esperar dados dessa fonte, pois ele está, de fato, offline.

>[!NOTE]
>
>Essa alteração não precisa ser executada por um consultor Adobe. Qualquer pessoa que tenha privilégios adequados para abrir o arquivo [!DNL Log Processing Mode.cfg] pode fazer essa alteração.

Se a WEB2 começar a enviar dados novamente, o [!DNL data workbench server] volta a colocar a fonte online e ajusta a Hora de início para refletir a última vez que recebeu dados de todas as origens de que tem conhecimento. Em outras palavras, os novos dados que entram no sistema têm precedência sobre os que estão escritos em [!DNL Log Processing Mode.cfg file].

Se a WEB2 voltar a ficar offline, a A partir do tempo será interrompida novamente e será necessário editar o arquivo [!DNL Log Processing Mode.cfg] novamente, mesmo que já tenha a WEB2 listada como uma fonte offline. Trata-se de um artefato do design do produto, em conformidade com a definição do tempo de início: a última vez que o sistema tiver dados para todas as fontes conhecidas.

Quando você adiciona mais servidores da Web (WEB4, WEB5, WEB6) e eles começam a enviar dados para o [!DNL data workbench server], não é necessário fazer nada para que o [!DNL data workbench server] reconheça as novas fontes. O sistema simplesmente sabe que deve estar esperando dados dessas novas fontes, conforme descrito acima.
