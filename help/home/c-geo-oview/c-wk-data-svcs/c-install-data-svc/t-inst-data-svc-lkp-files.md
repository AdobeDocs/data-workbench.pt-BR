---
description: Etapas para instalar os arquivos de pesquisa de GeoIntelligence ou GeoLocation de IP.
title: Instalar os arquivos de pesquisa do serviço de dados
uuid: a3fe8a14-2c74-4105-bc5b-2298f0f4b61e
exl-id: b19904f4-ead0-4bed-a79f-864c78bc0e1d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 6%

---

# Instalar os arquivos de pesquisa do serviço de dados{#installing-the-data-service-lookup-files}

Etapas para instalar os arquivos de pesquisa de GeoIntelligence ou GeoLocation de IP.

O arquivo de pesquisa (Lookups\*nome do perfil*\*nome do arquivo de dados*) fornecido com o perfil do serviço de dados é um arquivo binário ( [!DNL .bin]) que contém dados geograficamente relacionados com base no endereço IP. Você deve substituir esse arquivo periodicamente para garantir que tenha os dados geográficos mais recentes. Consulte [Atualizando arquivos do serviço de dados](../../../../home/c-geo-oview/c-wk-data-svcs/c-updt-data-svc-files.md#concept-2b3d11e4cb814fc09add5de58a87045c).

**Para instalar os arquivos de pesquisa de geolocalização de IP ou geolocalização de IP**

>[!NOTE]
>
>Todos os arquivos de dados [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] devem se encaixar na memória física disponível do servidor do Data Workbench.

1. Abra a pasta Pesquisas do arquivo [!DNL .zip] que você recebeu do Adobe.
1. Copie a pasta IP Geo-intelligence ou IP GeoLocation para a pasta Lookups no diretório de instalação do servidor do Data Workbench (você deseja acabar com um ...\Lookups\IP Geo-intelligence or a ...\Lookups\IP Geo-location folder on your data workbench server as shown in the following example. Os nomes das outras pastas dentro da pasta Pesquisas podem ser diferentes dos mostrados.

   ![Informações da etapa](assets/Geo_installLookups_dirIP.png)

   >[!NOTE]
   >
   >Periodicamente, o Adobe envia arquivos contendo arquivos de pesquisa atualizados [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location]. Ao receber esses arquivos, você precisa carregá-los no servidor do Data Workbench, conforme determinado pelo Adobe. Para obter instruções, consulte a seção a seguir.
