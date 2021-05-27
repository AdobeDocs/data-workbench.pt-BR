---
description: Para alterar o servidor do Data Workbench com o qual um Sensor se comunica (o servidor de destino), edite o arquivo txlogd.conf em cada um dos servidores da Web em que o Sensor está instalado.
title: Alterar o servidor do Data Workbench do público alvo
uuid: 931d376d-8622-4858-8290-19ce91538570
exl-id: 9d18cae1-4037-48c6-8514-3278e2c73b47
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---

# Alterar o servidor do Data Workbench do público alvo{#changing-the-target-data-workbench-server}

Para alterar o servidor do Data Workbench com o qual um Sensor se comunica (o servidor de destino), edite o arquivo txlogd.conf em cada um dos servidores da Web em que o Sensor está instalado.

**Para alterar para o target[!DNL data workbench server]**

1. Pare o servidor de destino original e o novo servidor de destino.
1. Copie o arquivo [!DNL .vsl] mais atual do servidor de destino original para o novo servidor de destino. Ao reiniciar o novo servidor de destino em uma etapa posterior, isso faz com que todos os novos dados [!DNL Sensor] sejam anexados ao arquivo [!DNL .vsl] atual, em vez de criar um novo arquivo [!DNL .vsl]. Para fazer isso, conclua as seguintes etapas:

   1. No servidor de destino original, navegue até a pasta [!DNL \Logs] no diretório de instalação [!DNL data workbench server].

   1. Copie o arquivo [!DNL .vsl] mais atual na pasta .
   1. No novo servidor de destino, navegue até a pasta [!DNL \Logs] no diretório de instalação [!DNL data workbench server] e cole o arquivo [!DNL .vsl] nessa pasta.

1. Em um dos servidores da Web em que [!DNL Sensor] está instalado, abra e edite o arquivo [!DNL txlogd.conf]. Para fazer isso, conclua as seguintes etapas:

   1. Navegue até o diretório de instalação [!DNL Sensor] e abra o arquivo [!DNL txlogd.conf] em um editor de texto.

   1. Localize o parâmetro ServerAddress e altere-o para refletir o endereço do novo servidor de destino.
   1. Salve e feche o arquivo.

1. Repita as etapas 2 a 3 em todos os servidores da Web restantes nos quais [!DNL Sensor] está instalado.
1. Reinicie o servidor de destino original (se ele ainda estiver para ser usado) e o novo servidor de destino.
1. Os dados começarão a transmitir para o novo servidor de destino que você especificou.
