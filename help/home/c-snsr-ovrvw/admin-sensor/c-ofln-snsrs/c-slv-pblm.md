---
description: Quando um servidor da Web fica offline por causa de uma falha, a solução é simples e requer um usuário do Data Workbench com privilégios adequados para abrir o arquivo Log Processing Mode.cfg e adicionar a ID do Sensor (em nosso exemplo, WEB2) à seção "Fontes offline".
title: Resolver o problema
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Resolver o problema{#solving-the-problem}

{{eol}}

Quando um servidor da Web fica offline por causa de uma falha, a solução é simples e requer um usuário do Data Workbench com privilégios adequados para abrir o arquivo Log Processing Mode.cfg e adicionar a ID do Sensor (em nosso exemplo, WEB2) à seção &quot;Fontes offline&quot;.

Esta seção do arquivo informa ao [!DNL data workbench server] que ele não deve mais esperar dados dessa fonte porque ela está, de fato, offline.

>[!NOTE]
>
>Essa alteração não precisa ser executada por um consultor Adobe. Qualquer pessoa que tenha privilégios adequados para abrir o [!DNL Log Processing Mode.cfg] pode fazer essa alteração.

Se a WEB2 começar a enviar dados novamente, a variável [!DNL data workbench server] O traz a fonte de volta para o modo online e ajusta a Hora de início para refletir a última vez que recebeu dados de todas as fontes que tem conhecimento. Em outras palavras, novos dados que entram no sistema têm precedência sobre os que estão escritos na [!DNL Log Processing Mode.cfg file].

Se a WEB2 voltar a ficar offline, o A partir do tempo voltará a parar e será necessário editar a variável [!DNL Log Processing Mode.cfg] novamente, mesmo que já tenha o WEB2 listado como uma fonte offline. Trata-se de um artefato do design do produto, em conformidade com a definição do tempo de início: a última vez que o sistema tiver dados para todas as fontes conhecidas.

Quando você adiciona mais servidores da Web (WEB4, WEB5, WEB6) e eles começam a enviar dados para a [!DNL data workbench server], você não precisa fazer nada para ter a variável [!DNL data workbench server] reconhecer as novas fontes. O sistema simplesmente sabe que deve estar esperando dados dessas novas fontes, conforme descrito acima.
