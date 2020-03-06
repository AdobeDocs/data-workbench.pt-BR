---
description: Você deve instalar e executar o Sensor em cada servidor da Web que serve o conteúdo do site para coletar todas as solicitações que são vistas por esses servidores.
solution: Analytics
title: Como eu obtenho esses dados_
topic: Data workbench
uuid: c0d8b01e-a135-4ef7-8159-811766929f62
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Como eu obtenho esses dados_{#how-do-i-acquire-this-data}

Você deve instalar e executar o Sensor em cada servidor da Web que serve o conteúdo do site para coletar todas as solicitações que são vistas por esses servidores.

Essas solicitações correspondem a 90% ou mais das solicitações feitas ao site e 90% ou mais dos dados necessários para a análise completa do tráfego do site. [!DNL Page Tags] deve ser usado para coletar os 10% ou menos restantes dos dados de tráfego que não são conhecidos dos servidores da Web. As configurações a seguir, no entanto, são válidas para a coleta de dados de solicitação da Web do site, por ordem de preferência, com base em nossa experiência operacional:

1. [!DNL Sensor] está instalado em cada servidor da Web que você controla e que oferece suporte ao seu site. O conteúdo de sites de terceiros, o conteúdo servido do cache e certos tipos de conteúdo dinâmico devem ser marcados e essas tags de página devem enviar os dados coletados para um servidor da Web no seu local em execução [!DNL Sensor]. Você pode adicionar um servidor da Web adicional se o nível de tráfego de solicitação de tag da página justificar tal ou, em casos especiais, dedicar um servidor da Web para coletar essas solicitações de tag da página.
1. [!DNL Sensor] é instalado em dois servidores da Web, também conhecidos como servidores de coleta de dados neste guia, em seu local dedicado à coleta de dados de solicitação de tag de página de páginas marcadas. Todo o conteúdo do site é marcado e todas as tags de página são direcionadas para os dois servidores de coleta de dados.
1. [!DNL Sensor’s] os serviços de coleta de dados são fornecidos por um terceirizado que executa servidores de coleta de dados para coletar todos os dados de solicitação da Web. Nesse caso, todo o conteúdo do site é marcado e as tags de página enviam seus dados para os servidores de coleta de dados terceirizados.

   Para obter mais informações sobre [!DNL Sensor], consulte o *Data Workbench[!DNL Sensor]Guide*.

