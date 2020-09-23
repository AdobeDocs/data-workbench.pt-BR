---
description: Para alterar o servidor de análise de big data com o qual um sensor se comunica (o servidor do público alvo), edite o arquivo txlogd.conf em cada um dos servidores da Web nos quais o Sensor está instalado.
solution: Analytics
title: Alterar o servidor do Data Workbench do público alvo
uuid: 931d376d-8622-4858-8290-19ce91538570
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---


# Alterar o servidor do Data Workbench do público alvo{#changing-the-target-data-workbench-server}

Para alterar o servidor de análise de big data com o qual um sensor se comunica (o servidor do público alvo), edite o arquivo txlogd.conf em cada um dos servidores da Web nos quais o Sensor está instalado.

**Para alterar para o público alvo[!DNL data workbench server]**

1. Pare o servidor de públicos alvos original e o novo servidor de públicos alvos.
1. Copie o arquivo mais atual do servidor de públicos alvos original para o novo servidor de públicos alvos. [!DNL .vsl] Ao reiniciar o novo servidor de públicos alvos em uma etapa posterior, isso faz com que todos os novos [!DNL Sensor] dados sejam anexados ao arquivo atual e existente, em vez de criar um novo [!DNL .vsl] [!DNL .vsl] arquivo. Para isso, execute as seguintes etapas:

   1. No servidor de público alvo original, navegue até a [!DNL \Logs] pasta no diretório de [!DNL data workbench server] instalação.

   1. Copie o [!DNL .vsl] arquivo mais atual na pasta.
   1. No novo servidor de públicos alvos, navegue até a [!DNL \Logs] pasta no diretório de [!DNL data workbench server] instalação e cole o arquivo nessa [!DNL .vsl] pasta.

1. Em um dos servidores da Web nos quais [!DNL Sensor] está instalado, abra e edite o [!DNL txlogd.conf] arquivo. Para isso, execute as seguintes etapas:

   1. Navegue até o diretório de [!DNL Sensor] instalação e abra o [!DNL txlogd.conf] arquivo em um editor de texto.

   1. Localize o parâmetro ServerAddress e altere-o para refletir o endereço do novo servidor de públicos alvos.
   1. Salve e feche o arquivo.

1. Repita as etapas de 2 a 3 em todos os servidores da Web restantes nos quais [!DNL Sensor] está instalado.
1. Reinicie o servidor de públicos alvos original (se ainda estiver para ser usado) e o novo servidor de públicos alvos.
1. Os dados começarão a ser transmitidos para o novo servidor de públicos alvos especificado.
