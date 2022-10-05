---
description: Etapas para instalar os arquivos de pesquisa de GeoIntelligence ou GeoLocation de IP.
title: Instalar os arquivos de pesquisa do serviço de dados
uuid: a3fe8a14-2c74-4105-bc5b-2298f0f4b61e
exl-id: b19904f4-ead0-4bed-a79f-864c78bc0e1d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 6%

---

# Instalar os arquivos de pesquisa do serviço de dados{#installing-the-data-service-lookup-files}

{{eol}}

Etapas para instalar os arquivos de pesquisa de GeoIntelligence ou GeoLocation de IP.

O arquivo de pesquisa (Lookups\*nome do perfil*\*nome do arquivo de dados*) fornecido com o perfil do serviço de dados é um arquivo binário ( [!DNL .bin]) que contém dados geograficamente relacionados com base no endereço IP. Você deve substituir esse arquivo periodicamente para garantir que tenha os dados geográficos mais recentes. Consulte [Atualizar arquivos do serviço de dados](../../../../home/c-geo-oview/c-wk-data-svcs/c-updt-data-svc-files.md#concept-2b3d11e4cb814fc09add5de58a87045c).

**Para instalar os arquivos de pesquisa de geolocalização de IP ou geolocalização de IP**

>[!NOTE]
>
>Todos os seus [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] os arquivos de dados devem se encaixar na memória física disponível do servidor do Data Workbench.

1. Abra a pasta Pesquisas no [!DNL .zip] arquivo recebido do Adobe.
1. Copie a pasta IP Geo-intelligence ou IP GeoLocation para a pasta Lookups no diretório de instalação do servidor do Data Workbench (você deseja acabar com um ...\Lookups\IP GeoIntelligence ou um ...\Lookups\IP Pasta de geolocalização no servidor do Data Workbench, como mostrado no exemplo a seguir. Os nomes das outras pastas dentro da pasta Pesquisas podem ser diferentes dos mostrados.

   ![Informações da etapa](assets/Geo_installLookups_dirIP.png)

   >[!NOTE]
   >
   >Periodicamente, o Adobe envia arquivos contendo atualizações [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] arquivos de pesquisa. Ao receber esses arquivos, você precisa carregá-los no servidor do Data Workbench, conforme determinado pelo Adobe. Para obter instruções, consulte a seção a seguir.
