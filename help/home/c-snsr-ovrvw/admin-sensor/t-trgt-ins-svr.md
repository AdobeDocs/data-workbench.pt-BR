---
description: Para alterar o servidor de análise de big data com o qual um sensor se comunica (o servidor de destino), edite o arquivo txlogd.conf em cada um dos servidores da Web nos quais o Sensor está instalado.
solution: Insight
title: Alteração do Servidor do Target Data Workbench
uuid: 931d376d-8622-4858-8290-19ce91538570
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Alteração do Servidor do Target Data Workbench{#changing-the-target-data-workbench-server}

Para alterar o servidor de análise de big data com o qual um sensor se comunica (o servidor de destino), edite o arquivo txlogd.conf em cada um dos servidores da Web nos quais o Sensor está instalado.

**Alteração no destino[!DNL data workbench server]**

1. Pare o servidor de destino original e o novo servidor de destino.
1. Copie o [!DNL .vsl] arquivo mais atual do servidor de destino original para o novo servidor de destino. Ao reiniciar o novo servidor de destino em uma etapa posterior, isso faz com que todos os novos [!DNL Sensor] dados sejam anexados ao arquivo atual e existente [!DNL .vsl] em vez de criar um novo [!DNL .vsl] arquivo. Para isso, execute as seguintes etapas:

   1. No servidor de destino original, navegue até a [!DNL \Logs] pasta no diretório de [!DNL data workbench server] instalação.

   1. Copie o [!DNL .vsl] arquivo mais atual na pasta.
   1. No novo servidor de destino, navegue até a [!DNL \Logs] pasta no diretório de [!DNL data workbench server] instalação e cole o [!DNL .vsl] arquivo nessa pasta.

1. Em um dos servidores da Web nos quais [!DNL Sensor] está instalado, abra e edite o [!DNL txlogd.conf] arquivo. Para isso, execute as seguintes etapas:

   1. Navegue até o diretório de [!DNL Sensor] instalação e abra o [!DNL txlogd.conf] arquivo em um editor de texto.

   1. Localize o parâmetro ServerAddress e altere-o para refletir o endereço do novo servidor de destino.
   1. Salve e feche o arquivo.

1. Repita as etapas de 2 a 3 em todos os servidores da Web restantes nos quais [!DNL Sensor] está instalado.
1. Reinicie o servidor de destino original (se ainda estiver para ser usado) e o novo servidor de destino.
1. Os dados começarão a transmitir ao novo servidor de destino que você especificou.
