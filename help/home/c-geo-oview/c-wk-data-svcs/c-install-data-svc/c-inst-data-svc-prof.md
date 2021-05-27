---
description: Os perfis do serviço de dados (Geosinteligência de IP e Geolocalização de IP) são perfis internos que fornecem funcionalidade adicional para seu aplicativo Adobe.
title: Instalar o perfil do serviço de dados
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
exl-id: 51d080bb-f874-426c-91ea-3912ffd38419
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 1%

---

# Instalar o perfil do serviço de dados{#installing-the-data-service-profile}

Os perfis do serviço de dados (Geosinteligência de IP e Geolocalização de IP) são perfis internos que fornecem funcionalidade adicional para seu aplicativo Adobe.

Assim como em todos os outros perfis internos fornecidos pelo Adobe, esses perfis não devem ser alterados. Toda personalização deve ocorrer em seu conjunto de dados, em perfis específicos de função ou em outros perfis que você criar.

Os perfis do serviço de dados incluem os seguintes arquivos de inclusão do conjunto de dados a serem instalados em um servidor do Data Workbench:

* **Perfis\*nome do perfil *\Dataset\Log Processing\Traffic\IP.cfg:** lista o campo c-ip a ser transmitido do processamento de log para a transformação.
* **Perfis\*nome do perfil *\Dataset\Transformation\Geography\IPLookup.cfg:** Define uma transformação IPLookup que produz vários campos de dados geográficos usando a Geosinteligência de IP ou o arquivo de pesquisa de GeoLocation de IP fornecido.

Para obter informações sobre arquivos de inclusão do conjunto de dados de transformação, consulte o *Guia de Configuração do Conjunto de Dados*.

Além disso, cada perfil de serviço de dados fornece um arquivo de camada de ponto de elemento chamado [!DNL IP Coordinates.layer]. Esse arquivo de camada permite mapear locais em seu conjunto de dados no mundo dinamicamente usando endereços IP. Após a instalação, a camada é armazenada na pasta Profiles\*data service name*\Maps no diretório de instalação do servidor do Data Workbench.

O arquivo [!DNL IP Coordinates.layer] faz referência à dimensão Coordenadas, que é definida no arquivo [!DNL Coordinates.cfg] fornecido com o perfil [!DNL Geography] e localizada na pasta Dataset\Transformation\Geography folder. Cada elemento da dimensão Coordenadas definido no conjunto de dados é mapeado no globo usando as informações de latitude e longitude contidas nesse elemento. Para obter mais informações sobre camadas de ponto de elemento que usam pontos dinâmicos, consulte [Definição de camadas de ponto de elemento usando pontos dinâmicos](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

>[!NOTE]
>
>Se você instalou o serviço de dados de Geolocalização de IP e Geolocalização de IP anterior à versão 5.1, seu arquivo de camada de ponto de elemento faz referência a um arquivo de pesquisa em vez de usar pontos dinâmicos. Cada arquivo de camada faz referência ao arquivo de pesquisa de Códigos geográficos IP e à dimensão Código geográfico de IP. O arquivo de pesquisa de Geocódigos IP contém uma lista de geocódigos IP (locais geográficos com base no endereço IP) e a latitude e a longitude de cada um. Cada elemento de uma dimensão de código geográfico de IP definido em seu conjunto de dados é mapeado no mundo usando a latitude e a longitude listadas para esse código geográfico de IP no arquivo de pesquisa de códigos geográficos de IP.

O nome do arquivo de camada e os arquivos aos quais ele faz referência são diferentes para cada serviço de dados:

* O arquivo [!DNL IP Geocodes D.layer] é instalado com o perfil IP Geo-intelligence (Digital Envoy). Essa camada de ponto de elemento faz referência ao arquivo de pesquisa [!DNL IP Geocodes D yyyymmdd.txt] (que você precisa atualizar periodicamente) e à dimensão ID do código geográfico de IP.

* O arquivo [!DNL IP Geocodes Q.layer] é instalado com o perfil de Geolocalização de IP (Quova). Essa camada de ponto de elemento faz referência ao arquivo de pesquisa [!DNL IP Geocodes Q yyyymmdd.txt] (que você precisa atualizar periodicamente) e à dimensão P do código geográfico de IP.

Para obter mais informações sobre camadas de ponto de elemento que usam arquivos de pesquisa, consulte [Definir camadas de ponto de elemento que fazem referência a arquivos de pesquisa](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f).

## Para instalar o perfil IP GeoIntelligence ou IP GeoLocation {#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>As instruções de instalação a seguir pressupõem que você instalou o Data Workbench e estabeleceu uma conexão entre o Data Workbench e o servidor do Data Workbench no qual está instalando o Data Workbench [!DNL Geography]. Se ainda não tiver feito isso, consulte o *Guia do Usuário do Data Workbench*.

1. Abra a pasta Perfis no arquivo [!DNL .zip] que você recebeu do Adobe.
1. Copie a pasta Geo-intelligence ou IP Geo-location para a pasta Perfis no diretório de instalação do servidor do Data Workbench. Você quer acabar com um ...\Profiles\IP Geo-intelligence folder or a ...\Profiles\IP Geo-location on your data workbench server as shown in the following example. Os nomes das outras pastas dentro da pasta [!DNL Profiles] podem ser diferentes dos mostrados.

   ![](assets/Geo_installProfiles_dirIP.png)

1. Use as etapas a seguir para atualizar o arquivo [!DNL profile.cfg] para cada perfil com o qual você deseja usar o perfil [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location].

   1. Abra o **[!UICONTROL Profile Manager]**.
   1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL profile.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece na coluna [!DNL User].

   1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. A janela [!DNL profile.cfg] é exibida.

   1. Na janela [!DNL profile.cfg], clique com o botão direito do mouse em **[!UICONTROL Directories]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Para adicionar o novo diretório ao final da lista de diretórios, clique com o botão direito do mouse no número ou nome do último diretório na lista e clique em **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Digite o nome do novo diretório: [!DNL IP Geo-intelligence] ou I [!DNL P Geo-location].

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. No [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção de [!DNL profile.cfg] na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***.

>[!NOTE]
>
>Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pelo Adobe (incluindo o perfil [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence]), pois as alterações são substituídas ao instalar atualizações nesses perfis.
