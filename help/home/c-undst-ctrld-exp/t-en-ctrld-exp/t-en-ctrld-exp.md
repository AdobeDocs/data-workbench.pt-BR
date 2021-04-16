---
description: Para habilitar a experimentação controlada, alguém com acesso de administrador à Web ou aos servidores de aplicativos deve modificar o parâmetro ExpFile no arquivo de configuração do Sensor (normalmente nomeado usando txlogd.conf) em cada servidor da Web ou de aplicativos em seu cluster da Web em que um Sensor está instalado.
solution: Analytics,Analytics
title: Ativar experimento controlado
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
exl-id: 53c18524-6050-4708-af63-9e8ef8da389e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 2%

---

# Ativar experimento controlado{#enabling-controlled-experimentation}

Para habilitar a experimentação controlada, alguém com acesso de administrador à Web ou aos servidores de aplicativos deve modificar o parâmetro ExpFile no arquivo de configuração do Sensor (normalmente nomeado usando txlogd.conf) em cada servidor da Web ou de aplicativos em seu cluster da Web em que um Sensor está instalado.

Além disso, dois outros parâmetros neste arquivo podem ser modificados para implementar uma ferramenta de teste (parâmetro ExpCookieURL) ou para remapear grandes seções do seu site (parâmetro ExpPartialMatch). Este capítulo fornece mais informações sobre esses parâmetros.

**Para editar o arquivo txlogd.conf**

Se você tiver acesso de administrador, conclua as etapas a seguir. Se você não tiver acesso de administrador, entre em contato com o arquiteto do sistema para solicitar as alterações, fornecendo as seguintes etapas.

1. Navegue até a pasta de instalação [!DNL Sensor] em um servidor da Web ou de aplicativos no cluster da Web em que [!DNL Sensor] está instalado.
1. Abra o arquivo de configuração [!DNL Sensor] (normalmente nomeado usando [!DNL txlogd.conf]) usando um editor de texto e edite o arquivo, conforme indicado em [Modificando o parâmetro ExpFile](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

   (Opcionalmente em [Modificando o parâmetro ExpCookieURL (Opcional)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) e [Modificando o parâmetro ExpPartialMatch (Opcional)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e).)

1. Salve e feche o arquivo.
1. Repita esse procedimento para cada servidor da Web ou de aplicativos no cluster da Web em que [!DNL Sensor] está instalado.
