---
description: Informações sobre como instalar um serviço de dados em um servidor de análise de big data.
solution: Analytics
title: Instalação de um serviço de dados em um servidor da análise de big data
topic: Data workbench
uuid: afe8e259-7fef-4327-9afc-18f36a1934db
translation-type: tm+mt
source-git-commit: 948c6dd04819e939b45745db573a53c8be51ce37

---


# Instalação de um serviço de dados em um servidor da análise de big data{#installing-a-data-service-on-a-data-workbench-server}

Informações sobre como instalar um serviço de dados em um servidor de análise de big data.

Se você estiver usando o serviço de dados de GeoInteligência de IP ou o serviço de dados de Geolocalização de IP, deverá instalar o perfil [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] os arquivos de pesquisa relacionados no servidor de análise de big data. Você deve concluir os seguintes procedimentos depois de instalar o [!DNL Geography] perfil da análise de big data. Consulte [Instalação da geografia](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md)da análise de big data. Se você não tiver instalado a análise de big data, siga as instruções no Guia ** do usuário da Análise de big data antes de continuar.

>[!NOTE]
>
>Para instalar os arquivos do serviço de dados, é necessário ter acesso aos arquivos no servidor do análise de big data.

A Adobe distribui os serviços de dados de GeoIntelligence e Geolocalização de IP como [!DNL .zip] arquivos. Cada [!DNL .zip] arquivo contém duas pastas: Pesquisas e Perfis. Para instalar um serviço de dados no servidor da análise de big data, execute as seguintes etapas:

* Instale o perfil do serviço de dados. Consulte [Instalação do perfil](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/c-inst-data-svc-prof.md)do serviço de dados.
* Instale as pesquisas do serviço de dados. Consulte [Instalação dos arquivos](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/t-inst-data-svc-lkp-files.md)de pesquisa do serviço de dados.

Você deve instalar o perfil do serviço de dados e os arquivos de pesquisa na máquina do servidor da análise de big data na qual você está processando e executando o perfil do conjunto de dados. Se você estiver executando um cluster de servidores de análise de big data, deverá instalar os arquivos no servidor mestre. Para obter informações sobre perfis de conjuntos de dados, consulte o Guia *de Configuração de* Conjuntos de Dados.
