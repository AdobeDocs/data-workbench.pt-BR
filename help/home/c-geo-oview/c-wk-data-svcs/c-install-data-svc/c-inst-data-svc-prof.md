---
description: Os perfis do serviço de dados (Geo-inteligência IP e Geo-localização de IP) são perfis internos que fornecem funcionalidade adicional para seu aplicativo Adobe.
solution: Analytics
title: Instalação do perfil do serviço de dados
topic: Data workbench
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Instalação do perfil do serviço de dados{#installing-the-data-service-profile}

Os perfis do serviço de dados (Geo-inteligência IP e Geo-localização de IP) são perfis internos que fornecem funcionalidade adicional para seu aplicativo Adobe.

Assim como com todos os outros perfis internos fornecidos pela Adobe, esses perfis não devem ser alterados. Toda personalização deve ocorrer em seu conjunto de dados ou em perfis específicos de função ou em outros perfis que você criar.

Os perfis do serviço de dados incluem o seguinte conjunto de dados que inclui arquivos a serem instalados em um servidor de análise de big data:

* **Perfis\*nome *do perfil\Dataset\Log Processing\Traffic\IP.cfg:** Lista o campo c-ip a ser transmitido do processamento de log para a transformação.
* **Perfis\*nome *do perfil \Dataset\Transformation\Geography\IPLookup.cfg:** Define uma transformação IPLookup que produz vários campos de dados geográficos usando o arquivo de geolinteligência de IP ou pesquisa de localização geográfica de IP fornecido.

Para obter informações sobre como o conjunto de dados de transformação incluir arquivos, consulte o Guia *de Configuração do* Conjunto de Dados.

Além disso, cada perfil de serviço de dados fornece um arquivo de camada de ponto de elemento chamado [!DNL IP Coordinates.layer]. Esse arquivo de camada permite mapear locais no conjunto de dados no mundo dinamicamente usando endereços IP. Após a instalação, a camada é armazenada na pasta Perfis\*nome do serviço de dados*\Maps no diretório de instalação do servidor da análise de big data.

O [!DNL IP Coordinates.layer] arquivo faz referência à dimensão Coordenadas, que é definida no [!DNL Coordinates.cfg] arquivo fornecido com o [!DNL Geography] perfil e localizado na pasta Dataset\Transformation\Geography folder. Cada elemento da dimensão Coordenadas definida no conjunto de dados é mapeado no globo usando as informações de latitude e longitude contidas nesse elemento. Para obter mais informações sobre camadas de ponto de elemento que usam pontos dinâmicos, consulte [Definição de camadas de ponto de elemento usando pontos](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3)dinâmicos.

>[!NOTE]
>
>Se você instalou o serviço de dados de GeoIntelligence e Geo-location de IP antes da versão 5.1, o arquivo de camada de ponto de elemento referencia um arquivo de pesquisa em vez de usar pontos dinâmicos. Cada arquivo de camada faz referência ao arquivo de pesquisa IP Geocodes e à dimensão IP Geocode. O arquivo de pesquisa de códigos geográficos IP contém uma lista de códigos geográficos IP (localizações geográficas com base no endereço IP) e a latitude e a longitude de cada um. Cada elemento de uma dimensão IP Geocode definida em seu conjunto de dados é mapeado no globo usando a latitude e a longitude listadas para esse código geográfico de IP no arquivo de pesquisa IP Geocodes.

O nome do arquivo de camada e os arquivos aos quais ele faz referência diferem para cada serviço de dados:

* O [!DNL IP Geocodes D.layer] arquivo é instalado com o perfil IP Geo-Intelligence (Digital Envoy). Essa camada de ponto de elemento faz referência ao arquivo de [!DNL IP Geocodes D yyyymmdd.txt] pesquisa (que você precisa atualizar periodicamente) e à dimensão do código geográfico de IP D.

* O [!DNL IP Geocodes Q.layer] arquivo é instalado com o perfil de localização geográfica IP (Quova). Essa camada de ponto de elemento faz referência ao arquivo de [!DNL IP Geocodes Q yyyymmdd.txt] pesquisa (que você precisa atualizar periodicamente) e à dimensão Q de código geográfico de IP.

Para obter mais informações sobre camadas de ponto de elemento que usam arquivos de pesquisa, consulte [Definição de camadas de ponto de elemento que fazem referência a arquivos](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f)de pesquisa.

## Para instalar o perfil IP GeoIntelligence ou IP GeoLocation {#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>As instruções de instalação a seguir pressupõem que você instalou a análise de big data e estabeleceu uma conexão entre a análise de big data e o servidor da análise de big data no qual você está instalando a análise de big data [!DNL Geography]. Se você não tiver feito isso, consulte o Guia ** do usuário da Análise de big data.

1. Abra a pasta Perfis a partir do [!DNL .zip] arquivo recebido da Adobe.
1. Copie a pasta IP Geo-Intelligence ou IP Geo-location para a pasta Perfis no diretório de instalação do servidor da análise de big data. Você quer acabar com um ...\Profiles\IP Geo-intelligence folder or a ...\Profiles\IP Geo-location on your data workbench server as shown in the following example. Os nomes das outras pastas dentro da [!DNL Profiles] pasta podem diferir dos mostrados.

   ![](assets/Geo_installProfiles_dirIP.png)

1. Use as etapas a seguir para atualizar o [!DNL profile.cfg] arquivo para cada perfil com o qual você deseja usar o perfil [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] .

   1. Abra o **[!UICONTROL Profile Manager]**.
   1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL profile.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção para este arquivo é exibida na [!DNL User] coluna.

   1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. A [!DNL profile.cfg] janela é exibida.

   1. Na [!DNL profile.cfg]janela, clique com o botão direito do mouse **[!UICONTROL Directories]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Para adicionar o novo diretório ao final da lista de diretórios, clique com o botão direito do mouse no número ou nome do último diretório na lista e clique em **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Digite o nome do novo diretório: [!DNL IP Geo-intelligence] ou eu [!DNL P Geo-location].

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Na [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção para [!DNL profile.cfg] na [!DNL User] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

>[!NOTE]
>
>Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pela Adobe (incluindo o perfil [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] ), pois suas alterações são substituídas quando você instala atualizações nesses perfis.

