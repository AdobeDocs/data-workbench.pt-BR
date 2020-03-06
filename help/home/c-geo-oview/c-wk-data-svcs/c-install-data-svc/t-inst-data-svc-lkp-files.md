---
description: Etapas para instalar os arquivos de pesquisa IP Geo-Intelligence ou IP Geo-location.
solution: Analytics
title: Instalação dos arquivos de pesquisa do serviço de dados
topic: Data workbench
uuid: a3fe8a14-2c74-4105-bc5b-2298f0f4b61e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Instalação dos arquivos de pesquisa do serviço de dados{#installing-the-data-service-lookup-files}

Etapas para instalar os arquivos de pesquisa IP Geo-Intelligence ou IP Geo-location.

O arquivo de pesquisa (Pesquisas\*nome do perfil*\*nome do arquivo de dados*) fornecido com o perfil do serviço de dados é um arquivo binário ( [!DNL .bin]) que contém dados geograficamente relacionados com base no endereço IP. É necessário substituir esse arquivo periodicamente para garantir que você tenha os dados geográficos mais recentes. Consulte [Atualização de arquivos](../../../../home/c-geo-oview/c-wk-data-svcs/c-updt-data-svc-files.md#concept-2b3d11e4cb814fc09add5de58a87045c)do serviço de dados.

**Para instalar os arquivos de pesquisa de GeoIntelligence de IP ou GeoLocation**

>[!NOTE]
>
>Todos os seus arquivos [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] de dados devem se encaixar na memória física disponível do servidor de análise de big data.

1. Abra a pasta Pesquisas a partir do [!DNL .zip] arquivo recebido da Adobe.
1. Copie a pasta IP Geo-Intelligence ou IP Geo-location para a pasta Pesquisas no diretório de instalação do servidor da análise de big data (você deseja acabar com um ...\Lookups\IP Geo-intelligence or a ...\Lookups\IP Geo-location folder on your data workbench server as shown in the following example. Os nomes das outras pastas dentro da pasta Pesquisas podem diferir dos mostrados.

   ![Informações da etapa](assets/Geo_installLookups_dirIP.png)

   >[!NOTE]
   >
   >Periodicamente, a Adobe envia arquivos que contêm arquivos atualizados [!DNL IP Geo-intelligence] ou de [!DNL IP Geo-location] pesquisa. Quando você recebe esses arquivos, é necessário carregá-los no servidor da análise de big data, conforme orientado pela Adobe. Para obter instruções, consulte a seção a seguir.

