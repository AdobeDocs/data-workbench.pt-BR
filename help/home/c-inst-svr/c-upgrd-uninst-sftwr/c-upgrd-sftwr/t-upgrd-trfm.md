---
description: Etapas para atualizar a pasta Transform .
title: Atualizar transformação
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
exl-id: b5e21862-caf1-42e4-9247-c870d7b3180e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---

# Atualizar transformação{#upgrading-transform}

Etapas para atualizar a pasta Transform .

1. Abra o arquivo [!DNL .zip] para o pacote de versão [!DNL Insight Server] e abra a pasta [!DNL Profiles] dentro desse arquivo [!DNL .zip].
1. Copie a pasta [!DNL Transform] para a pasta [!DNL Profiles] no diretório de instalação [!DNL Insight Server]. Isso substitui a pasta [!DNL Transform] existente.
1. Para cada perfil que herda o perfil [!DNL Transform], confirme se o arquivo [!DNL profile.cfg] tem uma entrada &quot;Transformar&quot; no vetor Diretórios.
O reprocessamento de dados começa após a sincronização do perfil.
