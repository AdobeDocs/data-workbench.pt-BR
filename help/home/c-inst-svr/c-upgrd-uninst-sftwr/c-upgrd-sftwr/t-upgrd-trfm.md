---
description: Etapas para atualizar a pasta Transform .
title: Atualizar transformação
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
exl-id: b5e21862-caf1-42e4-9247-c870d7b3180e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---

# Atualizar transformação{#upgrading-transform}

{{eol}}

Etapas para atualizar a pasta Transform .

1. Abra o [!DNL .zip] para o [!DNL Insight Server] liberar pacote e abrir o [!DNL Profiles] dentro dessa [!DNL .zip] arquivo.
1. Copie o [!DNL Transform] para [!DNL Profiles] na sua pasta [!DNL Insight Server] diretório de instalação. Isso substitui o [!DNL Transform] pasta.
1. Para cada perfil que herda a variável [!DNL Transform] confirme se a variável [!DNL profile.cfg] O arquivo tem uma entrada &quot;Transformar&quot; no vetor Diretórios .
O reprocessamento de dados começa após a sincronização do perfil.
