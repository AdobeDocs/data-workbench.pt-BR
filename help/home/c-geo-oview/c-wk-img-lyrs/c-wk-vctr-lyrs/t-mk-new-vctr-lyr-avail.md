---
description: Etapas para tornar uma camada vetorial disponível para exibição na visualização global.
solution: Analytics
title: Disponibilização de uma nova camada de vetor
topic: Data workbench
uuid: 7e88f183-b0aa-452d-b124-7cd970be9bb9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Disponibilização de uma nova camada de vetor{#making-a-new-vector-layer-available}

Etapas para tornar uma camada vetorial disponível para exibição na visualização global.

1. Na pasta Perfis\*nome do perfil*\Maps no diretório de instalação do servidor da análise de big data, coloque o arquivo de camada e os [!DNL .vec] arquivos ou [!DNL .tsv] arquivos.
1. Edite o [!DNL order.txt] arquivo na pasta Perfis\*nome do perfil*\Mapas para refletir a ordem em que deseja que as camadas sejam exibidas. Por padrão, as camadas são exibidas em ordem lexicográfica pelos nomes.

   >[!NOTE]
   >
   >Ao editar o [!DNL order.txt] arquivo, tenha cuidado para não ocultar as camadas do mapa que você deseja mostrar.

   Para obter mais informações sobre o uso de [!DNL order.txt] arquivos, consulte o capítulo Configuração de recursos de interface e análise do Guia *do Usuário do* Análise de big data.

1. Na análise de big data, selecione o perfil desejado clicando com o botão direito do mouse na barra de título da área de trabalho e clicando em **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Clique com o botão direito do mouse na barra de título do espaço de trabalho e clique em **[!UICONTROL Work Online]**. Um X é exibido ao lado de [!DNL Work Online].
1. Abra um espaço de trabalho e, em uma visualização de globo, clique com o botão direito do mouse e selecione a nova camada. Um X é exibido ao lado do nome da camada.
