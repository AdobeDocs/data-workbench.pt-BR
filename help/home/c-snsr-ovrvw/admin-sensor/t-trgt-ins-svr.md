---
description: Para alterar o servidor do Data Workbench com o qual um Sensor se comunica (o servidor de destino), edite o arquivo txlogd.conf em cada um dos servidores da Web em que o Sensor está instalado.
title: Alterar o servidor do Data Workbench do público alvo
uuid: 931d376d-8622-4858-8290-19ce91538570
exl-id: 9d18cae1-4037-48c6-8514-3278e2c73b47
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---

# Alterar o servidor do Data Workbench do público alvo{#changing-the-target-data-workbench-server}

{{eol}}

Para alterar o servidor do Data Workbench com o qual um Sensor se comunica (o servidor de destino), edite o arquivo txlogd.conf em cada um dos servidores da Web em que o Sensor está instalado.

**Para alterar para o target[!DNL data workbench server]**

1. Pare o servidor de destino original e o novo servidor de destino.
1. Copiar o mais atual [!DNL .vsl] do servidor de destino original para o novo servidor de destino. Ao reiniciar o novo servidor de destino em uma etapa posterior, isso causa todos os novos [!DNL Sensor] dados a serem anexados ao atual, existente [!DNL .vsl] em vez de criar um novo [!DNL .vsl] arquivo. Para fazer isso, conclua as seguintes etapas:

   1. No servidor de destino original, navegue até o [!DNL \Logs] na pasta [!DNL data workbench server] diretório de instalação.

   1. Copiar o mais atual [!DNL .vsl] na pasta.
   1. No novo servidor de destino, navegue até o [!DNL \Logs] na pasta [!DNL data workbench server] diretório de instalação e cole o [!DNL .vsl] para esta pasta.

1. Em um dos servidores da Web em que [!DNL Sensor] está instalado, abra e edite o [!DNL txlogd.conf] arquivo. Para fazer isso, conclua as seguintes etapas:

   1. Navegue até o [!DNL Sensor] e abra o [!DNL txlogd.conf] em um editor de texto.

   1. Localize o parâmetro ServerAddress e altere-o para refletir o endereço do novo servidor de destino.
   1. Salve e feche o arquivo.

1. Repita as etapas 2 a 3 em todos os servidores da Web restantes nos quais [!DNL Sensor] está instalado.
1. Reinicie o servidor de destino original (se ele ainda estiver para ser usado) e o novo servidor de destino.
1. Os dados começarão a transmitir para o novo servidor de destino que você especificou.
