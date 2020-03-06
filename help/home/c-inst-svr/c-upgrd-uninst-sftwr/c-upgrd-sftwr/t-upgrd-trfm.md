---
description: Etapas para atualizar a pasta Transform.
solution: Insight
title: Atualização da transformação
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Atualização da transformação{#upgrading-transform}

Etapas para atualizar a pasta Transform.

1. Abra o [!DNL .zip] arquivo do pacote de [!DNL Insight Server] versão e abra a [!DNL Profiles] pasta dentro desse [!DNL .zip] arquivo.
1. Copie a [!DNL Transform] pasta para a [!DNL Profiles] pasta no diretório [!DNL Insight Server] de instalação. Isso substitui a [!DNL Transform] pasta existente.
1. Para cada perfil que herda o [!DNL Transform] perfil, confirme se o [!DNL profile.cfg] arquivo tem uma entrada &quot;Transformar&quot; no vetor Diretórios.
O reprocessamento de dados é iniciado após a sincronização do perfil.
