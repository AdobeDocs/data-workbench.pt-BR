---
description: Você deve instalar e executar o Sensor em cada servidor da Web que fornece o conteúdo para seu site coletar todas as solicitações que são vistas por esses servidores.
title: Como eu obtenho esses dados?
uuid: c0d8b01e-a135-4ef7-8159-811766929f62
exl-id: 1c886f60-eae9-48c2-b641-396c622035d4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---

# Como eu obtenho esses dados?{#how-do-i-acquire-this-data}

{{eol}}

Você deve instalar e executar o Sensor em cada servidor da Web que fornece o conteúdo para seu site coletar todas as solicitações que são vistas por esses servidores.

Essas solicitações compõem 90% ou mais das solicitações feitas no site e 90% ou mais dos dados necessários para a análise completa do tráfego do site. [!DNL Page Tags] O deve ser usado para coletar os 10% ou menos dos dados de tráfego restantes que não são conhecidos dos servidores da Web. As seguintes, no entanto, são configurações válidas para a coleta de dados de solicitação da Web do seu site, em ordem de preferência, com base em nossa experiência operacional:

1. [!DNL Sensor] O está instalado em cada servidor da Web que você controla e que suporta o seu site. O conteúdo de sites de terceiros, o conteúdo veiculado a partir do cache e determinados tipos de conteúdo dinâmico devem ser marcados e essas tags de página devem enviar os dados coletados para um servidor da Web no seu local em execução [!DNL Sensor]. Você pode adicionar um servidor da Web adicional se o nível de tráfego de solicitação de tag da página justificar tal ou, em casos especiais, dedicar um servidor da Web para coletar essas solicitações de tag da página.
1. [!DNL Sensor] O é instalado em dois servidores da Web, também conhecidos como servidores de coleta de dados neste guia, em seu local dedicado à coleta de dados de solicitação de tag de página de páginas marcadas. Todo o conteúdo do site é marcado e todas as tags de página são direcionadas para os dois servidores de coleta de dados.
1. [!DNL Sensor’s] os serviços de coleta de dados são fornecidos por um terceirizado que executa servidores de coleta de dados para coletar todos os dados de solicitação da Web. Nesse caso, todo o conteúdo do site é marcado e as tags de página enviam seus dados para os servidores de coleta de dados terceirizados.

   Para obter mais informações sobre [!DNL Sensor], consulte o *Data Workbench [!DNL Sensor] Guia*.
