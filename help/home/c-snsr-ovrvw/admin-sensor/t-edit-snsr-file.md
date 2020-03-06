---
description: O arquivo de configuração do sensor, txlogd.conf, contém parâmetros que o Sensor usa para estabelecer uma conexão com o servidor da análise de big data.
solution: Insight
title: Edição do arquivo Sensor txlogd.conf
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# Edição do arquivo Sensor txlogd.conf{#editing-the-sensor-txlogd-conf-file}

O arquivo de configuração do sensor, txlogd.conf, contém parâmetros que o Sensor usa para estabelecer uma conexão com o servidor da análise de big data.

Esses parâmetros incluem o endereço do servidor, o número da porta e o protocolo de comunicação (HTTP ou HTTPS). O arquivo de configuração também contém opções de filtragem de conteúdo de log e informações de experiência controladas. Experimentos controlados permitem que os designers do site realizem experimentos para testar o conteúdo ou projetar alterações em um subconjunto de todos os visitantes do site.

Ao alterar outros [!DNL txlogd.conf] parâmetros, como o endereço IP do [!DNL data workbench server] ou o nome do [!DNL Sensor], você pode simplesmente substituir [!DNL txlogd.conf] pela versão atualizada e [!DNL Sensor] coletar as alterações automaticamente. Em alguns sistemas, talvez você não consiga editar ou substituir o arquivo sem interromper o servidor da Web ou o processo do transmissor.

**Para abrir e editar txlogd.conf**

1. Navegue até o diretório de [!DNL Sensor] instalação e abra o [!DNL txlogd.conf] arquivo em um editor de texto.
1. Edite o arquivo conforme necessário.
1. Salve e feche o arquivo.

   * O local do arquivo de configuração de experimento controlado (definido pelo parâmetro ExpFile no [!DNL txlogd.conf] arquivo) deve estar em um diretório no servidor da Web acessível aos desenvolvedores de conteúdo da Web ou controlado pelo seu sistema de gerenciamento de conteúdo.
   * O valor no parâmetro ExpCookieURL é uma página virtual usada para testar sites. Um usuário visitando essa página receberá uma nova ID de rastreamento.

Para obter mais informações sobre como trabalhar com [!DNL txlogd.conf], entre em contato com os Serviços de consultoria da Adobe.
