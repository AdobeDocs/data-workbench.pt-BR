---
description: O arquivo de configuração do Sensor, txlogd.conf, contém parâmetros que o Sensor usa para estabelecer uma conexão com o servidor do Data Workbench.
title: Editar o arquivo do Sensor txlogd.conf
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
exl-id: ed243bb4-cf87-4bcf-89d6-5ff5cec3bc6e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 3%

---

# Editar o arquivo do Sensor txlogd.conf{#editing-the-sensor-txlogd-conf-file}

{{eol}}

O arquivo de configuração do Sensor, txlogd.conf, contém parâmetros que o Sensor usa para estabelecer uma conexão com o servidor do Data Workbench.

Esses parâmetros incluem o endereço do servidor, o número da porta e o protocolo de comunicação (HTTP ou HTTPS). O arquivo de configuração também contém opções de filtragem de conteúdo de log e informações experimentais controladas. Experimentos controlados permitem que designers de sites realizem experimentos para testar alterações de conteúdo ou design em um subconjunto de todos os visitantes do site.

Ao alterar outros [!DNL txlogd.conf] , como o endereço IP da [!DNL data workbench server] ou o nome da [!DNL Sensor], você pode simplesmente substituir [!DNL txlogd.conf] com a versão atualizada e [!DNL Sensor] O selecionará as alterações automaticamente. Em alguns sistemas, talvez você não consiga editar ou substituir o arquivo sem parar o servidor da Web ou o processo do transmissor.

**Para abrir e editar txlogd.conf**

1. Navegue até o [!DNL Sensor] e abra o [!DNL txlogd.conf] em um editor de texto.
1. Edite o arquivo conforme necessário.
1. Salve e feche o arquivo.

   * O local do arquivo de configuração de experimento controlado (definido pelo parâmetro ExpFile na função [!DNL txlogd.conf] ) deve estar em um diretório no servidor da Web que seja acessível aos desenvolvedores de conteúdo da Web ou controlado pelo seu sistema de gerenciamento de conteúdo.
   * O valor no parâmetro ExpCookieURL é uma página virtual usada para testar sites. Um usuário que visitar essa página receberá uma nova ID de rastreamento.

Para obter mais informações sobre como trabalhar com o [!DNL txlogd.conf], entre em contato com os Serviços de consultoria da Adobe.
