---
description: Informações sobre a instalação de um serviço de dados em um servidor do Data Workbench.
title: Instalar um serviço de dados em um servidor do Data Workbench
uuid: afe8e259-7fef-4327-9afc-18f36a1934db
exl-id: 414e93b7-4e9c-4c84-8fba-8052939240c5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 7%

---

# Instalar um serviço de dados em um servidor do Data Workbench{#installing-a-data-service-on-a-data-workbench-server}

Informações sobre a instalação de um serviço de dados em um servidor do Data Workbench.

Se você estiver usando o serviço de dados de Geolocalização de IP ou o serviço de dados de Geolocalização de IP, deverá instalar o perfil [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] e os arquivos de pesquisa relacionados no servidor do Data Workbench. Você deve concluir os seguintes procedimentos após instalar o perfil do Data Workbench [!DNL Geography]. Consulte [Instalando a Geografia do Data Workbench](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md). Se você não tiver instalado o Data Workbench, siga as instruções no *Guia do Usuário do Data Workbench* antes de continuar.

>[!NOTE]
>
>Para instalar os arquivos do serviço de dados, você deve ter acesso aos arquivos no servidor do Data Workbench.

O Adobe distribui os serviços de dados de geolocalização de IP e geolocalização de IP como arquivos [!DNL .zip]. Cada arquivo [!DNL .zip] contém duas pastas: Pesquisas e Perfis. Para instalar um serviço de dados no servidor do Data Workbench, você deve executar as seguintes etapas:

* Instale o perfil do serviço de dados. Consulte [Instalar o perfil do serviço de dados](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/c-inst-data-svc-prof.md).
* Instale as pesquisas do serviço de dados. Consulte [Instalar os arquivos de pesquisa do serviço de dados](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/t-inst-data-svc-lkp-files.md).

Você deve instalar o perfil do serviço de dados e os arquivos de pesquisa na máquina do servidor do Data Workbench na qual você está processando e executando o perfil do conjunto de dados. Se você estiver executando um cluster de servidores do Data Workbench, deverá instalar os arquivos no servidor principal. Para obter informações sobre perfis do conjunto de dados, consulte o *Guia de configuração do conjunto de dados*.
